---
type: crt.WebInput
selector: crt-web-input
group: "Поля вводу"
usage_in_configs: 5
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.WebInput

Angular-селектор: `<crt-web-input>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `tools`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **5** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `icon` |  | `"google-web-icon"`, `"facebook-web-icon"`, `"linkedin-web-icon"`, `"twitter-web-icon"`, `"skype-web-icon"` | 5 |  |
| `displayTools` |  |  |  | (успадковано від базового класу) |
| `inputType` | `"text"` |  |  | (успадковано від базового класу) |
| `mask` |  |  |  | (успадковано від базового класу) |
| `multiline` | `false` |  |  | (успадковано від базового класу) |
| `autocomplete` | `"none"` |  |  | (успадковано від базового класу) |
| `autofocus` | `false` |  |  | (успадковано від базового класу) |
| `readonly` | `false` | `true` | 2 | (успадковано від базового класу) |
| `value` |  |  |  | (успадковано від базового класу) |
| `appearance` | `"legacy"` | `legacy`, `outline` |  | (успадковано від базового класу) |
| `ariaLabel` | `""` |  |  | (успадковано від базового класу) |
| `control` |  | `<binding>` | 3 | (успадковано від базового класу) |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `label` | `""` | `<binding>`, `"Web"` | 3 | (успадковано від базового класу) |
| `labelPosition` |  | `"above"` | 3 | (успадковано від базового класу) |
| `placeholder` |  | `""` | 3 | (успадковано від базового класу) |
| `tooltip` |  | `""` | 3 | (успадковано від базового класу) |

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
| `visible` | 3 | `true` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` | 2 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{groupType:_.h.Inputs,position:44,icon:t(89474),defaultPropertyValues:{label:"",control:"",labelPosition:"auto",placeholder:"",tooltip:"",needHandleSave:false},defaultLocalizableStrings:{caption:"DataValueType.WebTextCaption",label:"DataValueType.WebTextCaption"}},dataValueTypes:[i.r.WEB_TEXT],propertiesPanelComponentTypeName:"crt.WebTextPropertiesPanel",viewElementGroupType:s.J.Inputs,typeCaption:"DataValueType.WebTextCaption"}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_0.js.завантаження`

```json
{layoutConfig:{},type:"crt.WebInput",label:"$Resources.Strings.AccountWeb",labelPosition:"above",control:"$AccountWeb",readonly:true,visible:true,placeholder:"",tooltip:""}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 29 згадок у конфігах. Мінімізовані імена класів не наводяться.*