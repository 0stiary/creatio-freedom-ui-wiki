---
type: crt.Checkbox
selector: crt-checkbox
group: "Поля вводу"
usage_in_configs: 97
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Checkbox

> Прапорець.

Angular-селектор: `<crt-checkbox>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **97** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `ariaLabel` | `""` | `""`, `<binding>` | 86 | (успадковано від базового класу) |
| `disabled` |  | `false` | 86 | (успадковано від базового класу) |
| `indeterminate` |  |  |  | третій стан |
| `inversed` | `false` | `false` | 86 | інвертоване значення |
| `multilineLabel` |  |  |  | (успадковано від базового класу) |
| `readonly` |  | `false`, `true` | 24 | (успадковано від базового класу) |
| `value` |  | `true`, `<binding>` | 86 | статичне значення |
| `appearance` | `"legacy"` | `legacy` |  | (успадковано від базового класу) |
| `control` |  | `<binding>` | 95 | `"$PDS_Bool"` |
| `label` | `""` | `<binding>` | 97 | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"`, `"right"`, `"left"` | 97 | (успадковано від базового класу) |
| `placeholder` |  | `""` | 28 | (успадковано від базового класу) |
| `tooltip` |  | `""` | 93 | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `valueChange` |  |  |
| `blurred` |  |  |
| `focused` |  |  |
| `keyDown` |  |  |
| `keyUp` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 81 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 28 | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |
| `layoutConfig.colSpan` | 77 | `1` |  |
| `layoutConfig.column` | 77 | `1`, `2` |  |
| `layoutConfig.row` | 77 | `1`, `4`, `2`, `3`, `5`, `8` |  |
| `layoutConfig.rowSpan` | 77 | `1` |  |

## Приклад з реальної схеми

Джерело: `UsrBillingLines_FormPage.js`

```json
{
					"layoutConfig": {
						"column": 2,
						"colSpan": 1,
						"row": 1,
						"rowSpan": 1
					},
					"type": "crt.Checkbox",
					"value": true,
					"disabled": false,
					"inversed": false,
					"label": "$Resources.Strings.PDS_UsrTriggerInitialPendingLine_zoyp8ot",
					"ariaLabel": "",
					"labelPosition": "left",
					"tooltip": "",
					"control": "$PDS_UsrTriggerInitialPendingLine_zoyp8ot",
					"visible": true,
					"readonly": false,
					"placeholder": ""
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 888 згадок у конфігах. Мінімізовані імена класів не наводяться.*