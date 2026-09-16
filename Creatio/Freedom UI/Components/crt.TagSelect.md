---
type: crt.TagSelect
selector: crt-tag-select
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TagSelect

> Теги запису.

Angular-селектор: `<crt-tag-select>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `disabled` |  |  |  |
| `items` |  |  |  |
| `label` | `""` |  |  |
| `labelPosition` | `""` |  |  |
| `listItems` |  |  |  |
| `wrap` | `false` |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `addTagsInRecord` |  |  |
| `createTag` |  |  |
| `deleteTag` |  |  |
| `deleteTagInRecord` |  |  |
| `editTag` |  |  |
| `paginationChange` |  |  |
| `showList` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `recordId` | `<binding>` | **прихована**: `$Id` — препроцесор налаштовує список тегів і схему `<Entity>Tag/InTag` |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:180,icon:t(19450),defaultPropertyValues:{tagInRecordSourceSchemaName:Is.lo}},propertiesPanelComponentTypeName:"crt.TagSelectPropertiesPanel",viewElementGroupType:O.J.Components,typeCaption:"Components.TagSelect.Caption",placeholderSize:{height:"18px"}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 2 згадок у конфігах. Мінімізовані імена класів не наводяться.*