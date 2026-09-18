---
tags: [creatio, dev-tools, banza-devhelper, csharp, creatio-8, standalone-package]
date: 2026-09-17
---

> ЗАУВАЖТЕ!
> Тестувалось лише на варіанті `fileDesignMode = 'true'` на локальному середовищі, на cloud середовищі не тестувалось

# Banza.DevHelper — виконання C# (ESQ Debug) у Creatio 8.x

Сторінка `…/0/Nui/ViewModule.aspx#BaseSchemaModuleV2/TsiDevESQDebugPage`, вкладка **C#** → сервіс `TsiDevESQDebugService/GetSQLFromCSharp` → `TsiDevDynamicCodeExecutor.Execute()` компілює скрипт користувача через `CSharpCodeProvider` і викликає `Run(UserConnection)`.

У 7.x працювало, у 8.x падало ще на компіляції:

```
The type or namespace name 'TsiDevIRunable' does not exist in the namespace 'Terrasoft.Configuration'
(are you missing an assembly reference?)
   at Terrasoft.Configuration.TsiDevScriptEngine.Compile(...)
```

плюс шум `The predefined type 'System.ObsoleteAttribute' is defined in multiple assemblies…` — це **warning CS1685**, який код помилково додавав у список помилок.

## Причина

| | Creatio 7.x | Creatio 8.x |
|---|---|---|
| Куди компілюються `Files/*.cs` пакета | у спільну `Terrasoft.Configuration.dll` | в окрему збірку пакета `Pkg/<Pkg>/Files/Bin/<Pkg>.dll` (пакет має `Files/<Pkg>.csproj`) |
| Де живе `TsiDevIRunable` | `Terrasoft.Configuration.dll` | `Banza.DevHelper.dll` (namespace лишається `Terrasoft.Configuration`) |
| `Assembly.Location` збірки пакета | є | **порожній** — платформа вантажить її з `byte[]` (`LoadPackageAssemblies`, `EnableResolveAssemblyFromStandalonePackage` у `Terrasoft.Core.dll`) |

`TsiDevDynamicCodeExecutor.GetLocations()` збирав референси для компілятора так: `AppDomain.CurrentDomain.GetAssemblies()` → `assembly.Location` (порожні відкидаються) + окремо вивантажена `Terrasoft.Configuration.dll`. У 8.x у результат не потрапляє **жодна** збірка standalone-пакетів, включно з власною.

Перевірка (без запуску):

```bash
grep -a -c TsiDevIRunable Pkg/Banza.DevHelper/Files/Bin/Banza.DevHelper.dll   # 1
grep -a -c TsiDevIRunable Terrasoft.Configuration/bin/Terrasoft.Configuration.dll  # 0
```

## Виправлення — `Files/TsiDevDynamicCodeExecutor.cs`

Усі зміни — доповнення, старий код не видалявся.

**1. Властивості**

```csharp
/// <summary> Path to packages folder (Terrasoft.Configuration\Pkg) </summary>
protected string PackagesPath => Path.Combine(AppConnection.AppSettings.AppBinDirectory, @"..\Terrasoft.Configuration\Pkg");

/// <summary> Assembly of this package (Creatio 8+: package Files are compiled into a standalone
/// assembly, not into Terrasoft.Configuration.dll, so TsiDevIRunable lives here) </summary>
protected Assembly ExecutorAssembly => typeof(TsiDevIRunable).Assembly;
```

**2. `GetLocations()` — один новий крок**

```csharp
UnloadConfigurationDllIntoFile(locations);
UploadAndAddPackageDlls(locations);
AddStandalonePackageDlls(locations);          // <-- додано
DeleteLocationsDuplicatesAndEmptyValues(ref locations);
```

**3. Нові методи** — власна збірка завжди; для кожної завантаженої в AppDomain збірки з порожнім `Location` шукається `Pkg\{Name}\Files\Bin\{Name}.dll` (щоб у скриптах можна було використовувати класи інших пакетів — `CrtCoreBase`…):

```csharp
protected void AddStandalonePackageDlls(List<string> locations) {
	string ownLocation = GetStandalonePackageDllPath(ExecutorAssembly);
	if (!string.IsNullOrEmpty(ownLocation)) {
		locations.Add(ownLocation);
	}
	foreach (Assembly assembly in AppDomain.CurrentDomain.GetAssemblies()) {
		if (assembly.IsDynamic || assembly == ExecutorAssembly) {
			continue;
		}
		string location = string.Empty;
		try {
			location = assembly.Location;
		} catch (Exception) { }
		if (!string.IsNullOrEmpty(location)) {
			continue;
		}
		string pkgDllPath = GetStandalonePackageDllPath(assembly);
		if (!string.IsNullOrEmpty(pkgDllPath)) {
			locations.Add(pkgDllPath);
		}
	}
}

protected string GetStandalonePackageDllPath(Assembly assembly) {
	try {
		if (!string.IsNullOrEmpty(assembly.Location) && System.IO.File.Exists(assembly.Location)) {
			return assembly.Location;
		}
	} catch (Exception) { }
	string name = assembly.GetName().Name;
	string path = Path.Combine(PackagesPath, name, "Files", "Bin", name + ".dll");
	return System.IO.File.Exists(path) ? path : string.Empty;
}
```

> Не можна просто додати всі `Pkg/*/Files/Bin/*.dll`: там трапляються нативні `Microsoft.Data.SqlClient.SNI.*.dll` (csc впаде з CS0009), застарілі копії `Terrasoft.Configuration.dll`, дублі `Newtonsoft.Json.dll`. Тому — лише `<Name>.dll` для реально завантажених збірок.

**4. `Execute()` — резолвер збірок.** Скрипт компілюється проти файлу на диску, а в рантаймі та сама збірка вже завантажена з `byte[]`; Fusion не знаходить її за іменем → був би `FileNotFoundException` або `InvalidCastException` при `(TsiDevIRunable)`. Тимчасовий `AssemblyResolve` повертає вже завантажений екземпляр:

```csharp
public string Execute(string csCode) {
	TsiDevScriptEngine engine = new TsiDevScriptEngine();
	ResolveEventHandler resolver = ResolveLoadedAssembly;
	AppDomain.CurrentDomain.AssemblyResolve += resolver;
	try {
		var run = (TsiDevIRunable)engine.Compile(
			csCode, Locations.ToArray(), "TsiDevTemp.ScriptCode.ScriptClass");
		return run.Run(userConnection);
	} finally {
		AppDomain.CurrentDomain.AssemblyResolve -= resolver;
	}
}

protected static Assembly ResolveLoadedAssembly(object sender, ResolveEventArgs args) {
	string name = new AssemblyName(args.Name).Name;
	return AppDomain.CurrentDomain.GetAssemblies()
		.FirstOrDefault(assembly => !assembly.IsDynamic && assembly.GetName().Name == name);
}
```

**5. `TsiDevScriptEngine.Compile()` — тільки помилки**

```csharp
for (int i = 0; i < CompilerResults.Errors.Count; i++) {
	if (CompilerResults.Errors[i].IsWarning) {   // <-- додано
		continue;
	}
	errors.Add(CompilerResults.Errors[i].ErrorText);
}
```

## Розгортання

1. Локальна перевірка без дотику до `Files/Bin`:
   ```bash
   dotnet build Files/Banza.DevHelper.csproj -c Release -p:OutputPath="<temp>/"
   ```
   (перевизначати `BaseIntermediateOutputPath` **не треба** — тоді старий `Files/obj` потрапляє в компіляцію і сиплються `CS0579 Duplicate attribute`).
2. Конфігурація → пакет **Banza.DevHelper** → **Compile** (або Compile all), щоб IIS завантажив нову `Files/Bin/Banza.DevHelper.dll`.

## Що ще може вилізти в 8.x (не міняли)

- `UnloadConfigurationDllIntoFileFromFileSystem` копіює `Terrasoft.Configuration.dll` і `*.netmodule` — у 8.x модулів немає, код це переживає.
- `UploadAndAddPackageDlls` читає `SysPackageReferenceAssembly` — таблиця ще існує.
- `#if NETFRAMEWORK` — під .NET Core/8 `Compile` кидає `NotSupportedException` (CodeDom нема); потрібен Roslyn.
