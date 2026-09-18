---
tags:
  - creatio
  - dev-tools
  - sql-console
  - datatables
  - culture-settings
  - postgresql
date: 2026-09-17
---
# Samarasoft.SqlConsole — сортування результатів (ORDER BY ігнорується, дати сортуються як текст) + лог запитів на PostgreSQL

Модуль `…/0/Nui/ViewModule.aspx#SqlConsoleModule`, пакет `Samarasoft.SqlConsole` 7.7.0 (DB-only, у `Pkg/` відсутній; джерела — `Samarasoft.SqlConsole`). Результат запиту рендериться jQuery **DataTables 1.10** у `SqlConsoleModule.js` → `showQueryResult()`.

## Симптоми

1. `SELECT … ORDER BY "CreatedOn"` — таблиця все одно відсортована за `Id`.
2. Клік по заголовку колонки з датою дає «переплутаний» порядок.

## Причини

**1.** DataTables має дефолт `order: [[0, 'asc']]` — після ініціалізації сам сортує за першою колонкою (`Id`) і перезаписує порядок з БД. У `showQueryResult` опція `order` не задавалась.

**2.** Сервіс віддає всі значення **рядками**: `field.ToString()`, `DBNull` → `"NULL"` (`SqlConsoleService.cs:84`). DataTables визначає тип колонки автоматично і лише якщо **всі** комірки проходять детектор:
- вбудований детектор дати очікує `yyyy-mm-dd[ hh:mm[:ss]]`; `12/22/2018 9:17:24 PM` або `22.12.2018 21:17:24` йому не відповідають;
- `"NULL"` ламає детекцію і дат, і чисел.

Колонка отримує тип `string` і сортується лексикографічно: `1/15/2026` < `10/6/2021` < `12/22/2018`; `"10"` < `"2"`.

## Важливо про формат дат із сервісу

`DateTime.ToString()` на сервері використовує культуру **«Date and time format» профілю користувача** (Creatio ставить її в `Thread.CurrentCulture` на запит), а не мову інтерфейсу:

| Профіль: Date and time format | Відповідь сервісу |
|---|---|
| Ukrainian (Ukraine) | `22.12.2018 21:17:24` |
| English (United States) | `12/22/2018 9:17:24 PM` |

На фронті та сама культура доступна як **`Terrasoft.Resources.CultureSettings`** — аналог `UserConnection.CurrentUser.DateTimeFormat` (формує `Terrasoft.Web.Common.dll` з `ShortDatePattern/ShortTimePattern`, вписується інлайн у сторінку):

| Поле | uk-UA | en-US |
|---|---|---|
| `dateFormat` (нотація `Ext.Date`) | `"d.m.Y"` | `"m/d/Y"` |
| `timeFormat` | `"G:i"` | `"g:i A"` |
| `decimalSeparator` / `thousandSeparator` / `dateSeparator` | `","` / `" "` / `"."` | `"."` / `","` / `"/"` |
| `currentCultureId`, `currentCultureName`, `startDay`, `shortDayNames`, `monthNames`, `numberGroupSizes`, `isRightToLeft` | | |

Не плутати з `Terrasoft.SysValue.CURRENT_USER_CULTURE` — це **мова** (Language). `getLocaleDateTimeFormat` з бандлів `CrtNUI/…/mf/*.js` — це `@angular/common`, до профілю Creatio стосунку не має і з класичного AMD-модуля недоступна.

Нюанси: `timeFormat` короткий (без секунд), а `ToString()` дає довгий (`21:17:24`); en-US віддає день/місяць без ведучих нулів (`6/8/2026`), а `Ext.Date.parse` строгий до кількості цифр. Тому з `dateFormat` беремо лише **порядок** день/місяць/рік, цифри — регекспом.

## Виправлення — `Schemas/SqlConsoleModule/SqlConsoleModule.js`

**1. `showQueryResult` → опції `DataTable({...})`** (після `scrollCollapse: false,`):

```js
order: [],   // не пересортовувати на клієнті — зберігати ORDER BY з БД
```

**2. Після `formDataTableColumns` (перед `return Ext.define(...)`):**

```js
var NULL_VALUE = "NULL";
var DATE_RE = /^\d{1,4}[.\/-]\d{1,2}[.\/-]\d{1,4}(?: \d{1,2}:\d{2}(?::\d{2})?(?: ?[AP]M)?)?$/i;
var NUMBER_RE = /^-?\d+(?:[.,]\d+)?$/;

/** DateTime.ToString() за культурою користувача → timestamp або NaN.
 *  Порядок д/м/р — з CultureSettings.dateFormat (d.m.Y, n/j/Y, ...), цифри — регекспом. */
var parseServerDate = function(value) {
	var parts = value.match(/\d+/g);
	if (!parts || parts.length < 3) {
		return NaN;
	}
	var order = Terrasoft.Resources.CultureSettings.dateFormat.replace(/[^djmnYy]/g, "");
	var dayIdx = order.search(/[dj]/), monthIdx = order.search(/[mn]/), yearIdx = order.search(/[Yy]/);
	if (dayIdx < 0 || monthIdx < 0 || yearIdx < 0) {
		return NaN;
	}
	var year = +parts[yearIdx];
	if (year < 100) { year += 2000; }
	var hours = +(parts[3] || 0);
	if (/PM/i.test(value) && hours < 12) { hours += 12; }
	if (/AM/i.test(value) && hours === 12) { hours = 0; }
	return new Date(year, +parts[monthIdx] - 1, +parts[dayIdx], hours, +(parts[4] || 0), +(parts[5] || 0)).getTime();
};

var parseServerNumber = function(value) {
	var normalized = value.replace(Terrasoft.Resources.CultureSettings.decimalSeparator, ".");
	return /^-?\d+(?:\.\d+)?$/.test(normalized) ? parseFloat(normalized) : NaN;
};

/** Типи колонок "sql-date" / "sql-num": "NULL" не ламає автовизначення, сортування за значенням.
 *  NULL → -Infinity (перший при asc). */
var registerSortTypes = function() {
	var ext = $.fn.dataTable.ext;
	if (ext.type.order["sql-date-pre"]) {
		return;
	}
	var isNull = function(d) {
		return d === NULL_VALUE || d === "" || d === null;
	};
	// детектори перебираються по порядку; свої ставимо перед вбудованими
	ext.type.detect.unshift(function(d) {
		if (isNull(d)) { return "sql-date"; }
		return typeof d === "string" && DATE_RE.test(d) && !isNaN(parseServerDate(d)) ? "sql-date" : null;
	});
	ext.type.detect.unshift(function(d) {
		if (isNull(d)) { return "sql-num"; }
		return typeof d === "string" && NUMBER_RE.test(d) && !isNaN(parseServerNumber(d)) ? "sql-num" : null;
	});
	ext.type.order["sql-date-pre"] = function(d) {
		var t = typeof d === "string" ? parseServerDate(d) : NaN;
		return isNaN(t) ? -Infinity : t;
	};
	ext.type.order["sql-num-pre"] = function(d) {
		var n = typeof d === "string" ? parseServerNumber(d) : NaN;
		return isNaN(n) ? -Infinity : n;
	};
};
```

**3. `initDataTables`:**

```js
initDataTables: function() {
	var dataTables = require('JQueryDataTables');
	$ = dataTables.$;
	registerSortTypes();
},
```

Відображення й «Export to CSV» не змінюються — змінюється лише те, за чим DataTables порівнює комірки. Колонка з самих `NULL` отримає тип `sql-num` — на порядок не впливає.

## «Show query log» падає на PostgreSQL - SqlConsoleService.cs

Кнопка **Show query log** → `SqlConsoleService/GetSqlConsoleLog` повертає:

```
Npgsql.PostgresException: 42601: синтаксична помилка в або поблизу "["
POSITION: 19
```

**Причина.** `GetSqlConsoleLog` — єдине місце в сервісі з «сирим» SQL, і він у діалекті MSSQL (`Schemas/SqlConsoleService/SqlConsoleService.cs:36`):

```csharp
string sqlScript = "SELECT TOP (1000) [CreatedOn], [ContactId], [IpAdress], [QueryText], [CompletedOn] FROM [SqlConsoleLog] ORDER BY [CreatedOn] DESC";
```

PostgreSQL не знає ні `TOP (n)`, ні `[квадратних дужок]` (позиція 19 = перша `[`). Запис у лог (`LogQuery` / `UpdateLogQuery`) зроблено через `Insert`/`Update`-білдери Terrasoft, тому він працює; ламається лише читання.

**Виправлення.** Замінити сирий рядок на `Select`-білдер — він генерує SQL під поточну СУБД (`TOP 1000 [..]` для MSSQL, `".." … LIMIT 1000` для PostgreSQL); далі текст іде тим самим шляхом через `ExecuteSqlScript(sql, false)`, тож рендер таблиці й обробка помилок не змінюються:

```csharp
public ExecuteSqlResult GetSqlConsoleLog() {
	var userConnection = (UserConnection)HttpContext.Current.Session["UserConnection"];
	var select = new Select(userConnection).Top(1000)
			.Column("CreatedOn")
			.Column("ContactId")
			.Column("IpAdress")
			.Column("QueryText")
			.Column("CompletedOn")
		.From("SqlConsoleLog")
		.OrderByDesc("CreatedOn") as Select;
	ExecuteSqlResult result = ExecuteSqlScript(select.GetSqlText(), false);
	return result;
}
```

`Select.GetSqlText()` віддає готовий текст із екранованими ідентифікаторами; параметрів у запиті немає. `using Terrasoft.Core.DB;` у файлі вже є.

**Доставка.** Це схема `SqlConsoleService` (SourceCode), а не `Files/` — зберегти в дизайнері → **Compile** пакета. Кеш браузера тут не задіяний (серверний код).

[[SqlConsoleModule]].md (js file)
[[SqlConsoleService]].md (cs file)



