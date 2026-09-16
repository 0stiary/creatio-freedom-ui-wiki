---
type: crt.FolderTree
selector: crt-folder-tree
group: "Фільтри"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FolderTree

> Дерево груп (папок) розділу.

Angular-селектор: `<crt-folder-tree>`  
Група: **Фільтри**  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `activeFolderId` |  |  |  |
| `borderRadius` |  | `"medium"`, `"none"` |  |
| `expandedItems` |  |  |  |
| `favoriteItems` |  |  |  |
| `items` |  |  |  |
| `minVisibleItemsCount` | `5` |  |  |
| `readonly` | `false` |  |  |
| `rootSchemaName` |  | `"AdCampaign"`, `"Activity"` | об'єкт розділу — для фільтрів папок |
| `showMask` |  |  |  |
| `sortingOrder` |  |  |  |
| `sourceSchemaName` |  | `"FolderTree"`, `"ActivityFolder"` | об'єкт папок (`<Entity>Folder`) |
| `useStaticFolders` | `false` |  | дозволити статичні групи |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `activeFolderChanged` |  |  |
| `addFolder` |  |  |
| `convertToStaticFolder` |  |  |
| `copyFolder` |  |  |
| `deleteFolder` |  |  |
| `folderChangeRights` |  |  |
| `folderFiltersUpdated` |  |  |
| `folderRenamed` |  |  |
| `folderTreeExpandedItemsChanged` |  |  |
| `folderTreeVisibleChanged` |  |  |
| `moveFolder` |  |  |
| `toggleFolderFavorite` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `_filterOptions` |  | **прихована**: `expose: [{attribute:"FolderTree_active_folder_filter", converters:[{converter:"crt.FolderTreeActiveFilterAttributeConverter", args:["<RootSchema>"]}]}], from: ["FolderTree_items","FolderTree_favoriteItems","FolderTree_active_folder_id"]` |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_filterOptions.expose` |  |  |
| `_filterOptions.expose[].attribute` | `"FolderTree_active_folder_filter"` |  |
| `_filterOptions.expose[].converters` |  |  |
| `_filterOptions.expose[].converters[].args` | `[]` |  |
| `_filterOptions.expose[].converters[].converter` |  |  |
| `_filterOptions.from` |  |  |
| `layoutConfig.width` | `328.125`, `328` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:60,hint:"Components.FolderTree.Hint",icon:n(19010),defaultPropertyValues:{sourceSchemaName:K.uE}},designViewItemCommands:{create:"crt.AddFilterViewItemCommand",update:"crt.ChangeFolderTreeViewItemCommand",delete:"crt.RemoveFolderTreeViewItemCommand",copy:"crt.CopyFolderTreeViewItemCommand"},propertiesPanelComponentTypeName:"crt.FolderTreePropertiesPanel",typeCaption:"Components.FolderTree.Caption",viewElementGroupType:h.J.Components,placeholderSize:{height:"49px"}}
```

## Приклад з реальної схеми


```json
{type:"crt.FolderTree",sourceSchemaName:"ActivityFolder",rootSchemaName:"Activity",layoutConfig:{width:328.125},classes:["section-folder-tree"],_filterOptions:{expose:[{attribute:"FolderTree_active_folder_filter",converters:[{converter:"crt.FolderTreeActiveFilterAttributeConverter",args:["Activity"]}]}],from:["FolderTree_items","FolderTree_favoriteItems","FolderTree_active_folder_id"]},borderRadius:"none"}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.FolderTree** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.FolderTree** (власні) | `activeFolderId`, `borderRadius`, `expandedItems`, `favoriteItems`, `items`, `minVisibleItemsCount`, `readonly`, `rootSchemaName`, `showMask`, `sortingOrder`, `sourceSchemaName`, `useStaticFolders` | `activeFolderChanged`, `addFolder`, `convertToStaticFolder`, `copyFolder`, `deleteFolder`, `folderChangeRights`, `folderFiltersUpdated`, `folderRenamed`, `folderTreeExpandedItemsChanged`, `folderTreeVisibleChanged`, `moveFolder`, `toggleFolderFavorite` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

## Пов'язані

[[crt.FolderTreeActions]], [[crt.QuickFilter]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (9662.hash=f19e0bc4945383e5.js) + 24 згадок у конфігах. Мінімізовані імена класів не наводяться.*