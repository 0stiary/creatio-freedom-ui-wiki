---
type: crt.ExpansionPanel
selector: crt-expansion-panel
group: "Layout"
usage_in_configs: 305
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ExpansionPanel

> Розгортна панель (деталь).

Angular-селектор: `<crt-expansion-panel>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`, `tools`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **305** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `ariaLabel` |  |  |  | (успадковано від базового класу) |
| `description` |  |  |  | (успадковано від базового класу) |
| `disableOverflow` |  |  |  | (успадковано від базового класу) |
| `expanded` | `true` | `true`, `false` | 305 | стан; зберігається у профіль (`DisableSaveToProfileExpPanelExpanded`) |
| `extraStyles` |  |  |  | (успадковано від базового класу) |
| `fullWidthHeader` | `true` | `false` | 305 | клікабельний весь хедер |
| `labelColor` |  | `"auto"`, `"#0D2E4E"` | 305 | (успадковано від базового класу) |
| `title` |  | `<binding>` | 305 | заголовок |
| `titleWidth` |  | `20`, `"20"`, `"30"` | 305 | ширина заголовка у % |
| `togglePosition` | `"before"` | `"before"`, `"after"` | 305 | `before` / `after` |
| `toggleType` |  | `default`, `material` · `"default"`, `"material"` | 305 | `default` / `material` |
| `tools` | `[]` | `[]` | 305 | слот для кнопок у хедері |
| `tooltip` |  |  |  | (успадковано від базового класу) |
| `borderRadius` |  |  |  | (успадковано від базового класу) |
| `color` |  |  |  | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` |  |  | (успадковано від базового класу) |
| `fitContent` | `true` | `true`, `false` | 247 | (успадковано від базового класу) |
| `items` | `[]` | `[]` | 305 | (успадковано від базового класу) |
| `padding` |  |  | 305 | (успадковано від базового класу) |
| `responsiveWidth` |  |  |  | (успадковано від базового класу) |
| `stretch` | `false` | `true` | 2 | (успадковано від базового класу) |
| `visiblePadding` | `true` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `closed` |  |  |
| `expandedChange` |  |  |
| `opened` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `visible` | 243 | `true`, `false`, `<binding>` | спільна → [[Common view-element properties#visible]] |
| `alignItems` | 174 | `"stretch"` |  |
| `layoutConfig` | 76 |  | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `layoutConfig.colSpan` | 76 | `1`, `2` |  |
| `layoutConfig.column` | 76 | `1`, `2`, `3` |  |
| `layoutConfig.row` | 76 | `1`, `3`, `2`, `45`, `70`, `40` |  |
| `layoutConfig.rowSpan` | 76 | `1`, `11` |  |
| `padding.bottom` | 305 | `"small"`, `"none"` |  |
| `padding.left` | 305 | `"none"` |  |
| `padding.right` | 305 | `"none"` |  |
| `padding.top` | 305 | `"small"`, `"none"`, `"medium"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:[D({groupType:_.h.LayoutElements,position:10,captionKey:"Components.ExpansionPanel.Caption",icon:t(26819)}),D({groupType:_.h.Components,position:30,id:ut,addCommandTypeName:"crt.CreateExpandedDataGridItemCommand",captionKey:C,hint:"Components.ExpandedList.Hint",icon:t(18430),fullWidthHeader:false,expansionPanelDefaultElements:[{name:v+"_"+c.N,type:"crt.DataGrid",layoutConfig:it(6)}],expansionPanelDefaultTools:[R("add-button-icon","Components.ExpandedList.AddBtnCaption",{request:"crt.CreateRecordRequest"}),J("Components.ExpandedList.RefreshBtnCaption"),{name:v+"SettingsBtn_"+c.N,type:"crt.Button",caption:"",defaultLocalizableStrings:{caption:"Components.ExpandedList.SettingsBtnCaption"},icon:"actions-button-icon",iconPosition:"only-icon",color:"default",size:s.Z.Medium,clickMode:"menu",menuItems:[{name:v+"ExportDataBtn_"+c.N,type:"crt.MenuItem",caption:"",icon:"export-button-icon",color:"default",size:s.Z.Medium,defaultLocalizableStrings:{caption:"Components.ExpandedList.ExportDataBtnCaption"},clicked:{request:"crt.ExportDataGridToExcelRequest"}},{name:v+"ImportDataBtn_"+c.N,type:"crt.MenuItem",caption:"",icon:"import-button-icon",color:"default",size:s.Z.Medium,defaultLocalizableStrings:{caption:"Components.ExpandedList.ImportDataBtnCaption"},clicked:{request:"crt.ImportDataRequest"}}]},$(true)]}),D({groupType:_.h.Components,position:100,addCommandTypeName:"crt.AddCommunicationOptionsCommand",captionKey:"Components.CommunicationOptions.Caption",hint:"Components.CommunicationOptions.Hint",icon:t(97545),fullWidthHeader:false,expansionPanelDefaultElements:[{name:"CommunicationOptions_"+c.N,type:"crt.CommunicationOptions",readonly:true,columnsCount:2,showNoDataPlaceholder:true,labelPosition:"auto",layoutConfig:it(1)}],expansionPanelDefaultTools:[R("add-button
```

## Приклад з реальної схеми

Джерело: `UsrUpdateBillingLines_MiniPage.js`

```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 1,
						"rowSpan": 1
					},
					"type": "crt.ExpansionPanel",
					"tools": [],
					"items": [],
					"title": "#ResourceString(ExpansionPanel_9z70o7n_title)#",
					"toggleType": "default",
					"togglePosition": "before",
					"expanded": true,
					"labelColor": "auto",
					"fullWidthHeader": false,
					"titleWidth": 20,
					"padding": {
						"top": "none",
						"bottom": "none",
						"left": "none",
						"right": "none"
					},
					"fitContent": true,
					"visible": "$IsContactFieldsVisible",
					"alignItems": "stretch"
				}
```

## Нотатки

Препроцесор: обмежує висоту вкладеного `crt.DataGrid` (`setDataGridMaxHeight`), фільтрує items за типом гріда і нормалізує paddings.

## Пов'язані

[[crt.FlexContainer]], [[crt.GridContainer]], [[crt.DataGrid]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 3792 згадок у конфігах. Мінімізовані імена класів не наводяться.*