---
type: crt.Button
selector: crt-button
group: "Базові компоненти"
usage_in_configs: 797
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Button

> Кнопка; з `menuItems` + `clickMode: "menu"` стає меню.

Angular-селектор: `<crt-button>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **797** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `allowMenuOnDisabled` |  |  |  | меню доступне навіть коли кнопка disabled |
| `ariaLabel` |  |  | 2 | (успадковано від базового класу) |
| `attributes` |  |  |  | (успадковано від базового класу) |
| `autofocus` |  |  |  | (успадковано від базового класу) |
| `caption` | `""` | `<binding>`, `"#ResourceString(Button_Data_Import)#"`, `"#ResourceString(ActionButton_caption)#"`, `"#ResourceString(RefreshButtonCaption)#"`, `""`, `"#ResourceString(BackButton)#"`, `"#ResourceString(Button_Back_caption)#"` | 797 | (успадковано від базового класу) |
| `clickMode` |  | `default` · `"default"`, `"menu"` | 483 | `default` / `menu` |
| `color` |  | `"default"`, `"accent"`, `"outline"`, `"primary"`, `"warn"` | 796 | `default` / `primary` / `accent` / `outline` / `warning` |
| `contentAlign` | `"center"` |  |  | (успадковано від базового класу) |
| `disableRipple` |  |  |  | (успадковано від базового класу) |
| `disabled` |  | `false`, `<binding>` | 204 | біндінг або `true/false` |
| `displayMenuIcon` | `false` |  |  | (успадковано від базового класу) |
| `displayType` |  | `"text"` | 5 | (успадковано від базового класу) |
| `icon` |  | `"actions-button-icon"`, `"reload-icon"`, `"add-button-icon"`, `"reload-button-icon"`, `<binding>`, `"close-button-icon"`, `"copy-icon"`, `"upload-button-icon"` | 730 | системна іконка (`add-button-icon`, `reload-button-icon`, `export-button-icon`, `import-button-icon`, `more-button-icon`, `actions-button-icon`, `settings-button-icon`, `delete-row-action`…) |
| `iconPosition` |  | `"only-icon"`, `"only-text"`, `"left-icon"` | 792 | `left-icon` / `right-icon` / `only-icon` / `only-text` |
| `iconSize` |  |  |  | (успадковано від базового класу) |
| `isIconModeSizePx` |  |  |  | (успадковано від базового класу) |
| `menuItems` |  | `[]`, `<binding>` | 242 | масив `crt.MenuItem` / `crt.MenuDivider` / `crt.MenuLabel` (слот `menuItems`) або біндінг |
| `menuPanelClass` |  | `"crt-bulk-actions-menu"` | 1 | (успадковано від базового класу) |
| `pressed` |  |  |  | (успадковано від базового класу) |
| `size` |  | `"medium"`, `"large"`, `"small"`, `"extra-large"`, `"none"` | 790 | `small` / `medium` / `large` |
| `textTransform` |  |  |  | (успадковано від базового класу) |
| `title` | `""` |  | 1 | (успадковано від базового класу) |
| `type` |  |  |  | (успадковано від базового класу) |
| `useGlassmorphism` |  | `true` | 1 | (успадковано від базового класу) |
| `classes` |  |  | 48 | (успадковано від базового класу) |
| `id` |  |  |  | (успадковано від базового класу) |
| `loading` |  |  |  | показати спінер замість вмісту |
| `name` |  | `"AddStepButton_"+c.N` | 6 | (успадковано від базового класу) |
| `shape` |  | `rounded` |  | `rounded` |
| `styles` |  |  |  | (успадковано від базового класу) |
| `tabIndex` |  |  |  | (успадковано від базового класу) |

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `blurred` |  |  |
| `clicked` | `"crt.LoadDataRequest"`, `"crt.CreateRecordRequest"`, `"bnz.FullScreenToggleRequest"`, `"crt.DataGridCreateItemRequest"`, `"crt.RunBusinessProcessRequest"`, `"crt.ClosePageRequest"`, `"bnz.RefreshLocationsTreeRequest"`, `"crt.UploadFileRequest"`, `"bnz.ClearActiveRowRequest"`, `"crt.AddCommunicationOptionsRequest"` | `{request: "crt.XRequest", params: {...}}`; для меню-кнопки часто `{}` |
| `focused` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `visible` | 409 | `true`, `<binding>`, `false` | приховане з боку компонента — керується `crtIf` (`"$Attr"` або `"$Attr \| crt.ToBoolean"`) |
| `layoutConfig` | 13 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `defaultLocalizableStrings` | 3 |  | службове поле дизайнера — ключі локалізації, які підставляються при вставці елемента |
| `selected` | 2 | `true` | службовий стан дизайнера (виділення елемента в Page Designer) |
| `params` | 2 |  |  |
| `bindTo` | 1 |  | спільна → [[Common view-element properties#bindTo]] |
| `menu` | 1 | `"default"` |  |
| `H` | 1 | `true` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `clicked.request` | 562 | `"crt.LoadDataRequest"`, `"crt.CreateRecordRequest"`, `"bnz.FullScreenToggleRequest"`, `"crt.DataGridCreateItemRequest"`, `"crt.RunBusinessProcessRequest"`, `"crt.ClosePageRequest"` |  |
| `clicked.params` | 460 | `{}` |  |
| `clicked.params.config` | 233 |  |  |
| `clicked.params.config.loadType` | 233 | `"reload"` |  |
| `clicked.params.dataSourceName` | 220 | `"AddressListDS"`, `"CasesListDS"`, `"RecommendedProductListDS"`, `"OpportunityListDS"`, `"OrderListDS"`, `"ServiceAgreementsListDS"` |  |
| `clicked.params.entityName` | 113 | `"Activity"`, `"Contact"`, `"Case"`, `"Account"`, `"Opportunity"`, `"Order"` |  |
| `clicked.params.defaultValues` | 41 |  |  |
| `clicked.params.defaultValues[].attributeName` | 36 | `"Account"`, `"Contact"`, `"QualifiedContact"`, `"Activity"`, `"QualifiedAccount"`, `"UsrAccount"` |  |
| `clicked.params.defaultValues[].value` | 36 | `<binding>` |  |
| `clicked.params.config.useLastLoadParameters` | 30 | `true` |  |
| `clicked.params.dataGridName` | 20 | `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_e547wcq"`, `"GridDetail_kuczql5"`, `"GridDetail_zm8vrun"`, `"GridDetail_odfqtzv"` |  |
| `clicked.params.insertionIndex` | 20 | `0` |  |
| `clicked.params.manualExecution` | 20 | `true` |  |
| `clicked.params.viewElementName` | 15 | `"CommunicationOptions_i77g6gv"`, `"FileList_v3u1cpz"`, `"FileList_pazhlwo"`, `"ContactCommunicationOptions"`, `"AttachmentList"`, `"AccountCommunicationOptions"` |  |
| `clicked.params.locationTypeName` | 14 | `"User"`, `"Data"`, `"Actual"` |  |
| `clicked.params.processName` | 14 | `"UsrNewBillingLineCP_Main4"`, `"ContactToLeadManualLeadCreation"`, `"UsrSplitBillingLineCPCP_Main1_Freedom"`, `"UsrCpPeerReviewCopyProcess"` |  |
| `clicked.params.processRunType` | 13 | `"ForTheSelectedPage"`, `"RegardlessOfThePage"` |  |
| `clicked.params.recordIdProcessParameterName` | 12 | `"ContactId"`, `"AccountID"`, `"ProcessSchemaParameter1"`, `"Case"`, `"BillingLine"` |  |
| `clicked.params.refreshDataConfig` | 12 |  |  |
| `clicked.params.refreshDataConfig.mode` | 12 | `"RefreshSpecific"`, `"RefreshAll"` |  |
| `clicked.params.refreshDataConfig.targetDataSourceNames` | 9 |  |  |
| `clicked.params.dataGridActiveRowName` | 8 | `"AddressList_ActiveRow"`, `"ContactsList_ActiveRow"` |  |
| `clicked.params.saveAtProcessStart` | 7 | `true` |  |
| `clicked.params.showNotification` | 7 | `true` |  |
| `clicked.params.elementIdName` | 5 | `"AddressExpansionPanel"`, `"ExpansionPanel_nz2nufi"`, `"ContactsExpansionPanel"`, `"ExpansionPanel_d2g9tfo"`, `"ExpansionPanel_u5p336y"` |  |
| `clicked.params.schemaName` | 4 | `"PostponeQueueItemPage"`, `"OAuthSettingsMiniPage"` |  |
| `clicked.params.showSuccessMessage` | 4 | `true`, `false` |  |
| `clicked.params.LocationTypeId` | 3 |  |  |
| `clicked.params.filters` | 3 | `<binding>` |  |
| `clicked.params.joinUrl` | 3 | `<binding>` |  |
| `clicked.params.nodeId` | 3 | `<binding>` |  |
| `clicked.params.recordId` | 3 | `<binding>` |  |
| `clicked.params.viewName` | 3 | `"EventAudience"`, `"DataTable"` |  |
| `clicked.params.activityId` | 2 | `"Id"` |  |
| `clicked.params.app` | 2 | `"digital_ads"` |  |
| `clicked.params.eventId` | 2 | `<binding>` |  |
| `clicked.params.itemsAttributeName` | 2 | `"Items"` |  |
| `clicked.params.modelInitConfigs` | 2 |  |  |
| `clicked.params.modelInitConfigs[].action` | 2 | `"edit"` |  |
| `clicked.params.modelInitConfigs[].recordId` | 2 | `<binding>` |  |
| `clicked.params.platform` | 2 | `"facebook"`, `"google"` |  |
| `clicked.params.queueItemId` | 2 | `<binding>` |  |
| `clicked.params.showBodyMask` | 2 | `true` |  |
| `clicked.params.call` | 1 |  |  |
| `clicked.params.callAccount` | 1 |  |  |
| `clicked.params.callContact` | 1 |  |  |
| `defaultLocalizableStrings.caption` | 3 |  |  |
| `menuItems[].caption` | 3 | `""` |  |
| `menuItems[].type` | 3 | `"crt.MenuItem"`, `"crt.MenuLabel"` |  |
| `menuItems[].clicked` | 2 |  |  |
| `menuItems[].clicked.request` | 2 | `"crt.ExportDataGridToExcelRequest"`, `"crt.AddNextStepRequest"` |  |
| `menuItems[].color` | 2 | `"default"` |  |
| `menuItems[].defaultLocalizableStrings` | 2 |  |  |
| `menuItems[].defaultLocalizableStrings.caption` | 2 | `"NextSteps.CreateActivityButtonCaption"` |  |
| `menuItems[].name` | 2 | `"CreateTaskMenuItem_"+c.N` |  |
| `menuItems[].size` | 2 |  |  |
| `menuItems[].clicked.params` | 1 |  |  |
| `menuItems[].clicked.params.entityName` | 1 | `"Activity"` |  |
| `menuItems[].icon` | 1 | `"export-button-icon"` |  |
| `params.messageTextAfterCompletion` | 2 | `<binding>` |  |
| `params.showSuccessMessage` | 2 | `true` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:10,icon:t(19127),defaultPropertyValues:{caption:"",color:"default",disabled:false},defaultLocalizableStrings:{caption:"Components.Button.Caption"}},propertiesPanelComponentTypeName:"crt.ButtonPropertiesPanel",collectionPropertyNames:["menuItems"],typeCaption:"Components.Button.Caption",viewElementGroupType:u.J.Components}
```

## Приклад з реальної схеми

Джерело: `UsrBillingLines_FormPage.js`

```json
{
					"type": "crt.Button",
					"caption": "#ResourceString(Button_9gjpks0_caption)#",
					"color": "accent",
					"disabled": "$UsrIsSplitBillingLineBtnEnabled | crt.IsEqual : false",
					"size": "large",
					"iconPosition": "only-text",
					"visible": "$UsrIsSplitLineButtonVisible",
					"clicked": {
						"request": "crt.RunBusinessProcessRequest",
						"params": {
							"processName": "UsrSplitBillingLineCPCP_Main1_Freedom",
							"processRunType": "ForTheSelectedPage",
							"saveAtProcessStart": true,
							"showNotification": true,
							"recordIdProcessParameterName": "BillingLine"
						}
					},
					"clickMode": "default"
				}
```

## Пов'язані

[[crt.MenuItem]], [[crt.MenuDivider]], [[crt.MenuLabel]], [[crt.ButtonToggleGroup]], [[crt.Link]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 5899 згадок у конфігах. Мінімізовані імена класів не наводяться.*