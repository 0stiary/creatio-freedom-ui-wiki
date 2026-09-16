---
type: crt.ListWidget
selector: crt-list-widget
group: "Дашборди та віджети"
usage_in_configs: 3
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ListWidget

Angular-селектор: `<crt-list-widget>`  
Група: **Дашборди та віджети**  
Слоти вкладених елементів (`contentSlots`): `placeholder`, `skeleton`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **3** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `widgetConfig` | `{}` |  | 3 |  |
| `widgetToolbarItems` | `[]` |  | 1 |  |
| `activeRow` |  | `<binding>` | 2 | (успадковано від базового класу) |
| `bulkActions` | `[]` | `[]` | 2 | (успадковано від базового класу) |
| `columns` | `[]` |  | 3 | (успадковано від базового класу) |
| `editingCells` |  |  |  | (успадковано від базового класу) |
| `features` |  |  | 3 | (успадковано від базового класу) |
| `fitContent` |  | `true` | 2 | (успадковано від базового класу) |
| `header` |  |  |  | (успадковано від базового класу) |
| `headerToolbarItems` | `[]` | `[]` | 1 | (успадковано від базового класу) |
| `hierarchicalColumnName` |  |  |  | (успадковано від базового класу) |
| `items` |  | `<binding>` | 3 | (успадковано від базового класу) |
| `maxHeight` |  |  |  | (успадковано від базового класу) |
| `primaryColumnName` |  | `"ListWidget_wgiaud9DS_Id"` | 3 | (успадковано від базового класу) |
| `rowToolbarItems` | `[]` |  |  | (успадковано від базового класу) |
| `selectedRows` |  |  |  | (успадковано від базового класу) |
| `selectionState` |  | `<binding>` | 2 | (успадковано від базового класу) |
| `sorting` |  |  |  | (успадковано від базового класу) |
| `stretch` |  |  |  | (успадковано від базового класу) |
| `title` |  | `<binding>` | 3 | (успадковано від базового класу) |
| `totalItemsCount` |  |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `loading` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `activeRowChange` |  |  |
| `cancelItemsChanges` |  |  |
| `columnsChange` |  |  |
| `createItem` |  |  |
| `deleteItem` |  |  |
| `paginationChange` |  |  |
| `rowDoubleClick` |  |  |
| `saveItemsChanges` |  |  |
| `selectedRowsChange` |  |  |
| `selectionStateChange` |  |  |
| `sortingChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `placeholder` | 3 | `false` |  |
| `layoutConfig` | 2 |  | спільна → [[Common view-element properties#layoutConfig]] |
| `_selectionOptions` | 2 |  |  |
| `visible` | 2 | `true` | спільна → [[Common view-element properties#visible]] |
| `rowsLimit` | 1 |  |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `_selectionOptions.attribute` | 2 | `"ListWidget_wgiaud9_SelectionState"` |  |
| `columns[].caption` | 2 | `<binding>` |  |
| `columns[].code` | 2 | `"ListWidget_wgiaud9DS_CreatedOn"` |  |
| `columns[].dataValueType` | 2 | `7` |  |
| `columns[].id` | 2 | `"3b745f55-618e-9b83-debd-8d20e46ffd3a"` |  |
| `features.columns` | 3 |  |  |
| `features.columns.dragAndDrop` | 3 | `false` |  |
| `features.columns.resizing` | 3 | `true` |  |
| `features.columns.sorting` | 3 | `true` |  |
| `features.editable` | 3 | `false` |  |
| `features.rows` | 3 |  |  |
| `features.rows.numeration` | 3 | `true` |  |
| `features.rows.selection` | 3 | `false` |  |
| `features.header` | 2 |  |  |
| `features.header.visible` | 2 | `true` |  |
| `features.rows.selection.enable` | 2 | `true` |  |
| `features.rows.selection.multiple` | 2 | `false` |  |
| `features.columns.adding` | 1 | `false` |  |
| `features.columns.toolbar` | 1 | `false` |  |
| `features.rows.hierarchical` | 1 | `false` |  |
| `features.rows.toolbar` | 1 | `false` |  |
| `layoutConfig.colSpan` | 2 | `12` |  |
| `layoutConfig.column` | 2 | `1` |  |
| `layoutConfig.row` | 2 | `12` |  |
| `layoutConfig.rowSpan` | 2 | `16` |  |
| `widgetConfig.layout` | 3 |  |  |
| `widgetConfig.layout.color` | 3 | `"dark-blue"` |  |
| `widgetConfig.theme` | 3 | `"without-fill"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:30,icon:t(89640),hint:"CDK.ListWidget.Hint",defaultPropertyValues:{widgetConfig:{theme:al.k.WithoutFill,layout:{color:Fe.e.DarkBlue}}},defaultLocalizableStrings:{title:bo}},propertiesPanelComponentTypeName:"crt.ListWidgetPropertiesPanel",designViewItemCommands:{copy:"crt.CopyDataGridItemCommand",create:"crt.CreateListWidgetItemCommand",delete:"crt.RemoveDataGridViewItemCommand"},designControlConfig:{allowDesignContent:true,defaultValues:Gi.n},viewElementGroupType:io.J.Charts,typeCaption:"CDK.ListWidget.Caption",collectionPropertyNames:["bulkActions"]}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_18.js.завантаження`

```json
{layoutConfig:{column:1,colSpan:12,row:12,rowSpan:16},type:"crt.ListWidget",widgetConfig:{theme:"without-fill",layout:{color:"dark-blue"}},title:"#ResourceString(SubmissionsList_title)#",features:{rows:{numeration:true,selection:{enable:true,multiple:false}},editable:false,header:{visible:true},columns:{dragAndDrop:false,resizing:true,sorting:true}},items:"$ListWidget_wgiaud9",selectionState:"$ListWidget_wgiaud9_SelectionState",_selectionOptions:{attribute:"ListWidget_wgiaud9_SelectionState"},primaryColumnName:"ListWidget_wgiaud9DS_Id",columns:[{id:"3b745f55-618e-9b83-debd-8d20e46ffd3a",code:"ListWidget_wgiaud9DS_CreatedOn",caption:"#ResourceString(ListWidget_wgiaud9DS_CreatedOn)#",dataValueType:7},{id:"f7eb7afa-7f01-87d3-df30-a25b691c21ae",code:"ListWidget_wgiaud9DS_Contact",caption:"#ResourceString(ListWidget_wgiaud9DS_Contact)#",dataValueType:10},{id:"51a026ee-83e0-6c8c-40b1-0c3a21d20c3b",code:"ListWidget_wgiaud9DS_Email",caption:"#ResourceString(ListWidget_wgiaud9DS_Email)#",dataValueType:28},{id:"b134ab56-94f0-c447-7720-ff4cd7f5fd1c",code:"ListWidget_wgiaud9DS_Channel",caption:"#ResourceString(ListWidget_wgiaud9DS_Channel)#",dataValueType:10},{id:"a084a4b8-9519-b00e-4da6-6d11c361acf4",code:"ListWidget_wgiaud9DS_Source",caption:"#ResourceString(ListWidget_wgiaud9DS_Source)#",dataValueType:10}],placeholder:false,bulkActions:[],visible:true,fitContent:true,activeRow:"$ListWidget_wgiaud9_ActiveRow"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 38 згадок у конфігах. Мінімізовані імена класів не наводяться.*