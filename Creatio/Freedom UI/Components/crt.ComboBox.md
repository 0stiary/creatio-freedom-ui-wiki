---
type: crt.ComboBox
selector: crt-combobox
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ComboBox

> Поле-довідник (lookup) / список.

Angular-селектор: `<crt-combobox>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `autofocus` |  |  |  |
| `controlActions` |  | `[]` | дії праворуч від поля |
| `debounceTime` | `500` |  |  |
| `disabled` |  |  |  |
| `filteringFn` |  |  |  |
| `groupControlActions` |  |  |  |
| `isAddAllowed` | `false` | `true`, `false` | показувати дію «Додати» (`crt.CreateRecordFromLookupRequest`) |
| `isGoToSourceAllowed` | `false` |  |  |
| `items` |  | `<binding>` | статичний список `{value, displayValue}` замість довідника |
| `linkViewConfig` |  |  |  |
| `listActions` |  | `[]` | дії у списку — `crt.ComboboxSearchTextAction` (`addRecord`), слот |
| `mode` |  | `"List"` | `List` (випадаючий список) / `Lookup` (вікно вибору) |
| `readonly` |  | `true`, `false`, `<binding>` |  |
| `showSecondaryDisplayValue` |  |  |  |
| `showValueAsLink` | `false` | `true`, `false` | значення як посилання на запис |
| `sortFilteringFn` |  |  |  |
| `tooltipConfig` |  |  |  |
| `useMultiChoice` | `false` | `true` | мультивибір |
| `useStaticFiltering` |  | `true` | фільтрувати статичний `items` на клієнті |
| `value` |  | `<binding>` |  |
| `valueDetails` |  | `null` | додаткові дані значення (null) |
| `appearance` | `"legacy"` | `legacy`, `outline` | `legacy` / `outline` |
| `ariaLabel` | `""` | `""`, `<binding>` | (успадковано від базового класу) |
| `control` |  | `<binding>` | `"$PDS_Column_hash"` — атрибут значення; препроцесор створює список `"$…_List"` (isCollection) і `formControlConfig` |
| `label` | `""` | `<binding>` | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"`, `"left"`, `"hidden"` | `auto` / `above` / `left` |
| `placeholder` |  | `""`, `<binding>`, `"#ResourceString(Type_placeholder)#"`, `"#ResourceString(Owner_placeholder)#"`, `"#ResourceString(Account_placeholder)#"`, `"#ResourceString(Gender_placeholder)#"`, `"#ResourceString(Language_placeholder)#"`, `"#ResourceString(Industry_placeholder)#"` | (успадковано від базового класу) |
| `tooltip` |  | `""`, `<binding>` | (успадковано від базового класу) |

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

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `secondaryDisplayValue` | `"Description"`, `null` |  |
| `isSimpleLookup` | `null` | **прихована**: спрощений lookup (без вікна вибору) |
| `formControlConfig` |  | **прихована**, генерується препроцесором (валідатори) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `formControlConfig.relatesTo` | `"control"` |  |
| `layoutConfig.colSpan` | `1`, `2` |  |
| `layoutConfig.column` | `1`, `2`, `4`, `3` |  |
| `layoutConfig.row` | `2`, `1`, `3`, `4`, `6`, `5` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:10,icon:t(7585),defaultPropertyValues:{label:"",ariaLabel:"",isAddAllowed:true,showValueAsLink:true,labelPosition:"auto",controlActions:[],listActions:[{...I.K,name:"addRecord_"+D.N,defaultLocalizableStrings:{caption:"Components.Combobox.AddNewRecord"}}],tooltip:""},defaultLocalizableStrings:{label:"Components.Combobox.Caption",ariaLabel:"Components.Combobox.Caption"}},designViewItemCommands:{copy:"crt.CopyComboBoxViewItemCommand",delete:"crt.RemoveComboBoxViewItemCommand"},dataValueTypes:[l.r.Lookup],propertiesPanelComponentTypeName:"crt.ComboboxPropertiesPanelComponent",collectionPropertyNames:["listActions","controlActions"],viewElementGroupType:m.J.Inputs,typeCaption:"Components.Combobox.Caption"}
```

## Приклад з реальної схеми


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

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ComboBox** → *BaseFormControl* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ComboBox** (власні) | `autofocus`, `controlActions`, `debounceTime`, `disabled`, `filteringFn`, `groupControlActions`, `isAddAllowed`, `isGoToSourceAllowed`, `items`, `linkViewConfig`, `listActions`, `mode`, `readonly`, `showSecondaryDisplayValue`, `showValueAsLink`, `sortFilteringFn`, `tooltipConfig`, `useMultiChoice`, `useStaticFiltering`, `value`, `valueDetails` | `addRecord`, `closed`, `goToSource`, `opened`, `paginationChange`, `selectionWindowIconPressed`, `showList`, `valueChange` |  |
| *BaseFormControl* | `appearance`, `ariaLabel`, `control`, `label`, `labelPosition`, `placeholder`, `tooltip` | `blurred`, `focused`, `keyDown`, `keyUp` | поле форми: `label, ariaLabel, appearance, placeholder, disabled, tooltip, control, labelPosition`; події `keyUp, keyDown, blurred, focused`; зв'язок з FormControl (`_initControl`, required, disabled state) |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

## Пов'язані

[[crt.ComboboxSearchTextAction]], [[crt.ComboboxAction]], [[crt.MultiSelect]], [[crt.TagSelect]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 4960 згадок у конфігах. Мінімізовані імена класів не наводяться.*