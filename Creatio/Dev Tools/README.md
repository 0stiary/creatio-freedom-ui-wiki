---
tags: [creatio, dev-tools, readme]
---
# Dev Tools — сторонні інструменти розробника в Creatio 8.x

Нотатки про пакети-помічники (SQL-консоль, виконання C#, ESQ-дебаг), які писалися під Creatio 7.x, і про те, що в них ламається у 8.x та як лагодити. Усе перевірено на Creatio 8.3.x** (PostgreSQL, IIS, .NET Framework, file design mode).

| Сторінка                                           | Що там                                                                                                                                                                                                                                               |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Banza.DevHelper — виконання коду у Creatio 8]]   | `TsiDevESQDebugPage` → вкладка C# падає з `TsiDevIRunable does not exist`: у 8.x `Files/*.cs` пакета компілюються в окрему `Files/Bin/<Pkg>.dll`, яка вантажиться з `byte[]` без `Location`. Патч `TsiDevDynamicCodeExecutor.cs` + `AssemblyResolve` |
| [[Samarasoft.SqlConsole — сортування результатів]] | DataTables ігнорує `ORDER BY` (`order: [[0,'asc']]`) і сортує дати як текст; `Terrasoft.Resources.CultureSettings` як фронтовий аналог `CurrentUser.DateTimeFormat`; власні типи `sql-date` / `sql-num`. «Show query log» падає на PostgreSQL (сирий MSSQL-SQL → `Select`-білдер) |

## Спільні висновки

- **Standalone-пакет у 8.x = окрема збірка.** Усе, що в 7.x «просто було» в `Terrasoft.Configuration.dll` (інтерфейси, хелпери), тепер треба резолвити явно; `Assembly.Location` у таких збірок порожній.
