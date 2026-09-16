---
type: crt.CommunicationOptions
selector: crt-communication-options
group: "Поля вводу"
usage_in_configs: 10
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.CommunicationOptions

> Засоби зв'язку контакта/контрагента (телефони, email, соцмережі).

Angular-селектор: `<crt-communication-options>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `templates`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **10** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `columnsCount` |  | `1`, `2` | 10 |  |
| `defaultOptionConfig` |  |  |  |  |
| `displayFormatColumnName` |  |  |  |  |
| `items` |  | `<binding>` | 9 |  |
| `labelPosition` | `"auto"` | `"above"`, `"auto"` | 10 |  |
| `masterRecordColumnName` |  | `"Contact"`, `"Account"` | 9 |  |
| `masterRecordColumnValue` |  | `<binding>` | 9 |  |
| `numberColumnName` |  |  |  |  |
| `optionActions` |  |  |  |  |
| `primaryColumnName` |  |  | 2 |  |
| `readonly` |  | `false`, `true` | 10 |  |
| `showNoDataPlaceholder` | `true` | `false`, `true` | 10 |  |
| `templates` |  |  |  |  |
| `typeColumnName` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 10 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 6 | `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `layoutConfig.colSpan` | 3 | `2` |  |
| `layoutConfig.column` | 3 | `1` |  |
| `layoutConfig.row` | 3 | `1` |  |
| `layoutConfig.rowSpan` | 3 | `1` |  |

## Приклад з реальної схеми

Джерело: `Contacts_FormPage.js`

```json
{
					"type": "crt.CommunicationOptions",
					"readonly": false,
					"columnsCount": 2,
					"showNoDataPlaceholder": true,
					"labelPosition": "auto",
					"layoutConfig": {
						"colSpan": 2,
						"column": 1,
						"row": 1,
						"rowSpan": 1
					},
					"masterRecordColumnValue": "$Id",
					"masterRecordColumnName": "Contact",
					"items": "$CommunicationOptions_i77g6gv"
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7262.hash=da34f3680bc7571c.js) + 86 згадок у конфігах. Мінімізовані імена класів не наводяться.*