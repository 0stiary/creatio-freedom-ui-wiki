---
type: crt.Button
selector: crt-button
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Button

> Кнопка; з `menuItems` + `clickMode: "menu"` стає меню.

Angular-селектор: `<crt-button>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `allowMenuOnDisabled` |  |  | меню доступне навіть коли кнопка disabled |
| `ariaLabel` |  |  | (успадковано від базового класу) |
| `attributes` |  |  | (успадковано від базового класу) |
| `autofocus` |  |  | (успадковано від базового класу) |
| `caption` | `""` | `<binding>`, `"#ResourceString(Button_Data_Import)#"`, `"#ResourceString(ActionButton_caption)#"`, `"#ResourceString(RefreshButtonCaption)#"`, `""`, `"#ResourceString(BackButton)#"`, `"#ResourceString(Button_Back_caption)#"` | (успадковано від базового класу) |
| `clickMode` |  | `default` · `"default"`, `"menu"` | `default` / `menu` |
| `color` |  | `"default"`, `"accent"`, `"outline"`, `"primary"`, `"warn"` | `default` / `primary` / `accent` / `outline` / `warning` |
| `contentAlign` | `"center"` |  | (успадковано від базового класу) |
| `disableRipple` |  |  | (успадковано від базового класу) |
| `disabled` |  | `false`, `<binding>` | біндінг або `true/false` |
| `displayMenuIcon` | `false` |  | (успадковано від базового класу) |
| `displayType` |  | `"text"` | (успадковано від базового класу) |
| `icon` |  | `"actions-button-icon"`, `"reload-icon"`, `"add-button-icon"`, `"reload-button-icon"`, `<binding>`, `"close-button-icon"`, `"copy-icon"`, `"upload-button-icon"` | системна іконка (`add-button-icon`, `reload-button-icon`, `export-button-icon`, `import-button-icon`, `more-button-icon`, `actions-button-icon`, `settings-button-icon`, `delete-row-action`…) |
| `iconPosition` |  | `"only-icon"`, `"only-text"`, `"left-icon"` | `left-icon` / `right-icon` / `only-icon` / `only-text` |
| `iconSize` |  |  | (успадковано від базового класу) |
| `isIconModeSizePx` |  |  | (успадковано від базового класу) |
| `menuItems` |  | `[]`, `<binding>` | масив `crt.MenuItem` / `crt.MenuDivider` / `crt.MenuLabel` (слот `menuItems`) або біндінг |
| `menuPanelClass` |  | `"crt-bulk-actions-menu"` | (успадковано від базового класу) |
| `pressed` |  |  | (успадковано від базового класу) |
| `size` |  | `"medium"`, `"large"`, `"small"`, `"extra-large"`, `"none"` | `small` / `medium` / `large` |
| `textTransform` |  |  | (успадковано від базового класу) |
| `title` | `""` |  | (успадковано від базового класу) |
| `type` |  |  | (успадковано від базового класу) |
| `useGlassmorphism` |  | `true` | (успадковано від базового класу) |
| `classes` |  |  | (успадковано від базового класу) |
| `id` |  |  | (успадковано від базового класу) |
| `loading` |  |  | показати спінер замість вмісту |
| `name` |  | `"AddStepButton_"+c.N` | (успадковано від базового класу) |
| `shape` |  | `rounded` | `rounded` |
| `styles` |  |  | (успадковано від базового класу) |
| `tabIndex` |  |  | (успадковано від базового класу) |

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `blurred` |  |  |
| `clicked` | `"crt.LoadDataRequest"`, `"crt.CreateRecordRequest"`, `"bnz.FullScreenToggleRequest"`, `"crt.DataGridCreateItemRequest"`, `"crt.RunBusinessProcessRequest"`, `"crt.ClosePageRequest"`, `"bnz.RefreshLocationsTreeRequest"`, `"crt.UploadFileRequest"`, `"bnz.ClearActiveRowRequest"`, `"crt.AddCommunicationOptionsRequest"` | `{request: "crt.XRequest", params: {...}}`; для меню-кнопки часто `{}` |
| `focused` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `true`, `<binding>`, `false` | приховане з боку компонента — керується `crtIf` (`"$Attr"` або `"$Attr \| crt.ToBoolean"`) |
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `defaultLocalizableStrings` |  | службове поле дизайнера — ключі локалізації, які підставляються при вставці елемента |
| `selected` | `true` | службовий стан дизайнера (виділення елемента в Page Designer) |
| `params` |  |  |
| `bindTo` |  | спільна → [[Common view-element properties#bindTo]] |
| `menu` | `"default"` |  |
| `H` | `true` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `clicked.request` | `"crt.LoadDataRequest"`, `"crt.CreateRecordRequest"`, `"bnz.FullScreenToggleRequest"`, `"crt.DataGridCreateItemRequest"`, `"crt.RunBusinessProcessRequest"`, `"crt.ClosePageRequest"` |  |
| `clicked.params` | `{}` |  |
| `clicked.params.config` |  |  |
| `clicked.params.config.loadType` | `"reload"` |  |
| `clicked.params.dataSourceName` | `"AddressListDS"`, `"CasesListDS"`, `"RecommendedProductListDS"`, `"OpportunityListDS"`, `"OrderListDS"`, `"ServiceAgreementsListDS"` |  |
| `clicked.params.entityName` | `"Activity"`, `"Contact"`, `"Case"`, `"Account"`, `"Opportunity"`, `"Order"` |  |
| `clicked.params.defaultValues` |  |  |
| `clicked.params.defaultValues[].attributeName` | `"Account"`, `"Contact"`, `"QualifiedContact"`, `"Activity"`, `"QualifiedAccount"`, `"UsrAccount"` |  |
| `clicked.params.defaultValues[].value` | `<binding>` |  |
| `clicked.params.config.useLastLoadParameters` | `true` |  |
| `clicked.params.dataGridName` | `"GridDetail_odku0r4"`, `"GridDetail_7wxmt7n"`, `"GridDetail_e547wcq"`, `"GridDetail_kuczql5"`, `"GridDetail_zm8vrun"`, `"GridDetail_odfqtzv"` |  |
| `clicked.params.insertionIndex` | `0` |  |
| `clicked.params.manualExecution` | `true` |  |
| `clicked.params.viewElementName` | `"CommunicationOptions_i77g6gv"`, `"FileList_v3u1cpz"`, `"FileList_pazhlwo"`, `"ContactCommunicationOptions"`, `"AttachmentList"`, `"AccountCommunicationOptions"` |  |
| `clicked.params.locationTypeName` | `"User"`, `"Data"`, `"Actual"` |  |
| `clicked.params.processName` | `"UsrNewBillingLineCP_Main4"`, `"ContactToLeadManualLeadCreation"`, `"UsrSplitBillingLineCPCP_Main1_Freedom"`, `"UsrCpPeerReviewCopyProcess"` |  |
| `clicked.params.processRunType` | `"ForTheSelectedPage"`, `"RegardlessOfThePage"` |  |
| `clicked.params.recordIdProcessParameterName` | `"ContactId"`, `"AccountID"`, `"ProcessSchemaParameter1"`, `"Case"`, `"BillingLine"` |  |
| `clicked.params.refreshDataConfig` |  |  |
| `clicked.params.refreshDataConfig.mode` | `"RefreshSpecific"`, `"RefreshAll"` |  |
| `clicked.params.refreshDataConfig.targetDataSourceNames` |  |  |
| `clicked.params.dataGridActiveRowName` | `"AddressList_ActiveRow"`, `"ContactsList_ActiveRow"` |  |
| `clicked.params.saveAtProcessStart` | `true` |  |
| `clicked.params.showNotification` | `true` |  |
| `clicked.params.elementIdName` | `"AddressExpansionPanel"`, `"ExpansionPanel_nz2nufi"`, `"ContactsExpansionPanel"`, `"ExpansionPanel_d2g9tfo"`, `"ExpansionPanel_u5p336y"` |  |
| `clicked.params.schemaName` | `"PostponeQueueItemPage"`, `"OAuthSettingsMiniPage"` |  |
| `clicked.params.showSuccessMessage` | `true`, `false` |  |
| `clicked.params.LocationTypeId` |  |  |
| `clicked.params.filters` | `<binding>` |  |
| `clicked.params.joinUrl` | `<binding>` |  |
| `clicked.params.nodeId` | `<binding>` |  |
| `clicked.params.recordId` | `<binding>` |  |
| `clicked.params.viewName` | `"EventAudience"`, `"DataTable"` |  |
| `clicked.params.activityId` | `"Id"` |  |
| `clicked.params.app` | `"digital_ads"` |  |
| `clicked.params.eventId` | `<binding>` |  |
| `clicked.params.itemsAttributeName` | `"Items"` |  |
| `clicked.params.modelInitConfigs` |  |  |
| `clicked.params.modelInitConfigs[].action` | `"edit"` |  |
| `clicked.params.modelInitConfigs[].recordId` | `<binding>` |  |
| `clicked.params.platform` | `"facebook"`, `"google"` |  |
| `clicked.params.queueItemId` | `<binding>` |  |
| `clicked.params.showBodyMask` | `true` |  |
| `clicked.params.call` |  |  |
| `clicked.params.callAccount` |  |  |
| `clicked.params.callContact` |  |  |
| `defaultLocalizableStrings.caption` |  |  |
| `menuItems[].caption` | `""` |  |
| `menuItems[].type` | `"crt.MenuItem"`, `"crt.MenuLabel"` |  |
| `menuItems[].clicked` |  |  |
| `menuItems[].clicked.request` | `"crt.ExportDataGridToExcelRequest"`, `"crt.AddNextStepRequest"` |  |
| `menuItems[].color` | `"default"` |  |
| `menuItems[].defaultLocalizableStrings` |  |  |
| `menuItems[].defaultLocalizableStrings.caption` | `"NextSteps.CreateActivityButtonCaption"` |  |
| `menuItems[].name` | `"CreateTaskMenuItem_"+c.N` |  |
| `menuItems[].size` |  |  |
| `menuItems[].clicked.params` |  |  |
| `menuItems[].clicked.params.entityName` | `"Activity"` |  |
| `menuItems[].icon` | `"export-button-icon"` |  |
| `params.messageTextAfterCompletion` | `<binding>` |  |
| `params.showSuccessMessage` | `true` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:10,icon:t(19127),defaultPropertyValues:{caption:"",color:"default",disabled:false},defaultLocalizableStrings:{caption:"Components.Button.Caption"}},propertiesPanelComponentTypeName:"crt.ButtonPropertiesPanel",collectionPropertyNames:["menuItems"],typeCaption:"Components.Button.Caption",viewElementGroupType:u.J.Components}
```

## Приклад з реальної схеми


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