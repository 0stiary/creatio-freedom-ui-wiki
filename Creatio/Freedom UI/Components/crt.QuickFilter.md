---
type: crt.QuickFilter
selector: crt-quick-filter
group: "Фільтри"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.QuickFilter

> Швидкий фільтр (lookup / date-range / custom) над гридом. Уся «магія» — у прихованому `_filterOptions`.

Angular-селектор: `<crt-quick-filter>`  
Група: **Фільтри**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `config` |  |  | lookup: `{caption, hint, icon, iconPosition, entitySchemaName, defaultValue: [] \| [{value:"[#currentUserContact#]", checkedState:true}], recordsFilter}`; date-range: `{…, defaultValue:"[#currentMonth#]", showTime, showFiscalPeriods}`; custom: `{caption, defaultValue:false, approachState}` |
| `filterType` |  | `"lookup"`, `"custom"`, `"date-range"` | `lookup` (довідник), `date-range` (період), `custom` (перемикач з готовим фільтром) |
| `value` |  |  | `"$<Name>_Value"` — поточне значення (генерується) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `valueChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `_filterOptions` |  | **прихована**: `{ from: "<Name>_Value", expose: [{ attribute: "<Name>_<Grid>", converters: [{ converter: "crt.QuickFilterAttributeConverter", args: [{ target: { viewAttributeName: "<Grid>", filterColumn \| filterColumnStart+filterColumnEnd \| customFilter }, quickFilterType, config }] }] }] }` — препроцесор створює exposed-атрибут-фільтр і його треба додати в `filterAttributes` колекції гріда |
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_filterOptions.expose` | `[]` |  |
| `_filterOptions.from` | `"QuickFilter_Country_Value"`, `"QuickFilter_GroupVIP_Value"`, `"QuickFilter_Group_Value"`, `"QuickFilter_Region_Value"`, `"QuickFilter_RecordType_Value"`, `"QuickFilter_UsrRegion_Value"` |  |
| `_filterOptions.expose[].attribute` | `"LookupQuickFilterByTag_Items"`, `"QuickFilter_hcx58uh_GridDetail_kuczql5"`, `"AddContactsQuickFilter_EventAudience"`, `"QuickFilter_Country_Items"`, `"QuickFilter_GroupVIP_Items"`, `"QuickFilter_Group_Items"` |  |
| `_filterOptions.expose[].converters` |  |  |
| `_filterOptions.expose[].converters[].args` |  |  |
| `_filterOptions.expose[].converters[].converter` | `"crt.QuickFilterAttributeConverter"` |  |
| `config.caption` | `<binding>` |  |
| `config.hint` | `""`, `<binding>` |  |
| `config.icon` | `"filter-column-icon"`, `"settings-button-icon"`, `"date"`, `"tag-icon"`, `"person-button-icon"`, `"filter-funnel-icon"` |  |
| `config.iconPosition` | `"left-icon"` |  |
| `config.defaultValue` | `[]`, `false`, `"[#currentMonth#]"`, `"[#currentWeek#]"`, `true`, `null` |  |
| `config.entitySchemaName` | `"Account"`, `"Contact"`, `"UsrCaseSubCategory"`, `"UsrCaseWorkflow"`, `"UsrAccountGroup"`, `"UsrVIPGroup"` |  |
| `config.recordsFilter` | `null` |  |
| `config.approachState` | `false`, `true` |  |
| `config.recordsFilter.filterType` | `6` |  |
| `config.recordsFilter.isEnabled` | `true` |  |
| `config.recordsFilter.items` |  |  |
| `config.recordsFilter.logicalOperation` | `0` |  |
| `config.recordsFilter.rootSchemaName` | `"UsrCaseSubCategory"`, `"Contact"`, `"SysAdminUnit"` |  |
| `config.showFiscalPeriods` | `false` |  |
| `config.showTime` | `false` |  |
| `config.defaultValue[].checkedState` | `true` |  |
| `config.defaultValue[].value` | `"[#currentUserContact#]"`, `"[#currentUserAccount#]"` |  |
| `layoutConfig.colSpan` | `1`, `12`, `4`, `2` |  |
| `layoutConfig.column` | `1`, `2`, `3`, `4`, `5`, `6` |  |
| `layoutConfig.row` | `1`, `2`, `3`, `4`, `11` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:170,icon:t(47924),defaultPropertyValues:{config:{caption:""}},defaultLocalizableStrings:{config:{caption:"Components.QuickFilter.Caption"}}},designViewItemCommands:{create:"crt.AddQuickFilterViewItemCommand",update:"crt.ChangeFilterViewItemCommand",delete:"crt.RemoveFilterViewItemCommand",copy:"crt.CopyQuickFilterViewItemCommand"},propertiesPanelComponentTypeName:"crt.QuickFilterPropertiesPanel",viewElementGroupType:s.J.Components,typeCaption:"Components.QuickFilter.Caption",placeholderSize:{height:"16px"}}
```

## Приклад з реальної схеми


```json
{
					"layoutConfig": {
						"column": 4,
						"colSpan": 1,
						"row": 1,
						"rowSpan": 1
					},
					"type": "crt.QuickFilter",
					"config": {
						"caption": "#ResourceString(QuickFilter_6vi5s1m_config_caption)#",
						"hint": "",
						"icon": "date",
						"iconPosition": "left-icon"
					},
					"_filterOptions": {
						"expose": [
							{
								"attribute": "QuickFilter_6vi5s1m_Items",
								"converters": [
									{
										"converter": "crt.QuickFilterAttributeConverter",
										"args": [
											{
												"target": {
													"viewAttributeName": "Items",
													"filterColumn": "UsrRenewalDay"
												},
												"quickFilterType": "date-range"
											}
										]
									}
								]
							}
						],
						"from": "QuickFilter_6vi5s1m_Value"
					},
					"filterType": "date-range"
				}
```

## Нотатки

Макроси у `defaultValue`: `[#currentUserContact#]`, `[#currentUserAccount#]`, `[#currentMonth#]`, `[#currentWeek#]`. Значення lookup-фільтра — масив `{value, displayValue, checkedState}`.

## Пов'язані

[[crt.SearchFilter]], [[crt.FolderTree]], [[crt.DataGrid]], [[crt.LookupQuickFilterMenuItem]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (3681.hash=5b6e27ea9c707070.js) + 937 згадок у конфігах. Мінімізовані імена класів не наводяться.*