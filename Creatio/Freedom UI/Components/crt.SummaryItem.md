---
type: crt.SummaryItem
selector: crt-summary-item
group: "Списки і дані"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.SummaryItem

> Один підсумок.

Angular-селектор: `<crt-summary-item>`  
Група: **Списки і дані**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `actions` |  |  |  |
| `error` |  |  |  |
| `label` |  | `<binding>` |  |
| `readonly` |  | `true` |  |
| `value` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `_designOptions` |  | **прихована**: `{value: {modelName, expression}}` — вираз агрегації для дизайнера |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_designOptions.value` |  |  |
| `_designOptions.value.attribute` | `"SummaryItem_gv5f1kv_Value"`, `"SummaryItem_cffulzk_Value"`, `"SummaryItem_k7pcl3p_Value"`, `"SummaryItem_rsc3m5r_Value"`, `"SummaryItem_rg3noka_Value"`, `"SummaryItem_2x2xw1r_Value"` |  |
| `_designOptions.value.expression` |  |  |
| `_designOptions.value.modelName` | `"GridDetail_1pq50ekDS"`, `"GridDetail_12go2z3DS"`, `"GridDetail_2ydt4vbDS"`, `"GridDetail_71gu8bkDS"`, `"DataGrid_x3umv3rDS"`, `"DataGrid_xm741rqDS"` |  |
| `_designOptions.value.expression.columns` |  |  |
| `_designOptions.value.expression.function` | `"sum"`, `"count"` |  |
| `_designOptions.value.expression.resultDataValueType` | `4`, `32`, `6` |  |
| `styles.color` | `"#1C9110"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{designControlConfig:{selfSelect:false},designViewItemCommands:{copy:"crt.CopySummaryItemCommand"}}
```

## Приклад з реальної схеми


```json
{
					"type": "crt.SummaryItem",
					"label": "#ResourceString(SummaryItem_gv5f1kv_label)#",
					"_designOptions": {
						"value": {
							"attribute": "SummaryItem_gv5f1kv_Value",
							"modelName": "GridDetail_1pq50ekDS",
							"expression": {
								"columns": [
									{
										"type": "Column",
										"path": "UsrTotalSale"
									}
								],
								"function": "sum",
								"resultDataValueType": 6
							}
						}
					},
					"readonly": true,
					"styles": {
						"color": "#1C9110"
					}
				}
```

## Пов'язані

[[crt.Summaries]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (6553.hash=41ee3da0cd19f881.js) + 125 згадок у конфігах. Мінімізовані імена класів не наводяться.*