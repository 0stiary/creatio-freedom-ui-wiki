---
type: crt.MultiSelect
selector: crt-multi-select
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.MultiSelect

> Мультивибір записів зв'язку M:N.

Angular-селектор: `<crt-multi-select>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `disabled` | `false` |  |  |
| `enableAddRecord` | `false` |  |  |
| `isModalView` | `false` |  |  |
| `items` |  |  |  |
| `label` | `""` | `<binding>` |  |
| `labelPosition` | `""` | `"auto"`, `"above"` |  |
| `listItems` |  |  |  |
| `placeholder` | `""` | `""` |  |
| `readonly` |  |  |  |
| `required` | `false` | `false` |  |
| `tooltip` | `""` | `""` |  |
| `wrap` | `false` |  |  |

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

| Властивість | Значення | Що робить |
|---|---|---|
| `recordId` | `<binding>` | **прихована**: `$Id` |
| `recordRelationColumnName` | `"UsrAccountProduct"` | **прихована**: колонка зв'язку |
| `selectSchemaName` | `"UsrAccountProductContact"` | **прихована**: об'єкт-зв'язка |
| `selectColumnName` | `"UsrContact"` | **прихована**: колонка вибраного значення |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `layoutConfig.colSpan` | `1` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `1` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:75,icon:c(6010),defaultPropertyValues:{label:""},defaultLocalizableStrings:{label:"Components.MultiSelect.Label"}},designViewItemCommands:{copy:"crt.CopyMultiSelectViewItemCommand",rename:"crt.RenameMultiSelectViewItemCommand",delete:"crt.RemoveMultiSelectViewItemCommand"},propertiesPanelComponentTypeName:"crt.MultiSelectPropertiesPanel",typeCaption:"Components.MultiSelect.Caption",viewElementGroupType:G.J.Components,placeholderSize:{height:"18px"}}
```

## Приклад з реальної схеми


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

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.MultiSelect** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.MultiSelect** (власні) | `disabled`, `enableAddRecord`, `isModalView`, `items`, `label`, `labelPosition`, `listItems`, `placeholder`, `readonly`, `required`, `tooltip`, `wrap` | `createRecord`, `deleteSelectedItems`, `paginationChange`, `selectedItemsChange`, `showList` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (6981.hash=17627d4046752ff7.js) + 32 згадок у конфігах. Мінімізовані імена класів не наводяться.*