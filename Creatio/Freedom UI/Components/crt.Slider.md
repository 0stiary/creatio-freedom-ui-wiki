---
type: crt.Slider
selector: crt-slider
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Slider

Angular-селектор: `<crt-slider>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `ariaLabel` |  |  | (успадковано від базового класу) |
| `color` |  | `"primary"` | (успадковано від базового класу) |
| `control` |  | `<binding>` | (успадковано від базового класу) |
| `disableResizing` | `false` |  | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `height` | `16` |  | (успадковано від базового класу) |
| `hideLabels` | `false` |  | (успадковано від базового класу) |
| `hideThumb` |  |  | (успадковано від базового класу) |
| `label` | `"Slider"` | `<binding>` | (успадковано від базового класу) |
| `maxValue` |  | `4` | (успадковано від базового класу) |
| `minValue` |  | `1` | (успадковано від базового класу) |
| `paddingLineMode` |  |  | (успадковано від базового класу) |
| `readonly` |  | `false` | (успадковано від базового класу) |
| `step` |  | `1` | (успадковано від базового класу) |
| `value` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `valueChanged` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `labelPosition` | `null` |  |
| `placeholder` | `""` |  |
| `tooltip` | `""` |  |
| `formControlConfig` |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `formControlConfig.relatesTo` | `"control"` |  |
| `layoutConfig.colSpan` | `1` |  |
| `layoutConfig.column` | `2` |  |
| `layoutConfig.row` | `2` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Приклад з реальної схеми


```json
{layoutConfig:{column:2,colSpan:1,row:2,rowSpan:1},type:"crt.Slider",color:"primary",minValue:1,maxValue:4,step:1,label:"$Resources.Strings.PDS_UsrDurationHours_1t4a0xh",visible:true,readonly:false,labelPosition:null,placeholder:"",tooltip:"",control:"$PDS_UsrDurationHours_1t4a0xh"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 13 згадок у конфігах. Мінімізовані імена класів не наводяться.*