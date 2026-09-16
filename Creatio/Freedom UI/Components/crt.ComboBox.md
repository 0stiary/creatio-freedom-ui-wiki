---
type: crt.ComboBox
selector: crt-combobox
group: "Поля вводу"
usage_in_configs: 465
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ComboBox

> Поле-довідник (lookup) / список.

Angular-селектор: `<crt-combobox>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **465** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `autofocus` |  |  |  |  |
| `controlActions` |  | `[]` | 464 | дії праворуч від поля |
| `debounceTime` | `500` |  |  |  |
| `disabled` |  |  |  |  |
| `filteringFn` |  |  |  |  |
| `groupControlActions` |  |  |  |  |
| `isAddAllowed` | `false` | `true`, `false` | 364 | показувати дію «Додати» (`crt.CreateRecordFromLookupRequest`) |
| `isGoToSourceAllowed` | `false` |  |  |  |
| `items` |  | `<binding>` | 3 | статичний список `{value, displayValue}` замість довідника |
| `linkViewConfig` |  |  |  |  |
| `listActions` |  | `[]` | 464 | дії у списку — `crt.ComboboxSearchTextAction` (`addRecord`), слот |
| `mode` |  | `"List"` | 45 | `List` (випадаючий список) / `Lookup` (вікно вибору) |
| `readonly` |  | `true`, `false`, `<binding>` | 148 |  |
| `showSecondaryDisplayValue` |  |  |  |  |
| `showValueAsLink` | `false` | `true`, `false` | 464 | значення як посилання на запис |
| `sortFilteringFn` |  |  |  |  |
| `tooltipConfig` |  |  |  |  |
| `useMultiChoice` | `false` | `true` | 2 | мультивибір |
| `useStaticFiltering` |  | `true` | 1 | фільтрувати статичний `items` на клієнті |
| `value` |  | `<binding>` | 2 |  |
| `valueDetails` |  | `null` | 24 | додаткові дані значення (null) |
| `appearance` | `"legacy"` | `legacy`, `outline` |  | `legacy` / `outline` |
| `ariaLabel` | `""` | `""`, `<binding>` | 365 | (успадковано від базового класу) |
| `control` |  | `<binding>` | 462 | `"$PDS_Column_hash"` — атрибут значення; препроцесор створює список `"$…_List"` (isCollection) і `formControlConfig` |
| `label` | `""` | `<binding>` | 464 | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"`, `"left"`, `"hidden"` | 465 | `auto` / `above` / `left` |
| `placeholder` |  | `""`, `<binding>`, `"#ResourceString(Type_placeholder)#"`, `"#ResourceString(Owner_placeholder)#"`, `"#ResourceString(Account_placeholder)#"`, `"#ResourceString(Gender_placeholder)#"`, `"#ResourceString(Language_placeholder)#"`, `"#ResourceString(Industry_placeholder)#"` | 206 | (успадковано від базового класу) |
| `tooltip` |  | `""`, `<binding>` | 432 | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `addRecord` |  |  |
| `closed` |  |  |
| `goToSource` |  |  |
| `opened` |  |  |
| `paginationChange` |  |  |
| `selectionWindowIconPressed` |  |  |
| `showList` |  |  |
| `valueChange` |  |  |
| `blurred` |  |  |
| `focused` |  |  |
| `keyDown` |  |  |
| `keyUp` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 371 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 206 | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `secondaryDisplayValue` | 5 | `"Description"`, `null` |  |
| `isSimpleLookup` | 2 | `null` | **прихована**: спрощений lookup (без вікна вибору) |
| `formControlConfig` | 1 |  | **прихована**, генерується препроцесором (валідатори) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |
| `layoutConfig.colSpan` | 355 | `1`, `2` |  |
| `layoutConfig.column` | 355 | `1`, `2`, `4`, `3` |  |
| `layoutConfig.row` | 355 | `2`, `1`, `3`, `4`, `6`, `5` |  |
| `layoutConfig.rowSpan` | 355 | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:10,icon:t(7585),defaultPropertyValues:{label:"",ariaLabel:"",isAddAllowed:true,showValueAsLink:true,labelPosition:"auto",controlActions:[],listActions:[{...I.K,name:"addRecord_"+D.N,defaultLocalizableStrings:{caption:"Components.Combobox.AddNewRecord"}}],tooltip:""},defaultLocalizableStrings:{label:"Components.Combobox.Caption",ariaLabel:"Components.Combobox.Caption"}},designViewItemCommands:{copy:"crt.CopyComboBoxViewItemCommand",delete:"crt.RemoveComboBoxViewItemCommand"},dataValueTypes:[l.r.Lookup],propertiesPanelComponentTypeName:"crt.ComboboxPropertiesPanelComponent",collectionPropertyNames:["listActions","controlActions"],viewElementGroupType:m.J.Inputs,typeCaption:"Components.Combobox.Caption"}
```

## Приклад з реальної схеми

Джерело: `UsrPendingLines_FormPage.js`

```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 10,
						"rowSpan": 1
					},
					"type": "crt.ComboBox",
					"label": "$Resources.Strings.PageParameters_UsrLookupParameter5_h0x8v8y",
					"ariaLabel": "",
					"isAddAllowed": true,
					"showValueAsLink": true,
					"labelPosition": "auto",
					"controlActions": [],
					"listActions": [],
					"tooltip": "",
					"control": "$PageParameters_UsrLookupParameter5_h0x8v8y",
					"mode": "List",
					"visible": true,
					"readonly": true,
					"placeholder": "",
					"valueDetails": null
				}
```

## Нотатки

Фільтрація списку/вікна: перехоплюйте `crt.LoadDataRequest` (для `dataSourceName === "<Attr>_List_DS"` додайте `request.parameters.push({type:"filter", value})`) та `crt.OpenSelectionWindowRequest` (`request.filtersConfig.filterAttributes.push({name:'X'})`, `attributesConfig.X = {value: filterGroup}`). Значення атрибута — `{value: guid, displayValue}`.

## Пов'язані

[[crt.ComboboxSearchTextAction]], [[crt.ComboboxAction]], [[crt.MultiSelect]], [[crt.TagSelect]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 4960 згадок у конфігах. Мінімізовані імена класів не наводяться.*