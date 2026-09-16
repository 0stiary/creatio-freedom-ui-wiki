---
type: crt.CommunicationOptions
selector: crt-communication-options
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.CommunicationOptions

> Засоби зв'язку контакта/контрагента (телефони, email, соцмережі).

Angular-селектор: `<crt-communication-options>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `templates`  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `columnsCount` |  | `1`, `2` |  |
| `defaultOptionConfig` |  |  |  |
| `displayFormatColumnName` |  |  |  |
| `items` |  | `<binding>` |  |
| `labelPosition` | `"auto"` | `"above"`, `"auto"` |  |
| `masterRecordColumnName` |  | `"Contact"`, `"Account"` |  |
| `masterRecordColumnValue` |  | `<binding>` |  |
| `numberColumnName` |  |  |  |
| `optionActions` |  |  |  |
| `primaryColumnName` |  |  |  |
| `readonly` |  | `false`, `true` |  |
| `showNoDataPlaceholder` | `true` | `false`, `true` |  |
| `templates` |  |  |  |
| `typeColumnName` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `layoutConfig.colSpan` | `2` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `1` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Приклад з реальної схеми


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

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.CommunicationOptions** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.CommunicationOptions** (власні) | `columnsCount`, `defaultOptionConfig`, `displayFormatColumnName`, `items`, `labelPosition`, `masterRecordColumnName`, `masterRecordColumnValue`, `numberColumnName`, `optionActions`, `primaryColumnName`, `readonly`, `showNoDataPlaceholder`, `templates`, `typeColumnName` | — |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7262.hash=da34f3680bc7571c.js) + 86 згадок у конфігах. Мінімізовані імена класів не наводяться.*