---
type: crt.Checkbox
selector: crt-checkbox
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Checkbox

> Прапорець.

Angular-селектор: `<crt-checkbox>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `ariaLabel` | `""` | `""`, `<binding>` | (успадковано від базового класу) |
| `disabled` |  | `false` | (успадковано від базового класу) |
| `indeterminate` |  |  | третій стан |
| `inversed` | `false` | `false` | інвертоване значення |
| `multilineLabel` |  |  | (успадковано від базового класу) |
| `readonly` |  | `false`, `true` | (успадковано від базового класу) |
| `value` |  | `true`, `<binding>` | статичне значення |
| `appearance` | `"legacy"` | `legacy` | (успадковано від базового класу) |
| `control` |  | `<binding>` | `"$PDS_Bool"` |
| `label` | `""` | `<binding>` | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"`, `"right"`, `"left"` | (успадковано від базового класу) |
| `placeholder` |  | `""` | (успадковано від базового класу) |
| `tooltip` |  | `""` | (успадковано від базового класу) |

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

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `formControlConfig` |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `formControlConfig.relatesTo` | `"control"` |  |
| `layoutConfig.colSpan` | `1` |  |
| `layoutConfig.column` | `1`, `2` |  |
| `layoutConfig.row` | `1`, `4`, `2`, `3`, `5`, `8` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Приклад з реальної схеми


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

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.Checkbox** → *BaseCheckbox* → *BaseFormControl* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.Checkbox** (власні) | — | — |  |
| *BaseCheckbox* | `ariaLabel`, `disabled`, `indeterminate`, `inversed`, `multilineLabel`, `readonly`, `value` | `valueChange` | `value, inversed, readonly, disabled, ariaLabel, indeterminate, multilineLabel`; `valueChange` |
| *BaseFormControl* | `appearance`, `control`, `label`, `labelPosition`, `placeholder`, `tooltip` | `blurred`, `focused`, `keyDown`, `keyUp` | поле форми: `label, ariaLabel, appearance, placeholder, disabled, tooltip, control, labelPosition`; події `keyUp, keyDown, blurred, focused`; зв'язок з FormControl (`_initControl`, required, disabled state) |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 888 згадок у конфігах. Мінімізовані імена класів не наводяться.*