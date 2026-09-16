---
type: crt.NumberInput
selector: crt-number-input
group: "Поля вводу"
usage_in_configs: 112
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.NumberInput

> Числове поле.

Angular-селектор: `<crt-number-input>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **112** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `format` |  |  | 1 | формат (кількість знаків береться з `dataValueType` колонки: Float1..Float8, Money, Integer) |
| `autocomplete` | `"none"` |  |  | (успадковано від базового класу) |
| `autofocus` | `false` |  |  | (успадковано від базового класу) |
| `readonly` | `false` | `true`, `false` | 97 | (успадковано від базового класу) |
| `value` |  |  |  | (успадковано від базового класу) |
| `appearance` | `"legacy"` | `legacy` |  | (успадковано від базового класу) |
| `ariaLabel` | `""` |  |  | (успадковано від базового класу) |
| `control` |  | `<binding>` | 112 | (успадковано від базового класу) |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `label` | `""` | `<binding>`, `"#ResourceString(Budget_label)#"` | 112 | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"` | 112 | (успадковано від базового класу) |
| `placeholder` |  | `""` | 101 | (успадковано від базового класу) |
| `tooltip` |  | `""`, `<binding>`, `"#ResourceString(Budget_tooltip)#"` | 101 | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `blurred` |  |  |
| `focused` |  |  |
| `keyDown` |  |  |
| `keyUp` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 85 |  | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 58 | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |
| `format.decimalPrecision` | 1 | `6` |  |
| `layoutConfig.colSpan` | 85 | `1` |  |
| `layoutConfig.column` | 85 | `1`, `2`, `3`, `4` |  |
| `layoutConfig.row` | 85 | `1`, `2`, `3`, `4`, `5`, `8` |  |
| `layoutConfig.rowSpan` | 85 | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:30,icon:t(48387),defaultPropertyValues:{label:"",control:"",readonly:false,placeholder:"",labelPosition:"auto",tooltip:""},defaultLocalizableStrings:{label:"Components.NumberInput.Caption"}},dataValueTypes:J,propertiesPanelComponentTypeName:"crt.InputPropertiesPanelComponent",viewElementGroupType:c.J.Inputs,typeCaption:"Components.NumberInput.Caption"}
```

## Приклад з реальної схеми

Джерело: `UsrPendingLines_FormPage.js`

```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 12,
						"rowSpan": 1
					},
					"type": "crt.NumberInput",
					"label": "$Resources.Strings.PageParameters_UsrIntegerParameter1_1kquzvq",
					"control": "$PageParameters_UsrIntegerParameter1_1kquzvq",
					"readonly": true,
					"placeholder": "",
					"labelPosition": "auto",
					"tooltip": "",
					"visible": true
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 780 згадок у конфігах. Мінімізовані імена класів не наводяться.*