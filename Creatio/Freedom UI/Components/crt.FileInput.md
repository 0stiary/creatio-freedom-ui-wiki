---
type: crt.FileInput
selector: crt-file-input
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FileInput

> Поле завантаження файлу в атрибут.

Angular-селектор: `<crt-file-input>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `accept` |  |  | MIME/розширення |
| `maxFileSize` |  |  | байти |
| `displayTools` |  |  | (успадковано від базового класу) |
| `inputType` | `"text"` |  | (успадковано від базового класу) |
| `mask` |  |  | (успадковано від базового класу) |
| `multiline` | `false` |  | (успадковано від базового класу) |
| `autocomplete` | `"none"` |  | (успадковано від базового класу) |
| `autofocus` | `false` |  | (успадковано від базового класу) |
| `readonly` | `false` |  | (успадковано від базового класу) |
| `value` |  |  | (успадковано від базового класу) |
| `appearance` | `"legacy"` | `legacy`, `outline` | (успадковано від базового класу) |
| `ariaLabel` | `""` |  | (успадковано від базового класу) |
| `control` |  |  | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `label` | `""` |  | (успадковано від базового класу) |
| `labelPosition` |  |  | (успадковано від базового класу) |
| `placeholder` |  |  | (успадковано від базового класу) |
| `tooltip` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `cancelUpload` |  |  |
| `delete` |  |  |
| `download` |  | **прихована**: `{request:"crt.DownloadEntityFileRequest"}` |
| `preview` |  |  |
| `upload` |  | **прихована**: препроцесор ставить `{request:"crt.UploadDataAttributeFileRequest", params:{fileAttributeName, detail:"@event.detail"}}` |
| `blurred` |  |  |
| `focused` |  |  |
| `keyDown` |  |  |
| `keyUp` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `formControlConfig` |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `formControlConfig.relatesTo` | `"control"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{requiredFeatures:{ShowDesignerDemoItems:true},position:70,icon:t(74262),defaultPropertyValues:{label:"",control:"",accept:"",readonly:false,placeholder:"",labelPosition:"auto"},defaultLocalizableStrings:{label:"Components.FileInput.LabelCaption",placeholder:"Components.FileInput.Placeholder"}},dataValueTypes:[A.r.Blob,A.r.FILE,A.r.Image,A.r.IMAGELOOKUP],propertiesPanelComponentTypeName:"crt.FileInputPropertiesPanelComponent",viewElementGroupType:O.J.Inputs,typeCaption:"Components.FileInput.Caption"}
```

## Приклад з реальної схеми


```json
{type:"crt.FileInput",formControlConfig:{relatesTo:"control"},reuseStrategy:b.B.Reuse}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 1 згадок у конфігах. Мінімізовані імена класів не наводяться.*