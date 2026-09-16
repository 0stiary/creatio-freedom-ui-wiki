---
type: crt.MenuItem
selector: crt-menu-item
group: "Базові компоненти"
usage_in_configs: 899
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.MenuItem

> Пункт меню (у `Button.menuItems`, `DataGrid.rowToolbarItems/bulkActions`, `ComboBox.listActions`…).

Angular-селектор: `<crt-menu-item>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **899** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `caption` |  | `<binding>`, `"Export to Excel"`, `"Delete"`, `"Add tag"`, `"Remove tag"`, `"DataGrid.RowToolbar.Open"`, `"DataGrid.RowToolbar.Delete"`, `"Merge"` | 899 | текст або локалізований ключ (`DataGrid.RowToolbar.Open`) або `#ResourceString(...)#` |
| `disabled` |  | `<binding>` | 58 | (успадковано від базового класу) |
| `handleItemClick` |  |  | 38 | (успадковано від базового класу) |
| `icon` |  | `"export-button-icon"`, `"import-button-icon"`, `"delete-button-icon"`, `"tag-icon"`, `"edit-row-action"`, `"delete-row-action"`, `"merge-icon"`, `"copy-row-action"` | 871 | (успадковано від базового класу) |
| `iconColor` |  | `"accent"`, `"warn"` | 4 | (успадковано від базового класу) |
| `items` |  | `[]` | 61 | вкладені пункти (підменю) |
| `visible` |  | `true`, `<binding>` | 196 | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `clicked` | `"crt.ExportDataGridToExcelRequest"`, `"crt.ImportDataRequest"`, `"crt.DeleteRecordsRequest"`, `"crt.AddTagsInRecordsRequest"`, `"crt.RemoveTagsInRecordsRequest"`, `"crt.UpdateRecordRequest"`, `"crt.DeleteRecordRequest"`, `"crt.MergeRecordsRequest"`, `"crt.OpenPageRequest"`, `"crt.SelectionActionRequest"` | `{request, params, useRelativeContext?}`; у рядкових тулбарах `params.recordId: "$Items.PDS_Id"`, `itemsAttributeName` |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `color` | 403 | `"default"` | **прихована/дизайнерська** — не input компонента |
| `size` | 403 | `"medium"` |  |
| `clickMode` | 5 | `"default"`, `"menu"` |  |
| `defaultLocalizableStrings` | 4 |  | службове поле дизайнера — ключі локалізації, які підставляються при вставці елемента |
| `readonly` | 2 | `<binding>` |  |
| `selected` | 1 |  | службовий стан дизайнера (виділення елемента в Page Designer) |
| `dataItemMarker` | 1 | `"external-access"` | маркер для автотестів (`ts-data-item-marker`) |
| `_d` | 1 |  |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `clicked.request` | 851 | `"crt.ExportDataGridToExcelRequest"`, `"crt.ImportDataRequest"`, `"crt.DeleteRecordsRequest"`, `"crt.AddTagsInRecordsRequest"`, `"crt.RemoveTagsInRecordsRequest"`, `"crt.UpdateRecordRequest"` |  |
| `clicked.params` | 840 | `{}`, `null` |  |
| `clicked.params.viewName` | 313 | `"DataTable"`, `"AddressList"`, `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_wv97db3"`, `"GridDetail_d2yhkhu"` |  |
| `clicked.params.filters` | 270 | `<binding>` |  |
| `clicked.params.entitySchemaName` | 196 | `"Activity"`, `"UsrPendingLines"`, `"Case"`, `"UsrContactRefCodes"`, `"Contact"`, `"UsrTransaction"` |  |
| `clicked.params.dataSourceName` | 182 | `"PDS"`, `"GridDetail_odku0r4DS"`, `"ContactsListDS"`, `"GridDetail_7wxmt7nDS"`, `"GridDetail_v3k7o8yDS"`, `"DataGrid_wij59kwDS"` |  |
| `clicked.params.recordId` | 83 | `<binding>` |  |
| `clicked.params.itemsAttributeName` | 79 | `"Items"`, `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_12go2z3"`, `"BfDisplayCondition"`, `"GridDetail_d2yhkhu"` |  |
| `clicked.useRelativeContext` | 23 | `true`, `false` |  |
| `clicked.params.selectionState` | 16 | `<binding>` |  |
| `clicked.params.schemaName` | 9 | `"LandingiDesigner_Page"`, `"CampaignProgressCheck_ListPage"` |  |
| `clicked.params.dataGridName` | 8 |  |  |
| `clicked.params.messageTextAfterCompletion` | 8 |  |  |
| `clicked.params.tagInRecordSourceSchemaName` | 8 | `"AccountInTag"`, `"CallInTag"`, `"CampaignInTag"` |  |
| `clicked.params.confirmation` | 7 |  |  |
| `clicked.params.confirmation.message` | 7 |  |  |
| `clicked.params.bulkEmailId` | 6 | `<binding>` |  |
| `clicked.params.rewriteAction` | 6 | `"Friendly"`, `"Formal"`, `"Shorten"`, `"Extend"`, `"Rephrase"`, `"AskCopilot"` |  |
| `clicked.params.selectionAttributeName` | 6 |  |  |
| `clicked.params.entityName` | 5 | `"Account"`, `"Activity"` |  |
| `clicked.params.processName` | 5 | `"CopyLandingPageProcess"`, `"GrantAdAccountAccess"`, `"SynchronizeAdCampaignData"` |  |
| `clicked.params.processRunType` | 5 | `"RegardlessOfThePage"` |  |
| `clicked.params.showSuccessMessage` | 5 | `true` |  |
| `clicked.params.sysAdminUnitIds` | 5 |  |  |
| `clicked.params.timeScale` | 5 | `"00:05:00"`, `"00:10:00"`, `"00:15:00"`, `"00:30:00"`, `"01:00:00"` |  |
| `clicked.params.timeScaleAttributeName` | 5 | `"Calendar_Tasks_TimeScale"` |  |
| `clicked.params.confirmation.approveAction` | 4 |  |  |
| `clicked.params.mode` | 4 | `"scratch"`, `"preset"` |  |
| `clicked.params.summariesName` | 4 |  |  |
| `clicked.params.clearDescendants` | 3 | `true` |  |
| `clicked.params.fileName` | 3 |  |  |
| `clicked.params.approvalListAttributeName` | 2 |  |  |
| `clicked.params.collectionName` | 2 | `"SelectedFormFieldsCollection"` |  |
| `clicked.params.config` | 2 |  |  |
| `clicked.params.config.actionType` | 2 |  |  |
| `clicked.params.config.id` | 2 |  |  |
| `clicked.params.config.schemaName` | 2 |  |  |
| `clicked.params.fieldName` | 2 | `<binding>` |  |
| `clicked.params.isDefault` | 2 | `true` |  |
| `clicked.params.loadDataConfig` | 2 |  |  |
| `clicked.params.loadDataConfig.parentRecordId` | 2 | `<binding>` |  |
| `clicked.params.loadDataConfig.parentSchemaName` | 2 |  |  |
| `clicked.params.name` | 2 |  |  |
| `clicked.params.processParameters` | 2 |  |  |
| `clicked.params.processParameters.LandingPageGoal` | 2 | `<binding>` |  |
| `clicked.params.processParameters.LandingPageId` | 2 | `<binding>` |  |
| `clicked.params.processParameters.LandingPageName` | 2 | `<binding>` |  |
| `clicked.params.saveAtProcessStart` | 2 | `false` |  |
| `clicked.params.showNotification` | 2 | `false` |  |
| `clicked.params.viewElementName` | 2 |  |  |
| `clicked.params.bindingColumns` | 1 |  |  |
| `clicked.params.calendarType` | 1 |  |  |
| `clicked.params.columns` | 1 |  |  |
| `clicked.params.convertInPDF` | 1 |  |  |
| `clicked.params.dataTableData` | 1 |  |  |
| `clicked.params.dataTableData.columns` | 1 |  |  |
| `clicked.params.dataTableData.sorting` | 1 |  |  |
| `clicked.params.defaultValues` | 1 |  |  |
| `clicked.params.detail` | 1 |  |  |
| `clicked.params.detail.file` | 1 |  |  |
| `clicked.params.drilldownConfig` | 1 |  |  |
| `clicked.params.drilldownConfig.columns` | 1 |  |  |
| `clicked.params.elementName` | 1 |  |  |
| `clicked.params.mailboxId` | 1 |  |  |
| `clicked.params.payload` | 1 |  |  |
| `clicked.params.payload.entitySchemaName` | 1 | `"SysSchemaAdminUnit"` |  |
| `clicked.params.payload.primaryColumnValue` | 1 |  |  |
| `clicked.params.payload.primaryDisplayColumnValue` | 1 |  |  |
| `clicked.params.printableCaption` | 1 |  |  |
| `clicked.params.reportId` | 1 |  |  |
| `clicked.params.showWeekendsAttributeName` | 1 | `"Calendar_showweekends"` |  |
| `clicked.params.summaryItemCreationConfig` | 1 |  |  |
| `clicked.params.summaryItemCreationConfig.expression` | 1 |  |  |
| `clicked.params.summaryItemCreationConfig.label` | 1 |  |  |
| `clicked.params.summaryItemCreationConfig.modelName` | 1 |  |  |
| `clicked.params.templateId` | 1 |  |  |
| `clicked.params.userProfileDataAttributeName` | 1 |  |  |
| `clicked.params.viewModelAttributeName` | 1 |  |  |
| `clicked.params.widgetAttributePrefix` | 1 |  |  |
| `defaultLocalizableStrings.caption` | 4 | `"NextSteps.CreateActivityButtonCaption"`, `"NextSteps.CreateEmailButtonCaption"` |  |
| `items[].caption` | 1 |  |  |
| `items[].clicked` | 1 |  |  |
| `items[].clicked.params` | 1 |  |  |
| `items[].clicked.params.dataSourceName` | 1 |  |  |
| `items[].clicked.params.filters` | 1 |  |  |
| `items[].clicked.request` | 1 | `"crt.RemoveTagsInRecordsRequest"` |  |
| `items[].icon` | 1 | `"delete-button-icon"` |  |
| `items[].name` | 1 |  |  |
| `items[].type` | 1 | `"crt.MenuItem"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{propertiesPanelComponentTypeName:"crt.MenuItemPropertiesPanel",typeCaption:"TypeCaptions.MenuItem",viewElementGroupType:u.J.Components}
```

## Приклад з реальної схеми

Джерело: `UsrBillingLines_FormPage.js`

```json
{
							"type": "crt.MenuItem",
							"caption": "DataGrid.RowToolbar.Delete",
							"icon": "delete-row-action",
							"visible": "$GridDetail_zr7fxln.GridDetail_zr7fxlnDS_UsrReletionType | usr.CanEditLinkedLines : $GridDetail_zr7fxln.GridDetail_zr7fxlnDS_Id",
							"clicked": {
								"request": "crt.DeleteRecordRequest",
								"params": {
									"itemsAttributeName": "GridDetail_zr7fxln",
									"recordId": "$GridDetail_zr7fxln.GridDetail_zr7fxlnDS_Id"
								}
							}
						}
```

## Пов'язані

[[crt.Button]], [[crt.Menu]], [[crt.DataGrid]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 3837 згадок у конфігах. Мінімізовані імена класів не наводяться.*