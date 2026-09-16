---
type: crt.MultiSelect
selector: crt-multi-select
group: "Поля вводу"
usage_in_configs: 3
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.MultiSelect

> Мультивибір записів зв'язку M:N.

Angular-селектор: `<crt-multi-select>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **3** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `disabled` | `false` |  |  |  |
| `enableAddRecord` | `false` |  |  |  |
| `isModalView` | `false` |  |  |  |
| `items` |  |  |  |  |
| `label` | `""` | `<binding>` | 3 |  |
| `labelPosition` | `""` | `"auto"`, `"above"` | 3 |  |
| `listItems` |  |  |  |  |
| `placeholder` | `""` | `""` | 3 |  |
| `readonly` |  |  |  |  |
| `required` | `false` | `false` | 3 |  |
| `tooltip` | `""` | `""` | 3 |  |
| `wrap` | `false` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `createRecord` |  |  |
| `deleteSelectedItems` |  |  |
| `paginationChange` |  |  |
| `selectedItemsChange` |  |  |
| `showList` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `recordId` | 3 | `<binding>` | **прихована**: `$Id` |
| `recordRelationColumnName` | 3 | `"UsrAccountProduct"` | **прихована**: колонка зв'язку |
| `selectSchemaName` | 3 | `"UsrAccountProductContact"` | **прихована**: об'єкт-зв'язка |
| `selectColumnName` | 3 | `"UsrContact"` | **прихована**: колонка вибраного значення |
| `visible` | 3 | `true` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` | 2 |  | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `layoutConfig.colSpan` | 2 | `1` |  |
| `layoutConfig.column` | 2 | `1` |  |
| `layoutConfig.row` | 2 | `1` |  |
| `layoutConfig.rowSpan` | 2 | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:75,icon:c(6010),defaultPropertyValues:{label:""},defaultLocalizableStrings:{label:"Components.MultiSelect.Label"}},designViewItemCommands:{copy:"crt.CopyMultiSelectViewItemCommand",rename:"crt.RenameMultiSelectViewItemCommand",delete:"crt.RemoveMultiSelectViewItemCommand"},propertiesPanelComponentTypeName:"crt.MultiSelectPropertiesPanel",typeCaption:"Components.MultiSelect.Caption",viewElementGroupType:G.J.Components,placeholderSize:{height:"18px"}}
```

## Приклад з реальної схеми

Джерело: `UsrAccountProducts_FormPage.js`

```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 1,
						"rowSpan": 1
					},
					"type": "crt.MultiSelect",
					"label": "#ResourceString(MultiSelect_4luzhhr_label)#",
					"recordId": "$Id",
					"recordRelationColumnName": "UsrAccountProduct",
					"selectSchemaName": "UsrAccountProductContact",
					"selectColumnName": "UsrContact",
					"visible": true,
					"labelPosition": "auto",
					"placeholder": "",
					"tooltip": "",
					"required": false
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (6981.hash=17627d4046752ff7.js) + 32 згадок у конфігах. Мінімізовані імена класів не наводяться.*