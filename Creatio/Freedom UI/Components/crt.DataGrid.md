---
type: crt.DataGrid
selector: crt-data-grid
group: "Списки і дані"
usage_in_configs: 251
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.DataGrid

> Реєстр (таблиця) над колекцією view-моделей. Найбільше прихованих властивостей: `_selectionOptions`, `_designOptions`, `placeholder`, `rowToolbarItems`, `bulkActions`, `features.*`.

Angular-селектор: `<crt-data-grid>`  
Група: **Списки і дані**  
Слоти вкладених елементів (`contentSlots`): `placeholder`, `skeleton`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **251** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ✅ рендериться — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `activeRow` |  | `<binding>` | 15 | `"$<Grid>_ActiveRow"` — Id активного рядка |
| `bulkActions` | `[]` | `[]` | 84 | дії над виділенням (`crt.MenuItem`, часто з `filters: "$Items \| crt.ToCollectionFilters : 'Items' : $DataTable_SelectionState \| crt.SkipIfSelectionEmpty : $DataTable_SelectionState"`) |
| `columns` |  | `<binding>` | 251 | масив колонок `{id, code, caption, dataValueType, width, path?, referenceSchemaName?, cellView?, editingCellView?}` або біндінг `"$DataTable_Columns"` (масив в атрибуті — можна міняти в рантаймі) |
| `editingCells` |  |  |  |  |
| `features` |  |  | 249 | `rows.selection.{enable,multiple}`, `rows.numeration`, `rows.toolbar`, `rows.hierarchical`, `columns.{sorting,resizing,dragAndDrop,adding,toolbar}`, `editable.{enable,itemsCreation,floatingEditPanel,lookupItemsCreation}`, `header.visible`, `cells.{selection,disableLinks}` |
| `fitContent` |  | `true`, `false` | 182 |  |
| `header` |  |  |  |  |
| `headerToolbarItems` |  | `[]` | 2 | кнопки у хедері гріда |
| `hierarchicalColumnName` |  | `"UsrParent"` | 1 | колонка-батько для ієрархічного відображення |
| `items` |  | `<binding>` | 251 | `"$Items"` / `"$GridDetail_xxx"` — колекція |
| `maxHeight` |  |  |  |  |
| `primaryColumnName` |  | `"AddressListDS_Id"`, `"CasesListDS_Id"`, `"RecommendedProductListDS_Id"`, `"OpportunityListDS_Id"`, `"OrderListDS_Id"`, `"ServiceAgreementsListDS_Id"`, `"LeadListDS_Id"`, `"GridDetail_e547wcqDS_Id"` | 249 | код колонки-ідентифікатора (`<DS>_Id`) |
| `rowToolbarItems` | `[]` |  | 35 | кнопки рядка — масив `crt.MenuItem` з `clicked {request, params: {itemsAttributeName, recordId: "$Items.PDS_Id"}}`, `disabled`, `visible`; `useRelativeContext: true` = контекст рядка |
| `selectedRows` |  |  |  | масив Id вибраних рядків (`DataTable_SelectedRows`) |
| `selectionState` |  | `<binding>` | 83 | `"$<Grid>_SelectionState"` — об'єкт `{type: "all"\|"specific", selected: [ids], unselected: [ids]}` |
| `sorting` |  | `<binding>` | 1 | `"$ItemsSorting \| crt.ToDataTableSortingConfig : 'Items'"` |
| `stretch` | `false` | `true` | 7 |  |
| `title` |  |  |  |  |
| `totalItemsCount` |  |  |  | загальна кількість (для пагінації/лічильника) |

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

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 238 |  | спільна → [[Common view-element properties#layoutConfig]] |
| `placeholder` | 189 | `false`, `null` | `false` або масив `crt.Placeholder` з `visible: "$DataTable_NoItems"` / `"$DataTable_NoFilteredItems"` |
| `visible` | 187 | `true` | спільна → [[Common view-element properties#visible]] |
| `_selectionOptions` | 83 |  | **прихована**: `{attribute: "<Grid>_SelectionState"}` — препроцесор створює атрибут стану виділення; або `{attribute:{from, expose}}` |
| `_designOptions` | 10 |  | **прихована**: `columns.cellViews[code]` — кастомний рендер комірки (`crt.Link`, `crt.TableTextCell`…), `columns.editingCellViews[code]`, `designSettings` — дефолтний профіль колонок |
| `style` | 4 | `"plain-white"` | `plain-white` |
| `referenceSchema` | 1 | `"SysSSPEntitySchemaAccessList"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `_designOptions.columns` | 10 |  |  |
| `_designOptions.columns.cellViews` | 10 |  |  |
| `_designOptions.columns.cellViews.GridDetail_2ydt4vbDS_UsrOracleInvoiceNo` | 3 |  |  |
| `_designOptions.columns.cellViews.GridDetail_iucisyyDS_UsrNoticeLetterPath` | 3 |  |  |
| `_designOptions.columns.cellViews.GridDetail_2k5u1e5DS_UsrOracleInvoiceNo` | 1 |  |  |
| `_designOptions.columns.cellViews.GridDetail_hjrwog2DS_UsrNumber` | 1 |  |  |
| `_designOptions.columns.cellViews.GridDetail_hxlmaupDS_UsrNumber` | 1 |  |  |
| `_designOptions.columns.cellViews.GridDetail_xy65rymDS_UsrOracleInvoiceNo` | 1 |  |  |
| `_selectionOptions.attribute` | 83 | `"GridDetail_odku0r4_SelectionState"`, `"GridDetail_7wxmt7n_SelectionState"`, `"GridDetail_wv97db3_SelectionState"`, `"GridDetail_d2yhkhu_SelectionState"`, `"GridDetail_12go2z3_SelectionState"`, `"GridDetail_v3k7o8y_SelectionState"` |  |
| `columns[].caption` | 141 | `<binding>`, `"#ResourceString(CasesListDS_Number)#"`, `"#ResourceString(OrderListDS_Number)#"`, `"#ResourceString(LeadListDS_LeadName)#"`, `"#ResourceString(CareerListDS_Account)#"`, `"#ResourceString(EventListDS_Event)#"` |  |
| `columns[].code` | 141 | `"AddressListDS_AddressType"`, `"CasesListDS_Number"`, `"RecommendedProductListDS_Product"`, `"OpportunityListDS_Title"`, `"OrderListDS_Number"`, `"ServiceAgreementsListDS_ServicePact"` |  |
| `columns[].dataValueType` | 141 | `10`, `28`, `27`, `30`, `7`, `12` |  |
| `columns[].id` | 141 | `"f23578a3-5240-8392-aef6-3253dff5ae76"`, `"5f12a33b-1971-47cf-2291-9b8226ddbb38"`, `"7e6dfd3c-b4a5-67f8-c43f-49034ad0c1e8"`, `"a7c6bc09-a9d8-4a93-0b1e-e3095bc8ac36"`, `"8bd7491f-6e03-01bb-b662-c27b4dab5ccd"`, `"5d82f0a9-f5e0-0bc4-fb2e-07d4b4d9772e"` |  |
| `columns[].width` | 66 | `114`, `163`, `340`, `280`, `314`, `272` |  |
| `columns[].path` | 43 | `"Number"`, `"AddressType"`, `"Product"`, `"ServicePact"`, `"Contact"`, `"Account"` |  |
| `columns[].referenceSchemaName` | 26 | `"Contact"`, `"AddressType"`, `"Product"`, `"ServicePact"`, `"Account"`, `"BulkEmailType"` |  |
| `columns[].editingCellView` | 2 |  |  |
| `columns[].editingCellView.items` | 2 | `<binding>` |  |
| `columns[].editingCellView.type` | 2 | `"crt.DataTableEditLookupCell"` |  |
| `columns[].editingCellView.useStaticFiltering` | 2 | `true` |  |
| `columns[].editingCellView.value` | 2 | `<binding>` |  |
| `columns[].editingCellView.valueChange` | 2 |  |  |
| `columns[].editingCellView.valueChange.params` | 2 |  |  |
| `columns[].editingCellView.valueChange.request` | 2 | `"crt.EditFormFieldRecordRequest"` |  |
| `columns[].sticky` | 1 | `true` |  |
| `createItem.params` | 2 |  |  |
| `createItem.params.insertionIndex` | 2 | `"@event.index"` |  |
| `createItem.request` | 2 | `"crt.AddFormFieldInlineRecordRequest"` |  |
| `features.rows` | 216 |  |  |
| `features.rows.selection` | 208 | `false` |  |
| `features.rows.selection.enable` | 182 | `true`, `false` |  |
| `features.rows.selection.multiple` | 182 | `true`, `false` |  |
| `features.editable` | 167 | `false` |  |
| `features.editable.itemsCreation` | 163 | `false`, `true` |  |
| `features.editable.enable` | 158 | `false`, `true` |  |
| `features.editable.floatingEditPanel` | 105 | `false`, `true` |  |
| `features.rows.numeration` | 76 | `false`, `true` |  |
| `features.rows.toolbar` | 42 | `false`, `true` |  |
| `features.columns` | 8 |  |  |
| `features.columns.dragAndDrop` | 6 | `true`, `false` |  |
| `features.header` | 6 |  |  |
| `features.header.visible` | 6 | `true`, `false` |  |
| `features.columns.resizing` | 5 | `true`, `false` |  |
| `features.columns.sorting` | 5 | `false`, `true` |  |
| `features.cells` | 2 |  |  |
| `features.cells.selection` | 2 | `false` |  |
| `features.columns.adding` | 2 | `false` |  |
| `features.hierarchical` | 1 |  |  |
| `features.hierarchical.enable` | 1 | `true` |  |
| `features.rows.hierarchical` | 1 | `true` |  |
| `features.rows.toobar` | 1 | `false` |  |
| `layoutConfig.colSpan` | 235 | `2`, `1`, `6` |  |
| `layoutConfig.column` | 235 | `1` |  |
| `layoutConfig.row` | 235 | `1`, `2`, `13` |  |
| `layoutConfig.rowSpan` | 235 | `6`, `1`, `8`, `15`, `16`, `11` |  |
| `layoutConfig.basis` | 2 | `"100%"` |  |
| `placeholder[].image` | 5 | `{}` |  |
| `placeholder[].subhead` | 5 | `<binding>`, `null` |  |
| `placeholder[].title` | 5 | `<binding>` |  |
| `placeholder[].type` | 5 | `"crt.Placeholder"` |  |
| `placeholder[].visible` | 5 | `<binding>` |  |
| `placeholder[].image.name` | 3 | `"search"` |  |
| `placeholder[].image.type` | 3 | `"animation"` |  |
| `rowToolbarItems[].caption` | 20 | `"DataGrid.RowToolbar.Open"`, `<binding>` |  |
| `rowToolbarItems[].clicked` | 20 |  |  |
| `rowToolbarItems[].clicked.params` | 20 |  |  |
| `rowToolbarItems[].clicked.request` | 20 | `"crt.UpdateRecordRequest"`, `"crt.DeleteFormFieldRecordRequest"` |  |
| `rowToolbarItems[].icon` | 20 | `"edit-row-action"`, `"delete-row-action"` |  |
| `rowToolbarItems[].type` | 20 | `"crt.MenuItem"` |  |
| `rowToolbarItems[].clicked.params.itemsAttributeName` | 18 | `"CampaignList"`, `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_d2yhkhu"`, `"GridDetail_1pq50ek"`, `"GridDetail_12go2z3"` |  |
| `rowToolbarItems[].clicked.params.recordId` | 18 | `<binding>` |  |
| `rowToolbarItems[].disabled` | 15 | `<binding>` |  |
| `rowToolbarItems[].clicked.useRelativeContext` | 9 | `true`, `false` |  |
| `rowToolbarItems[].visible` | 5 | `true` |  |
| `rowToolbarItems[].clicked.params.collectionName` | 2 | `"SelectedFormFieldsCollection"` |  |
| `rowToolbarItems[].clicked.params.fieldName` | 2 | `<binding>` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:20,icon:t(42604),hint:"Components.DataGrid.Hint",defaultPropertyValues:{}},propertiesPanelComponentTypeName:"crt.DataGridPropertiesPanel",designViewItemCommands:{copy:"crt.CopyDataGridItemCommand",create:"crt.CreateDataGridItemCommand",delete:"crt.RemoveDataGridViewItemCommand"},designControlConfig:{allowDesignContent:true,defaultValues:Ct},viewElementGroupType:r.J.Components,typeCaption:"Components.DataGrid.Caption",collectionPropertyNames:["bulkActions"]}
```

## Приклад з реальної схеми

Джерело: `Cases_FormPage.js`

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