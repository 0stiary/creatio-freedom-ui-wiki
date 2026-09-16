---
type: crt.FileList
selector: crt-file-list
group: "Timeline / Feed / Файли"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FileList

> Список файлів (успадковує DataGrid).

Angular-селектор: `<crt-file-list>`  
Група: **Timeline / Feed / Файли**  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `droppable` | `false` |  |  |
| `features` |  |  |  |
| `fileGroups` |  |  | групи файлів |
| `galleryItemConfig` |  |  |  |
| `items` |  | `<binding>` |  |
| `masterRecordColumnValue` |  | `<binding>`, `null` | `$Id` |
| `recordColumnName` |  | `"RecordId"`, `"VwSysProcess"`, `"UsrPendingLines"` | колонка-посилання на майстер-запис (`UsrPendingLines`) |
| `tag` |  |  |  |
| `viewType` |  | `"gallery"` | `gallery` / `list` |
| `activeRow` |  |  | (успадковано від базового класу) |
| `bulkActions` | `[]` |  | (успадковано від базового класу) |
| `columns` |  |  | (успадковано від базового класу) |
| `editingCells` |  |  | (успадковано від базового класу) |
| `fitContent` |  |  | (успадковано від базового класу) |
| `header` |  |  | (успадковано від базового класу) |
| `headerToolbarItems` |  |  | (успадковано від базового класу) |
| `hierarchicalColumnName` |  |  | (успадковано від базового класу) |
| `maxHeight` |  |  | (успадковано від базового класу) |
| `primaryColumnName` |  | `"AttachmentListDS_Id"`, `"FileList_v3u1cpzDS_Id"`, `"FileList_pazhlwoDS_Id"` | (успадковано від базового класу) |
| `rowToolbarItems` | `[]` |  | (успадковано від базового класу) |
| `selectedRows` |  |  | (успадковано від базового класу) |
| `selectionState` |  |  | (успадковано від базового класу) |
| `sorting` |  |  | (успадковано від базового класу) |
| `stretch` | `false` |  | (успадковано від базового класу) |
| `title` |  |  | (успадковано від базового класу) |
| `totalItemsCount` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `fileDropped` |  |  |
| `uploadClicked` |  |  |
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

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `tileSize` | `"small"`, `"medium"` | **прихована**: `small`… |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `columns[].caption` | `<binding>` |  |
| `columns[].code` | `"AttachmentListDS_Name"`, `"FileList_v3u1cpzDS_Name"`, `"FileList_pazhlwoDS_Name"` |  |
| `columns[].dataValueType` | `28` |  |
| `columns[].id` | `"0193477a-4a7f-4e8f-b40a-6908c85dfeb0"`, `"5ab4b71a-d4a1-8189-f7e0-1a859e4555c5"`, `"3085fa39-2b1a-2a36-d098-9cf8310d04e2"` |  |
| `columns[].width` | `200` |  |
| `layoutConfig.colSpan` | `2` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `1` |  |
| `layoutConfig.rowSpan` | `10`, `6` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{propertiesPanelComponentTypeName:"crt.FileListPropertiesPanel",designViewItemCommands:{copy:"crt.CopyFileListItemCommand",delete:"crt.RemoveCollectionViewItemCommand"},designControlConfig:{allowDesignContent:true},viewElementGroupType:b.J.Components,typeCaption:"Components.Attachment.Caption"}
```

## Приклад з реальної схеми


```json
{
					"type": "crt.FileList",
					"masterRecordColumnValue": "$Id",
					"recordColumnName": "RecordId",
					"layoutConfig": {
						"colSpan": 2,
						"column": 1,
						"row": 1,
						"rowSpan": 10
					},
					"items": "$FileList_v3u1cpz",
					"primaryColumnName": "FileList_v3u1cpzDS_Id",
					"columns": [
						{
							"id": "5ab4b71a-d4a1-8189-f7e0-1a859e4555c5",
							"code": "FileList_v3u1cpzDS_Name",
							"caption": "#ResourceString(FileList_v3u1cpzDS_Name)#",
							"dataValueType": 28
						},
						{
							"id": "b6b67a9f-e067-3ef8-cafb-c6b98b0414b5",
							"code": "FileList_v3u1cpzDS_CreatedOn",
							"caption": "#ResourceString(FileList_v3u1cpzDS_CreatedOn)#",
							"dataValueType": 7
						},
						{
							"id": "1a2f1899-4647-645f-c1b1-85a12470e60a",
							"code": "FileList_v3u1cpzDS_CreatedBy",
							"caption": "#ResourceString(FileList_v3u1cpzDS_CreatedBy)#",
							"dataValueType": 10
						},
						{
							"id": "d6888e9c-739f-485c-f7f7-5ed22e75c489",
							"code": "FileList_v3u1cpzDS_Size",
							"caption": "#ResourceString(FileList_v3u1cpzDS_Size)#",
							"dataValueType": 4
						}
					],
					"visible": true,
					"viewType": "gallery",
					"tileSize": "medium"
				}
```

## Пов'язані

[[crt.DataGrid]], [[crt.FileGalleryItem]], [[crt.FileInput]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 90 згадок у конфігах. Мінімізовані імена класів не наводяться.*