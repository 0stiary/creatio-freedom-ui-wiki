---
type: crt.SearchFilter
selector: crt-search-filter
group: "Фільтри"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.SearchFilter

> Рядок пошуку по колонках гріда.

Angular-селектор: `<crt-search-filter>`  
Група: **Фільтри**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `columnsGroupsConfig` |  |  | групи колонок для випадаючого вибору |
| `disabled` |  |  |  |
| `filteredColumn` |  |  | код колонки, по якій шукати (атрибут `<Name>_SearchFilteredColumn` можна виставити в `HandleViewModelInitRequest`) |
| `iconOnly` |  | `true` | тільки іконка, поле розгортається по кліку (деталі) |
| `instant` | `false` |  | фільтрувати без Enter |
| `minifySearch` |  |  |  |
| `placeholder` | `null` | `<binding>`, `null`, `""` |  |
| `selectedColumnsGroups` |  |  |  |
| `tooltip` |  |  |  |
| `value` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `minifySearchChange` |  |  |
| `selectedColumnsGroupsChange` |  |  |
| `valueChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `_filterOptions` |  | **прихована**: `{ from: ["<Name>_SearchValue", "<Name>_FilteredColumnsGroups"], expose: [{ attribute: "<Name>_<Grid>", converters: [{converter: "crt.SearchFilterAttributeConverter", args: ["<Grid>"]}] }] }` |
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `defaultLocalizableStrings` |  | службове поле дизайнера — ключі локалізації, які підставляються при вставці елемента |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_filterOptions.expose` | `[]` |  |
| `_filterOptions.from` |  |  |
| `_filterOptions.expose[].attribute` | `"AddressSearchFilter_AddressList"`, `"CasesSearchFilter_CasesList"`, `"OrderSearchFilter_OrderList"`, `"LeadSearchFilter_LeadList"`, `"SearchFilter_Items"`, `"CareerSearchFilter_CareerList"` |  |
| `_filterOptions.expose[].converters` |  |  |
| `_filterOptions.expose[].converters[].args` |  |  |
| `_filterOptions.expose[].converters[].converter` | `"crt.SearchFilterAttributeConverter"` |  |
| `defaultLocalizableStrings.placeholder` | `"Components.SearchFilter.Placeholder"` |  |
| `layoutConfig.colSpan` | `1`, `2` |  |
| `layoutConfig.column` | `2`, `1`, `4`, `3` |  |
| `layoutConfig.row` | `1`, `2`, `3`, `4` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:160,icon:t(63849),defaultPropertyValues:{placeholder:""},defaultLocalizableStrings:{placeholder:"Components.SearchFilter.Placeholder"}},designViewItemCommands:{create:"crt.AddFilterViewItemCommand",update:"crt.ChangeFilterViewItemCommand",delete:"crt.RemoveFilterViewItemCommand",copy:"crt.CopyFilterViewItemCommand"},propertiesPanelComponentTypeName:"crt.SearchFilterPropertiesPanel",viewElementGroupType:r.J.Components,typeCaption:"Components.SearchFilter.Caption",placeholderSize:{height:"32px"}}
```

## Приклад з реальної схеми


```json
{
					"layoutConfig": {
						"column": 2,
						"colSpan": 1,
						"row": 2,
						"rowSpan": 1
					},
					"type": "crt.SearchFilter",
					"placeholder": "#ResourceString(SearchFilter_AlternativeName_placeholder)#",
					"_filterOptions": {
						"expose": [
							{
								"attribute": "SearchFilter_AlternativeName_Items",
								"converters": [
									{
										"converter": "crt.SearchFilterAttributeConverter",
										"args": [
											"Items"
										]
									}
								]
							}
						],
						"from": [
							"SearchFilter_AlternativeName_SearchValue",
							"SearchFilter_AlternativeName_FilteredColumnsGroups"
						]
					}
				}
```

## Пов'язані

[[crt.QuickFilter]], [[crt.DataGrid]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 923 згадок у конфігах. Мінімізовані імена класів не наводяться.*