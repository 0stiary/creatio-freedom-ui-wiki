---
type: crt.MenuItem
selector: crt-menu-item
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.MenuItem

> Пункт меню (у `Button.menuItems`, `DataGrid.rowToolbarItems/bulkActions`, `ComboBox.listActions`…).

Angular-селектор: `<crt-menu-item>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `caption` |  | `<binding>`, `"Export to Excel"`, `"Delete"`, `"Add tag"`, `"Remove tag"`, `"DataGrid.RowToolbar.Open"`, `"DataGrid.RowToolbar.Delete"`, `"Merge"` | текст або локалізований ключ (`DataGrid.RowToolbar.Open`) або `#ResourceString(...)#` |
| `disabled` |  | `<binding>` | (успадковано від базового класу) |
| `handleItemClick` |  |  | (успадковано від базового класу) |
| `icon` |  | `"export-button-icon"`, `"import-button-icon"`, `"delete-button-icon"`, `"tag-icon"`, `"edit-row-action"`, `"delete-row-action"`, `"merge-icon"`, `"copy-row-action"` | (успадковано від базового класу) |
| `iconColor` |  | `"accent"`, `"warn"` | (успадковано від базового класу) |
| `items` |  | `[]` | вкладені пункти (підменю) |
| `visible` |  | `true`, `<binding>` | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `clicked` | `"crt.ExportDataGridToExcelRequest"`, `"crt.ImportDataRequest"`, `"crt.DeleteRecordsRequest"`, `"crt.AddTagsInRecordsRequest"`, `"crt.RemoveTagsInRecordsRequest"`, `"crt.UpdateRecordRequest"`, `"crt.DeleteRecordRequest"`, `"crt.MergeRecordsRequest"`, `"crt.OpenPageRequest"`, `"crt.SelectionActionRequest"` | `{request, params, useRelativeContext?}`; у рядкових тулбарах `params.recordId: "$Items.PDS_Id"`, `itemsAttributeName` |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `color` | `"default"` | **прихована/дизайнерська** — не input компонента |
| `size` | `"medium"` |  |
| `clickMode` | `"default"`, `"menu"` |  |
| `defaultLocalizableStrings` |  | службове поле дизайнера — ключі локалізації, які підставляються при вставці елемента |
| `readonly` | `<binding>` |  |
| `selected` |  | службовий стан дизайнера (виділення елемента в Page Designer) |
| `dataItemMarker` | `"external-access"` | маркер для автотестів (`ts-data-item-marker`) |
| `_d` |  |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `clicked.request` | `"crt.ExportDataGridToExcelRequest"`, `"crt.ImportDataRequest"`, `"crt.DeleteRecordsRequest"`, `"crt.AddTagsInRecordsRequest"`, `"crt.RemoveTagsInRecordsRequest"`, `"crt.UpdateRecordRequest"` |  |
| `clicked.params` | `{}`, `null` |  |
| `clicked.params.viewName` | `"DataTable"`, `"AddressList"`, `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_wv97db3"`, `"GridDetail_d2yhkhu"` |  |
| `clicked.params.filters` | `<binding>` |  |
| `clicked.params.entitySchemaName` | `"Activity"`, `"UsrPendingLines"`, `"Case"`, `"UsrContactRefCodes"`, `"Contact"`, `"UsrTransaction"` |  |
| `clicked.params.dataSourceName` | `"PDS"`, `"GridDetail_odku0r4DS"`, `"ContactsListDS"`, `"GridDetail_7wxmt7nDS"`, `"GridDetail_v3k7o8yDS"`, `"DataGrid_wij59kwDS"` |  |
| `clicked.params.recordId` | `<binding>` |  |
| `clicked.params.itemsAttributeName` | `"Items"`, `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_12go2z3"`, `"BfDisplayCondition"`, `"GridDetail_d2yhkhu"` |  |
| `clicked.useRelativeContext` | `true`, `false` |  |
| `clicked.params.selectionState` | `<binding>` |  |
| `clicked.params.schemaName` | `"LandingiDesigner_Page"`, `"CampaignProgressCheck_ListPage"` |  |
| `clicked.params.dataGridName` |  |  |
| `clicked.params.messageTextAfterCompletion` |  |  |
| `clicked.params.tagInRecordSourceSchemaName` | `"AccountInTag"`, `"CallInTag"`, `"CampaignInTag"` |  |
| `clicked.params.confirmation` |  |  |
| `clicked.params.confirmation.message` |  |  |
| `clicked.params.bulkEmailId` | `<binding>` |  |
| `clicked.params.rewriteAction` | `"Friendly"`, `"Formal"`, `"Shorten"`, `"Extend"`, `"Rephrase"`, `"AskCopilot"` |  |
| `clicked.params.selectionAttributeName` |  |  |
| `clicked.params.entityName` | `"Account"`, `"Activity"` |  |
| `clicked.params.processName` | `"CopyLandingPageProcess"`, `"GrantAdAccountAccess"`, `"SynchronizeAdCampaignData"` |  |
| `clicked.params.processRunType` | `"RegardlessOfThePage"` |  |
| `clicked.params.showSuccessMessage` | `true` |  |
| `clicked.params.sysAdminUnitIds` |  |  |
| `clicked.params.timeScale` | `"00:05:00"`, `"00:10:00"`, `"00:15:00"`, `"00:30:00"`, `"01:00:00"` |  |
| `clicked.params.timeScaleAttributeName` | `"Calendar_Tasks_TimeScale"` |  |
| `clicked.params.confirmation.approveAction` |  |  |
| `clicked.params.mode` | `"scratch"`, `"preset"` |  |
| `clicked.params.summariesName` |  |  |
| `clicked.params.clearDescendants` | `true` |  |
| `clicked.params.fileName` |  |  |
| `clicked.params.approvalListAttributeName` |  |  |
| `clicked.params.collectionName` | `"SelectedFormFieldsCollection"` |  |
| `clicked.params.config` |  |  |
| `clicked.params.config.actionType` |  |  |
| `clicked.params.config.id` |  |  |
| `clicked.params.config.schemaName` |  |  |
| `clicked.params.fieldName` | `<binding>` |  |
| `clicked.params.isDefault` | `true` |  |
| `clicked.params.loadDataConfig` |  |  |
| `clicked.params.loadDataConfig.parentRecordId` | `<binding>` |  |
| `clicked.params.loadDataConfig.parentSchemaName` |  |  |
| `clicked.params.name` |  |  |
| `clicked.params.processParameters` |  |  |
| `clicked.params.processParameters.LandingPageGoal` | `<binding>` |  |
| `clicked.params.processParameters.LandingPageId` | `<binding>` |  |
| `clicked.params.processParameters.LandingPageName` | `<binding>` |  |
| `clicked.params.saveAtProcessStart` | `false` |  |
| `clicked.params.showNotification` | `false` |  |
| `clicked.params.viewElementName` |  |  |
| `clicked.params.bindingColumns` |  |  |
| `clicked.params.calendarType` |  |  |
| `clicked.params.columns` |  |  |
| `clicked.params.convertInPDF` |  |  |
| `clicked.params.dataTableData` |  |  |
| `clicked.params.dataTableData.columns` |  |  |
| `clicked.params.dataTableData.sorting` |  |  |
| `clicked.params.defaultValues` |  |  |
| `clicked.params.detail` |  |  |
| `clicked.params.detail.file` |  |  |
| `clicked.params.drilldownConfig` |  |  |
| `clicked.params.drilldownConfig.columns` |  |  |
| `clicked.params.elementName` |  |  |
| `clicked.params.mailboxId` |  |  |
| `clicked.params.payload` |  |  |
| `clicked.params.payload.entitySchemaName` | `"SysSchemaAdminUnit"` |  |
| `clicked.params.payload.primaryColumnValue` |  |  |
| `clicked.params.payload.primaryDisplayColumnValue` |  |  |
| `clicked.params.printableCaption` |  |  |
| `clicked.params.reportId` |  |  |
| `clicked.params.showWeekendsAttributeName` | `"Calendar_showweekends"` |  |
| `clicked.params.summaryItemCreationConfig` |  |  |
| `clicked.params.summaryItemCreationConfig.expression` |  |  |
| `clicked.params.summaryItemCreationConfig.label` |  |  |
| `clicked.params.summaryItemCreationConfig.modelName` |  |  |
| `clicked.params.templateId` |  |  |
| `clicked.params.userProfileDataAttributeName` |  |  |
| `clicked.params.viewModelAttributeName` |  |  |
| `clicked.params.widgetAttributePrefix` |  |  |
| `defaultLocalizableStrings.caption` | `"NextSteps.CreateActivityButtonCaption"`, `"NextSteps.CreateEmailButtonCaption"` |  |
| `items[].caption` |  |  |
| `items[].clicked` |  |  |
| `items[].clicked.params` |  |  |
| `items[].clicked.params.dataSourceName` |  |  |
| `items[].clicked.params.filters` |  |  |
| `items[].clicked.request` | `"crt.RemoveTagsInRecordsRequest"` |  |
| `items[].icon` | `"delete-button-icon"` |  |
| `items[].name` |  |  |
| `items[].type` | `"crt.MenuItem"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{propertiesPanelComponentTypeName:"crt.MenuItemPropertiesPanel",typeCaption:"TypeCaptions.MenuItem",viewElementGroupType:u.J.Components}
```

## Приклад з реальної схеми


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