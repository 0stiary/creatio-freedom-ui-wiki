---
type: crt.ColorPicker
selector: crt-color-picker
group: "Поля вводу"
usage_in_configs: 1
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ColorPicker

Angular-селектор: `<crt-color-picker>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **1** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `colors` |  |  |  |  |
| `control` |  |  |  |  |
| `pickerConfig` |  |  |  |  |
| `pickerMode` | `"extended"` | `basic`, `extended` |  |  |
| `selectedColor` |  |  |  |  |
| `appearance` | `"legacy"` | `legacy` |  | (успадковано від базового класу) |
| `ariaLabel` | `""` |  |  | (успадковано від базового класу) |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `label` | `""` |  |  | (успадковано від базового класу) |
| `labelPosition` |  |  |  | (успадковано від базового класу) |
| `placeholder` |  |  |  | (успадковано від базового класу) |
| `tooltip` |  |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `selectedColorChange` |  |  |
| `blurred` |  |  |
| `focused` |  |  |
| `keyDown` |  |  |
| `keyUp` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:50,icon:r(9490),defaultPropertyValues:{label:"",labelPosition:"auto"},defaultLocalizableStrings:{label:"Components.ColorPicker.Caption"}},propertiesPanelComponentTypeName:"crt.ColorPickerPropertiesPanel",dataValueTypes:[X.r.Color],viewElementGroupType:K.J.Inputs,typeCaption:"Components.ColorPicker.Caption"}
```

## Приклад з реальної схеми

Джерело: `2781.hash=639f09a96afbb896.js`

```json
{type:"crt.ColorPicker",formControlConfig:{relatesTo:"control"},reuseStrategy:Y.B.Reuse}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2781.hash=639f09a96afbb896.js) + 1 згадок у конфігах. Мінімізовані імена класів не наводяться.*