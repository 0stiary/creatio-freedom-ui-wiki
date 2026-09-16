---
type: crt.FolderTreeActions
selector: crt-folder-tree-actions
group: "Фільтри"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FolderTreeActions

Angular-селектор: `<crt-folder-tree-actions>`  
Група: **Фільтри**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `activeFolderId` |  |  |  |
| `activeFolderName` |  |  |  |
| `favoriteItems` |  |  |  |
| `folderTree` |  | `"FolderTree"` |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `activeFolderChanged` |  |  |
| `folderTreeVisibleChanged` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:50,hint:"Components.FolderTreeActions.Hint",icon:n(41456),defaultPropertyValues:{folderTree:null}},propertiesPanelComponentTypeName:"crt.FolderTreeActionsPropertiesPanel",viewElementGroupType:f.J.Components,typeCaption:"Components.FolderTreeActions.Caption",placeholderSize:{height:"18px"}}
```

## Пов'язані

[[crt.FolderTree]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (9662.hash=f19e0bc4945383e5.js) + 7 згадок у конфігах. Мінімізовані імена класів не наводяться.*