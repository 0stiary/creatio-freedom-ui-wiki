---
type: crt.ImageInput
selector: crt-image-input
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ImageInput

> Поле зображення (аватар).

Angular-селектор: `<crt-image-input>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `alt` |  |  | (успадковано від базового класу) |
| `borderRadius` |  | `string` · `"medium"`, `"none"`, `"small"` | (успадковано від базового класу) |
| `colorId` |  |  | (успадковано від базового класу) |
| `customBorderWidth` |  |  | (успадковано від базового класу) |
| `customHeight` |  | `"16px"` | (успадковано від базового класу) |
| `customWidth` |  | `"16px"` | (успадковано від базового класу) |
| `isFocused` | `false` |  | (успадковано від базового класу) |
| `maxFileSize` |  |  | (успадковано від базового класу) |
| `placeholder` |  | `""` | (успадковано від базового класу) |
| `placeholderMode` |  |  | режим заглушки |
| `positioning` |  | `"cover"`, `"scale-down"` | (успадковано від базового класу) |
| `size` |  | `"extra-small"`, `"large"` | розмір |
| `value` |  | `<binding>` | біндінг; препроцесор додає конвертер `crt.ToImageLink`, запити вибору/очищення та бізнес-правила readonly |
| `valueValidationInfo` |  |  | (успадковано від базового класу) |
| `displayTools` |  |  | (успадковано від базового класу) |
| `inputType` | `"text"` |  | (успадковано від базового класу) |
| `mask` |  |  | (успадковано від базового класу) |
| `multiline` | `false` |  | (успадковано від базового класу) |
| `autocomplete` | `"none"` |  | (успадковано від базового класу) |
| `autofocus` | `false` |  | (успадковано від базового класу) |
| `readonly` | `false` | `true` | (успадковано від базового класу) |
| `appearance` | `"legacy"` | `legacy`, `outline` | (успадковано від базового класу) |
| `ariaLabel` | `""` |  | (успадковано від базового класу) |
| `control` |  |  | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `label` | `""` | `""`, `<binding>` | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"` | (успадковано від базового класу) |
| `tooltip` |  | `""` | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `imageClear` |  |  |
| `imageSelected` |  |  |
| `blurred` |  |  |
| `focused` |  |  |
| `keyDown` |  |  |
| `keyUp` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `valuePropertyName` | `"value"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `layoutConfig.colSpan` | `2` |  |
| `layoutConfig.column` | `6` |  |
| `layoutConfig.row` | `1` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{...D,icon:t(70285)},...I,propertiesPanelComponentTypeName:"crt.ImageInputPropertiesPanelComponent"}
```

## Приклад з реальної схеми


```json
{type:"crt.ImageInput",label:"$Resources.Strings.null",value:"https://d3a7ykdi65m4cy.cloudfront.net/ac-en/s3fs-public/images/Demo/No-access-meet-summary.svg",readonly:true,placeholder:"",labelPosition:"auto",size:"large",borderRadius:"none",positioning:"scale-down",visible:true,tooltip:"",layoutConfig:{column:6,colSpan:2,row:1,rowSpan:1}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 165 згадок у конфігах. Мінімізовані імена класів не наводяться.*