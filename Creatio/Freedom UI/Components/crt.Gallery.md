---
type: crt.Gallery
selector: crt-gallery
group: "Списки і дані"
usage_in_configs: 0
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Gallery

Angular-селектор: `<crt-gallery>`  
Група: **Списки і дані**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `ariaLabel` | `"gallery"` |  |  |  |
| `bulkActions` |  |  |  |  |
| `itemStyles` |  |  |  |  |
| `mode` |  |  |  |  |
| `multiselect` |  |  |  |  |
| `selectable` | `true` |  |  |  |
| `selectedItemId` |  |  |  |  |
| `selectionState` |  |  |  |  |
| `itemConfig` | `{}` |  |  | (успадковано від базового класу) |
| `items` |  |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `itemClick` |  |  |
| `itemDblClick` |  |  |
| `itemEvent` |  |  |
| `paginationChange` |  |  |
| `selectedItemIdChange` |  |  |
| `selectionStateChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:80,icon:t(45379),defaultPropertyValues:{}},propertiesPanelComponentTypeName:"crt.GalleryPropertiesPanel",designViewItemCommands:{copy:"crt.CopyGalleryItemCommand",create:"crt.CreateGalleryItemCommand",delete:"crt.RemoveCollectionViewItemCommand"},designControlConfig:{allowDesignContent:true},viewElementGroupType:d.J.Components,typeCaption:"Components.Gallery.Caption",collectionPropertyNames:["bulkActions"]}
```

## Приклад з реальної схеми

Джерело: `4223.hash=3d5a69794a1b3d08.js`

```json
{type:"crt.Gallery",reuseStrategy:i.B.Reuse,compatibleAPIs:{[s.I.Filtration]:true}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*