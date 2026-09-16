---
type: crt.DataGrid
selector: crt-data-grid
group: "Списки і дані"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.DataGrid

> Реєстр (таблиця) над колекцією view-моделей. Найбільше прихованих властивостей: `_selectionOptions`, `_designOptions`, `placeholder`, `rowToolbarItems`, `bulkActions`, `features.*`.

Angular-селектор: `<crt-data-grid>`  
Група: **Списки і дані**  
Слоти вкладених елементів (`contentSlots`): `placeholder`, `skeleton`  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ✅ рендериться — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `activeRow` |  | `<binding>` | `"$<Grid>_ActiveRow"` — Id активного рядка |
| `bulkActions` | `[]` | `[]` | дії над виділенням (`crt.MenuItem`, часто з `filters: "$Items \| crt.ToCollectionFilters : 'Items' : $DataTable_SelectionState \| crt.SkipIfSelectionEmpty : $DataTable_SelectionState"`) |
| `columns` |  | `<binding>` | масив колонок `{id, code, caption, dataValueType, width, path?, referenceSchemaName?, cellView?, editingCellView?}` або біндінг `"$DataTable_Columns"` (масив в атрибуті — можна міняти в рантаймі) |
| `editingCells` |  |  |  |
| `features` |  |  | `rows.selection.{enable,multiple}`, `rows.numeration`, `rows.toolbar`, `rows.hierarchical`, `columns.{sorting,resizing,dragAndDrop,adding,toolbar}`, `editable.{enable,itemsCreation,floatingEditPanel,lookupItemsCreation}`, `header.visible`, `cells.{selection,disableLinks}` |
| `fitContent` |  | `true`, `false` |  |
| `header` |  |  |  |
| `headerToolbarItems` |  | `[]` | кнопки у хедері гріда |
| `hierarchicalColumnName` |  | `"UsrParent"` | колонка-батько для ієрархічного відображення |
| `items` |  | `<binding>` | `"$Items"` / `"$GridDetail_xxx"` — колекція |
| `maxHeight` |  |  |  |
| `primaryColumnName` |  | `"AddressListDS_Id"`, `"CasesListDS_Id"`, `"RecommendedProductListDS_Id"`, `"OpportunityListDS_Id"`, `"OrderListDS_Id"`, `"ServiceAgreementsListDS_Id"`, `"LeadListDS_Id"`, `"GridDetail_e547wcqDS_Id"` | код колонки-ідентифікатора (`<DS>_Id`) |
| `rowToolbarItems` | `[]` |  | кнопки рядка — масив `crt.MenuItem` з `clicked {request, params: {itemsAttributeName, recordId: "$Items.PDS_Id"}}`, `disabled`, `visible`; `useRelativeContext: true` = контекст рядка |
| `selectedRows` |  |  | масив Id вибраних рядків (`DataTable_SelectedRows`) |
| `selectionState` |  | `<binding>` | `"$<Grid>_SelectionState"` — об'єкт `{type: "all"\|"specific", selected: [ids], unselected: [ids]}` |
| `sorting` |  | `<binding>` | `"$ItemsSorting \| crt.ToDataTableSortingConfig : 'Items'"` |
| `stretch` | `false` | `true` |  |
| `title` |  |  |  |
| `totalItemsCount` |  |  | загальна кількість (для пагінації/лічильника) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `activeRowChange` |  |  |
| `cancelItemsChanges` |  |  |
| `columnsChange` |  |  |
| `createItem` | `"crt.AddFormFieldInlineRecordRequest"` | інлайн-створення рядка (`crt.DataGridCreateItemRequest`) |
| `deleteItem` |  |  |
| `paginationChange` |  |  |
| `rowDoubleClick` |  | `{}` або `{request}`; за замовчуванням відкриває запис (`crt.DataGridRowDoubleClickRequest`) |
| `saveItemsChanges` |  |  |
| `selectedRowsChange` |  |  |
| `selectionStateChange` |  |  |
| `sortingChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `placeholder` | `false`, `null` | `false` або масив `crt.Placeholder` з `visible: "$DataTable_NoItems"` / `"$DataTable_NoFilteredItems"` |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `_selectionOptions` |  | **прихована**: `{attribute: "<Grid>_SelectionState"}` — препроцесор створює атрибут стану виділення; або `{attribute:{from, expose}}` |
| `_designOptions` |  | **прихована**: `columns.cellViews[code]` — кастомний рендер комірки (`crt.Link`, `crt.TableTextCell`…), `columns.editingCellViews[code]`, `designSettings` — дефолтний профіль колонок |
| `style` | `"plain-white"` | `plain-white` |
| `referenceSchema` | `"SysSSPEntitySchemaAccessList"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_designOptions.columns` |  |  |
| `_designOptions.columns.cellViews` |  |  |
| `_designOptions.columns.cellViews.GridDetail_2ydt4vbDS_UsrOracleInvoiceNo` |  |  |
| `_designOptions.columns.cellViews.GridDetail_iucisyyDS_UsrNoticeLetterPath` |  |  |
| `_designOptions.columns.cellViews.GridDetail_2k5u1e5DS_UsrOracleInvoiceNo` |  |  |
| `_designOptions.columns.cellViews.GridDetail_hjrwog2DS_UsrNumber` |  |  |
| `_designOptions.columns.cellViews.GridDetail_hxlmaupDS_UsrNumber` |  |  |
| `_designOptions.columns.cellViews.GridDetail_xy65rymDS_UsrOracleInvoiceNo` |  |  |
| `_selectionOptions.attribute` | `"GridDetail_odku0r4_SelectionState"`, `"GridDetail_7wxmt7n_SelectionState"`, `"GridDetail_wv97db3_SelectionState"`, `"GridDetail_d2yhkhu_SelectionState"`, `"GridDetail_12go2z3_SelectionState"`, `"GridDetail_v3k7o8y_SelectionState"` |  |
| `columns[].caption` | `<binding>`, `"#ResourceString(CasesListDS_Number)#"`, `"#ResourceString(OrderListDS_Number)#"`, `"#ResourceString(LeadListDS_LeadName)#"`, `"#ResourceString(CareerListDS_Account)#"`, `"#ResourceString(EventListDS_Event)#"` |  |
| `columns[].code` | `"AddressListDS_AddressType"`, `"CasesListDS_Number"`, `"RecommendedProductListDS_Product"`, `"OpportunityListDS_Title"`, `"OrderListDS_Number"`, `"ServiceAgreementsListDS_ServicePact"` |  |
| `columns[].dataValueType` | `10`, `28`, `27`, `30`, `7`, `12` |  |
| `columns[].id` | `"f23578a3-5240-8392-aef6-3253dff5ae76"`, `"5f12a33b-1971-47cf-2291-9b8226ddbb38"`, `"7e6dfd3c-b4a5-67f8-c43f-49034ad0c1e8"`, `"a7c6bc09-a9d8-4a93-0b1e-e3095bc8ac36"`, `"8bd7491f-6e03-01bb-b662-c27b4dab5ccd"`, `"5d82f0a9-f5e0-0bc4-fb2e-07d4b4d9772e"` |  |
| `columns[].width` | `114`, `163`, `340`, `280`, `314`, `272` |  |
| `columns[].path` | `"Number"`, `"AddressType"`, `"Product"`, `"ServicePact"`, `"Contact"`, `"Account"` |  |
| `columns[].referenceSchemaName` | `"Contact"`, `"AddressType"`, `"Product"`, `"ServicePact"`, `"Account"`, `"BulkEmailType"` |  |
| `columns[].editingCellView` |  |  |
| `columns[].editingCellView.items` | `<binding>` |  |
| `columns[].editingCellView.type` | `"crt.DataTableEditLookupCell"` |  |
| `columns[].editingCellView.useStaticFiltering` | `true` |  |
| `columns[].editingCellView.value` | `<binding>` |  |
| `columns[].editingCellView.valueChange` |  |  |
| `columns[].editingCellView.valueChange.params` |  |  |
| `columns[].editingCellView.valueChange.request` | `"crt.EditFormFieldRecordRequest"` |  |
| `columns[].sticky` | `true` |  |
| `createItem.params` |  |  |
| `createItem.params.insertionIndex` | `"@event.index"` |  |
| `createItem.request` | `"crt.AddFormFieldInlineRecordRequest"` |  |
| `features.rows` |  |  |
| `features.rows.selection` | `false` |  |
| `features.rows.selection.enable` | `true`, `false` |  |
| `features.rows.selection.multiple` | `true`, `false` |  |
| `features.editable` | `false` |  |
| `features.editable.itemsCreation` | `false`, `true` |  |
| `features.editable.enable` | `false`, `true` |  |
| `features.editable.floatingEditPanel` | `false`, `true` |  |
| `features.rows.numeration` | `false`, `true` |  |
| `features.rows.toolbar` | `false`, `true` |  |
| `features.columns` |  |  |
| `features.columns.dragAndDrop` | `true`, `false` |  |
| `features.header` |  |  |
| `features.header.visible` | `true`, `false` |  |
| `features.columns.resizing` | `true`, `false` |  |
| `features.columns.sorting` | `false`, `true` |  |
| `features.cells` |  |  |
| `features.cells.selection` | `false` |  |
| `features.columns.adding` | `false` |  |
| `features.hierarchical` |  |  |
| `features.hierarchical.enable` | `true` |  |
| `features.rows.hierarchical` | `true` |  |
| `features.rows.toobar` | `false` |  |
| `layoutConfig.colSpan` | `2`, `1`, `6` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `1`, `2`, `13` |  |
| `layoutConfig.rowSpan` | `6`, `1`, `8`, `15`, `16`, `11` |  |
| `layoutConfig.basis` | `"100%"` |  |
| `placeholder[].image` | `{}` |  |
| `placeholder[].subhead` | `<binding>`, `null` |  |
| `placeholder[].title` | `<binding>` |  |
| `placeholder[].type` | `"crt.Placeholder"` |  |
| `placeholder[].visible` | `<binding>` |  |
| `placeholder[].image.name` | `"search"` |  |
| `placeholder[].image.type` | `"animation"` |  |
| `rowToolbarItems[].caption` | `"DataGrid.RowToolbar.Open"`, `<binding>` |  |
| `rowToolbarItems[].clicked` |  |  |
| `rowToolbarItems[].clicked.params` |  |  |
| `rowToolbarItems[].clicked.request` | `"crt.UpdateRecordRequest"`, `"crt.DeleteFormFieldRecordRequest"` |  |
| `rowToolbarItems[].icon` | `"edit-row-action"`, `"delete-row-action"` |  |
| `rowToolbarItems[].type` | `"crt.MenuItem"` |  |
| `rowToolbarItems[].clicked.params.itemsAttributeName` | `"CampaignList"`, `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_d2yhkhu"`, `"GridDetail_1pq50ek"`, `"GridDetail_12go2z3"` |  |
| `rowToolbarItems[].clicked.params.recordId` | `<binding>` |  |
| `rowToolbarItems[].disabled` | `<binding>` |  |
| `rowToolbarItems[].clicked.useRelativeContext` | `true`, `false` |  |
| `rowToolbarItems[].visible` | `true` |  |
| `rowToolbarItems[].clicked.params.collectionName` | `"SelectedFormFieldsCollection"` |  |
| `rowToolbarItems[].clicked.params.fieldName` | `<binding>` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:20,icon:t(42604),hint:"Components.DataGrid.Hint",defaultPropertyValues:{}},propertiesPanelComponentTypeName:"crt.DataGridPropertiesPanel",designViewItemCommands:{copy:"crt.CopyDataGridItemCommand",create:"crt.CreateDataGridItemCommand",delete:"crt.RemoveDataGridViewItemCommand"},designControlConfig:{allowDesignContent:true,defaultValues:Ct},viewElementGroupType:r.J.Components,typeCaption:"Components.DataGrid.Caption",collectionPropertyNames:["bulkActions"]}
```

## Приклад з реальної схеми


```json
{
					"type": "crt.DataGrid",
					"layoutConfig": {
						"colSpan": 2,
						"column": 1,
						"row": 1,
						"rowSpan": 6
					},
					"features": {
						"rows": {
							"selection": {
								"enable": true,
								"multiple": true
							}
						}
					},
					"items": "$GridDetail_zfx9e33",
					"visible": true,
					"style": "plain-white",
					"fitContent": true,
					"primaryColumnName": "GridDetail_zfx9e33DS_Id",
					"columns": [
						{
							"id": "44301434-6117-1767-ee68-77d580ce08e9",
							"code": "GridDetail_zfx9e33DS_CreatedBy",
							"caption": "#ResourceString(GridDetail_zfx9e33DS_CreatedBy)#",
							"dataValueType": 10
						}
					],
					"placeholder": false
				}
```

## Нотатки

**Атрибути, що генеруються навколо гріда `<Grid>`:** `<Grid>` (колекція), `<Grid>_ActiveRow`, `<Grid>_SelectionState`, `<Grid>_SelectedRows`, `<Grid>_PredefinedFilter`, `<Grid>_Columns` (якщо `columns: "$…"`), `<Grid>_NoItems`/`_NoFilteredItems` (через конвертери `crt.DataGridHasNoItems`).
**cellView** (через `_designOptions.columns.cellViews.<code>` або `columns[].cellView`): `{ type: "crt.Link", caption: "$Items.PDS_X | crt.ToObjectProp : 'displayValue'", href: "$Items.PDS_X | crt.ToObjectProp : 'value' | crt.ToRecordLinkAsync : 'PDS_X'", target: "_blank", mode: "native" }` або `{ name, type: "crt.TableTextCell", disabled: true, control: "Items.PDS_X", value: "$Items.PDS_X | usr.Conv" }`.
**Запити гріда:** `crt.LoadDataRequest {dataSourceName, config:{loadType:"reload"}}`, `crt.ExportDataGridToExcelRequest {viewName}`, `crt.DeleteRecordsRequest`, `crt.DataGridSortDataRequest`, `crt.DataGridCreateItemRequest`, `crt.DataGridRowDoubleClickRequest`, `crt.DataGridSaveDesignSettingsRequest`.

## Пов'язані

[[crt.MenuItem]], [[crt.Placeholder]], [[crt.TableTextCell]], [[crt.TableBooleanCell]], [[crt.TableColoredCell]], [[crt.DataTableEditLookupCell]], [[crt.SearchFilter]], [[crt.QuickFilter]], [[crt.Summaries]], [[crt.FileList]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 2132 згадок у конфігах. Мінімізовані імена класів не наводяться.*