---
type: crt.TimelineTile
selector: crt-timeline-tile
group: "Timeline / Feed / Файли"
usage_in_configs: 80
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TimelineTile

> Плитка типу запису у Timeline (описова, не має слотів у конфігу — читає препроцесор).

Angular-селектор: `<crt-timeline-tile>`  
Група: **Timeline / Feed / Файли**  
Слоти вкладених елементів (`contentSlots`): `items`, `filters`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **80** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `entity` |  |  |  |  |
| `tileColumnsConfig` |  |  |  |  |
| `tileEntityConfig` |  |  |  |  |
| `tileViewConfig` |  |  |  |  |
| `updatedEntity` |  |  |  |  |

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `classes` | 80 |  | спільна → [[Common view-element properties#classes]] |
| `sortedByColumn` | 80 | `"CreatedOn"`, `null`, `"SendDate"`, `"RegisteredOn"`, `"StartDate"` | **прихована** |
| `ownerColumn` | 80 | `"CreatedBy"`, `"Owner"`, `"SenderContact"`, `"Contact"` | **прихована** |
| `data` | 80 |  | **прихована**: список колонок для відображення |
| `linkedColumn` | 76 | `"Account"`, `"Contact"`, `"QualifiedAccount"`, `"QualifiedContact"` | **прихована**: колонка зв'язку з майстер-записом |
| `iconId` | 54 | `null` |  |
| `filters` | 50 | `<binding>` | **прихована**: фільтри плитки |
| `iconPosition` | 36 | `"only-icon"` |  |
| `icon` | 36 | `"star-tab-icon"`, `"star-icon"` |  |
| `visible` | 36 | `true` | спільна → [[Common view-element properties#visible]] |
| `isDefault` | 2 | `true` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `data.columns` | 72 |  |  |
| `data.schemaName` | 72 | `"Activity"`, `"Opportunity"`, `"Lead"`, `"Call"`, `"Case"`, `"Order"` |  |
| `data.isDefault` | 66 | `true`, `false` |  |
| `data.schemaType` | 60 | `null`, `"Email"`, `"Activity"`, `"SysFile"`, `"Feed"` |  |
| `data.columns[].columnLayout` | 50 | `null` |  |
| `data.columns[].columnName` | 50 | `"CreatedOn"`, `"Title"`, `"Direction"`, `"Category"` |  |
| `data.filter` | 8 | `null` |  |
| `data.uId` | 8 | `"c449d832-a4cc-4b01-b9d5-8a12c42a9f89"`, `"2f81fa05-11ae-400d-8e07-5ef6a620d1ad"`, `"04184833-0a7d-4c43-a6da-fcd8bdd098c5"` |  |
| `data.columns[].columnLayout.colSpan` | 6 | `12`, `4`, `3` |  |
| `data.columns[].columnLayout.column` | 6 | `1` |  |
| `data.columns[].columnLayout.row` | 6 | `1` |  |
| `data.columns[].columnLayout.rowSpan` | 6 | `1` |  |
| `data.filter.columnName` | 4 | `"Type"` |  |
| `data.filter.columnValue` | 4 | `"e2831dec-cfc0-df11-b00f-001d60e938c6"`, `"fbe0acdc-cfc0-df11-b00f-001d60e938c6"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{propertiesPanelComponentTypeName:"crt.TimelineItemPropertiesPanel",viewElementGroupType:pt.J.CustomElements,typeCaption:"TypeCaptions.TimelineTile"}
```

## Приклад з реальної схеми

Джерело: `Accounts_FormPage.js`

```json
{
					"type": "crt.TimelineTile",
					"classes": [
						"view-element"
					],
					"linkedColumn": "Account",
					"sortedByColumn": null,
					"ownerColumn": "CreatedBy",
					"iconId": null,
					"data": {
						"columns": [
							{
								"columnName": "CreatedOn",
								"columnLayout": null
							},
							{
								"columnName": "Name",
								"columnLayout": null
							},
							{
								"columnName": "Description",
								"columnLayout": "{\"column\": 1,\"row\": 2,\"colSpan\": 12,\"rowSpan\": 1}"
							}
						],
						"schemaName": "AIInsight",
						"schemaType": null,
						"isDefault": true
					},
					"filters": "$TimelineTile_AIInsight_r5qtdo1_Items"
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7910.hash=7aee5aadbf21d80e.js) + 610 згадок у конфігах. Мінімізовані імена класів не наводяться.*