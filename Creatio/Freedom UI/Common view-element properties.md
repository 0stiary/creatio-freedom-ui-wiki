---
tags: [creatio, freedom-ui, reference]
generated: 2026-09-16
---
# Спільні властивості всіх view-елементів Freedom UI

Джерело: код Shell Creatio 8.3.4.2753 (базовий клас view-елемента, компілятор view-конфігу, директива `crtIf`, препроцесори).

## Обов'язкові ключі елемента у `viewConfigDiff`

```json
{
  "operation": "insert",            // insert | merge | remove | move
  "name": "MyElement_abc1234",       // унікальне ім'я
  "values": { "type": "crt.Button", ... },
  "parentName": "GridContainer_x",  // куди вставити
  "propertyName": "items",           // у який слот батька: items | tools | menuItems | listActions | bulkActions | rowToolbarItems | template | placeholder
  "index": 0
}
```
`remove` може мати `properties: ["layoutConfig"]` — видалити лише окремі властивості. `move` = `name + parentName + propertyName + index`.

## Базові inputs (є у кожного компонента)

| Властивість | Опис |
|---|---|
| `name` | ім'я; рендериться як атрибут `element-name`; за ним працює `for`, `viewName`, `viewElementName` у запитах |
| `id` | DOM id |
| `tabIndex` | порядок фокуса |
| `classes` | масив CSS-класів → `[ngClass]`; можна біндити: `"classes": "$Items.X \| usr.ClassesConverter"` |
| `styles` | об'єкт стилів → `[ngStyle]`; CSS-змінні (`--crt-…`) підтримуються |
| `shape` | `rounded` |
| `loading` | показати skeleton/спінер |

## Хто реально рендерить `classes` і `styles`

`classes`/`styles` — inputs **базового класу** (`set classes(p){this._classes = p || []}`, `getClasses()`), тому конфіг з ними валідний для будь-якого елемента. Але в DOM вони потрапляють лише там, де шаблон компонента використовує `getClasses()`/`classMap(hostClasses)`/`[ngClass]="classes"`. Перевірено по шаблонах Shell 8.3.4.2753:

| Стан | Елементи |
|---|---|
| ✅ `classes` рендериться **на host-елемент** (`<crt-flex class="…">`) | `crt.FlexContainer`, `crt.GridContainer` (через `hostClasses`, коли не `useOldTemplate`) |
| ✅ `classes` рендериться на внутрішній елемент | `crt.Button` (на `<button>`), `crt.ExpansionPanel`, `crt.DataGrid`, `crt.FileList`, `crt.TemplateList` (зовнішній `div`), `crt.ToggleContainer`/`crt.ToggleContainerItem` (сюди ж потрапляють `classes` з `crt.TabPanel` у toggle-режимі), `crt.FolderTree`, `crt.NavigationPanel`, `crt.HeaderContainer`, `crt.EmailInput`, `crt.WebInput`, `crt.EncryptedInput`, `crt.List`/`crt.FilterableList`/`crt.ComponentList`, `crt.ChatItem`, `crt.TranslateToggle`/`crt.AutoTranslateToggle`, `crt.DeprecatedLabel` |
| ⚠️ ймовірно (компонент у спільному модулі — перевірте в DOM) | `crt.TagSelect`, `crt.FileInput`, `crt.PasswordInput`, `crt.AppToolbar`, `crt.AppBackground`, `crt.NavigationPanelItem`, `crt.ItemWrapper`, `crt.MultiList`, `crt.ObjectExplorer`, `crt.OperatorState`, `crt.Playbook`, `crt.ArticlesList`, `crt.AllowedResults`, `crt.DeprecatedInput` |
| ❌ **ігнорують** `classes` | усе інше — зокрема `crt.Label`, `crt.Input`, `crt.NumberInput`, `crt.DateTimePicker`, `crt.Checkbox`, `crt.ComboBox`, `crt.Link`, `crt.MenuItem`, `crt.TabContainer`, `crt.TabPanel` (у tab-режимі), `crt.QuickFilter`, `crt.SearchFilter`, `crt.Placeholder`, `crt.Summaries`, усі `Table*Cell` |
| ✅ `styles` рендериться | `crt.FlexContainer`, `crt.GridContainer` (host `styleMap`), `crt.DataGrid`, `crt.HeaderContainer`, `crt.EncryptedInput`, `crt.List`/`crt.FilterableList`/`crt.ComponentList`, `crt.DeprecatedLabel` |

Правила:
- `classes` має бути **масивом** (`["my-class"]`). Рядок не впаде з помилкою, але контейнери роблять `[...super.getClasses()]` — рядок розкладеться на окремі символи-класи.
- Якщо елемент ігнорує `classes` — обгорніть його в `crt.FlexContainer` з `classes` і пишіть CSS через нащадка: `.my-wrap crt-label .crt-label { color: red }`. Для `crt.Label` є ще `labelStyle` (об'єкт → `[ngStyle]`), `labelColor`, `labelBackgroundColor`, `labelFontSize`, `labelTextAlign`, `labelTextTransform`.
- Для полів вводу (`crt.Input`, `crt.ComboBox`, …) класи задаються лише через обгортку; `appearance` (`legacy`/`outline`) та `labelPosition` — єдині стильові inputs.
- `classes` можна біндити з конвертером (`"classes": "$Items.X | usr.Conv"`) — конвертер має повертати масив.

## `visible` та `visibilityStrategyMode`

`visible` (true/false/біндінг) **не є input компонента** — компілятор загортає елемент у структурну директиву `*crtIf`. Режими (`visibilityStrategyMode` на тому ж елементі):

| Режим | Поведінка |
|---|---|
| `"destroy"` (default) | `viewContainer.clear()` — DOM і Angular-компонент знищуються; при `visible=true` створюються заново (усі внутрішні стани, DOM-стилі, скрол — втрачені; події зміни атрибутів **не** повторюються) |
| `"hide"` | елемент лишається в DOM, ховається класом; **працює лише якщо увімкнена фіча `UseHideVisibilityStrategy`** (інакше мовчки `destroy`) |

Приклад з ядра (схема `MainShell`): `LeftNavigationPanel`, `LeftPanelContainer` та права toggle-панель Shell мають `visibilityStrategyMode: "hide"`.

Для `crt.TabPanel` у toggle-режимі з `ButtonToggleGroup` препроцесор сам ставить `visible: "$<Name>_SelectedItem | crt.ToBoolean"`, тому закриття панелі = destroy.

## `layoutConfig`

- Дитина `crt.GridContainer`: `{ "column": 1, "row": 1, "colSpan": 1, "rowSpan": 1 }` (1-based).
- Дитина `crt.FlexContainer`: `{ "width": 328, "minWidth": 400, "maxWidth": 550, "basis": "100%", "grow": 1 }`.
Компілюється в атрибути `layout-config-*` елемента.

## Слоти (`contentSlots`)

Властивість-масив, у яку кладуть інші view-елементи: `items` (контейнери, вкладки), `tools` (хедер ExpansionPanel/TabContainer/Timeline), `menuItems` (Button), `listActions`/`controlActions` (ComboBox), `rowToolbarItems`/`bulkActions`/`headerToolbarItems`/`placeholder` (DataGrid), `template` (TemplateList), `customFilters` (Timeline). Lazy-слоти рендеряться при першому показі.

## Біндінги

| Синтаксис | Значення |
|---|---|
| `"$Attr"` | значення атрибута view-моделі |
| `"$Collection.Attr"` | атрибут елемента колекції (у `template`/`columns`/`rowToolbarItems`) |
| `"$Attr \| crt.Conv : 'arg' : $Other"` | конвертер; сигнатура `convert(value, $context, ...args)` |
| `"#ResourceString(Key)#"` | локалізований рядок схеми |
| `"$Resources.Strings.Key"` | те саме як біндінг (лейбли полів) |
| `"#MacrosTemplateString(...)#"` | рядок з макросами |
| `"#PrimaryDataSourceName()#"`, `"#DataSourceEntityName()#"` | ім'я головного DS / його об'єкта |
| `"[#currentUserContact#]"`, `"[#currentMonth#]"` | макроси значень у фільтрах |
| `"@event.detail"`, `"@event"` | payload події у `params` запиту |
| `"bindTo": "Attr"` | масове зв'язування inputs з полів об'єкта-атрибута |

## Події → запити

Будь-який `@Output` компонента (`clicked`, `valueChange`, `rowDoubleClick`, `upload`…) у конфігу описується як
```json
"clicked": { "request": "crt.RunBusinessProcessRequest", "params": { "processName": "X", "processParameters": {"Id": "$Id"} }, "useRelativeContext": true }
```
`useRelativeContext: true` — `$context` запиту = view-модель елемента (рядок гріда/списку), інакше — сторінка. Обробники: `handlers: [{ request: "crt.XRequest", handler: async (request, next) => { ...; return next?.handle(request); } }]`.

## Службові властивості дизайнера (не впливають на рантайм)

`_designOptions` (крім `DataGrid.columns.cellViews/editingCellViews/designSettings`, `Dashboards`, `Summaries`, `SummaryItem` — там читаються препроцесорами), `defaultLocalizableStrings`, `selected`, `sealed`, `dragging`, `dataItemMarker`, `_d`.

## Фічі (Feature toggles), що змінюють поведінку елементів

`UseHideVisibilityStrategy`, `DisableTabPanelPreprocessing`, `DisableSaveToProfileSelectedTabIndex`, `DisableSaveToProfileToggleGroupSelectedTab`, `DisableSaveToProfileExpPanelExpanded`, `UseSchemaOutletReuseViewStrategy`, `UseReuseViewStrategyBindingActivator`.
