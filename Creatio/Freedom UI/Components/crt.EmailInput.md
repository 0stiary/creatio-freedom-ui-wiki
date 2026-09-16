---
type: crt.EmailInput
selector: crt-email-input
group: "Поля вводу"
usage_in_configs: 1
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.EmailInput

Angular-селектор: `<crt-email-input>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `tools`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **1** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `isFormatValidated` | `true` |  |  |  |
| `displayTools` |  |  |  | (успадковано від базового класу) |
| `inputType` | `"text"` |  |  | (успадковано від базового класу) |
| `mask` |  |  |  | (успадковано від базового класу) |
| `multiline` | `false` |  |  | (успадковано від базового класу) |
| `autocomplete` | `"none"` |  |  | (успадковано від базового класу) |
| `autofocus` | `false` |  |  | (успадковано від базового класу) |
| `readonly` | `false` |  |  | (успадковано від базового класу) |
| `value` |  |  |  | (успадковано від базового класу) |
| `appearance` | `"legacy"` | `legacy`, `outline` |  | (успадковано від базового класу) |
| `ariaLabel` | `""` |  |  | (успадковано від базового класу) |
| `control` |  | `<binding>` | 1 | (успадковано від базового класу) |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `label` | `""` | `"Email"` | 1 | (успадковано від базового класу) |
| `labelPosition` |  | `"above"` | 1 | (успадковано від базового класу) |
| `placeholder` |  | `""` | 1 | (успадковано від базового класу) |
| `tooltip` |  | `""` | 1 | (успадковано від базового класу) |

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
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |
| `visible` | 1 | `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{groupType:d.h.Inputs,position:43,icon:t(73635),defaultPropertyValues:{label:"",control:"",labelPosition:"auto",placeholder:"",tooltip:"",needHandleSave:false},defaultLocalizableStrings:{caption:"DataValueType.EmailTextCaption",label:"DataValueType.EmailTextCaption"}},dataValueTypes:[p.r.EMAIL_TEXT],propertiesPanelComponentTypeName:"crt.PhoneTextPropertiesPanel",viewElementGroupType:r.J.Inputs,typeCaption:"DataValueType.EmailTextShortenedCaption"}
```

## Приклад з реальної схеми

Джерело: `7262.hash=da34f3680bc7571c.js`

```json
{type:"crt.EmailInput",label:"Email",labelPosition:"above",control:"$Email",visible:true,placeholder:"",tooltip:"",name:"Email"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 8 згадок у конфігах. Мінімізовані імена класів не наводяться.*