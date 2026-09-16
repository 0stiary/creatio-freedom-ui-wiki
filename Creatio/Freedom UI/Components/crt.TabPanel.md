---
type: crt.TabPanel
selector: crt-tab-panel-container
group: "Layout"
usage_in_configs: 28
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TabPanel

> Панель вкладок або toggle-панель. Препроцесор розбирає `crt.TabPanel` на `crt.TabPanelHeader` + `crt.ToggleContainer`; більшість «вхідних» властивостей з конфігу читає саме препроцесор, а не компонент.

Angular-селектор: `<crt-tab-panel-container>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **28** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `headerBackgroundColor` |  | `"auto"` | 22 | фон хедера |
| `selectedTab` |  |  | 10 | `{ value: "TabName" }` або біндінг `"$Attr"`; при `ButtonToggleGroup.for` перезаписується на `$<Name>_SelectedItem` |
| `selectedTabIndex` |  |  |  | індекс активної вкладки; зберігається у профіль користувача (вимикається фічею `DisableSaveToProfileSelectedTabIndex`) |
| `styleType` |  | `default`, `fullyColored` · `"default"` | 22 | `default` / `fullyColored` |
| `underlineSelectedTabColor` |  | `"auto"` | 22 | колір підкреслення активної вкладки |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `selectedTabChange` |  | двостороння прив'язка до `selectedTab` (атрибут `<Name>_SelectedItem`) |
| `selectedTabIndexChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `items` | 28 | `[]` | масив `crt.TabContainer` (слот) |
| `mode` | 26 | `"toggle"`, `"tab"` | `"tab"` — класичні вкладки з хедером; `"toggle"` — панель без хедера, перемикається зовнішнім `crt.ButtonToggleGroup { for }` |
| `bodyBackgroundColor` | 24 | `"primary-contrast-500"`, `"primary-contrast-100"` | колір тіла вкладок → `backgroundColor` кожного `crt.ToggleContainerItem` |
| `selectedTabTitleColor` | 22 | `"auto"` | колір активного заголовка |
| `tabTitleColor` | 22 | `"auto"` | колір заголовків (→ `TabPanelHeaderItem.titleColor`) |
| `allowToggleClose` | 18 | `true`, `false` | toggle-режим: чи можна закрити панель повторним кліком (default `true`); → `ToggleContainerItem.allowToggleClose` і `ButtonToggleGroup.allowUntoggle` |
| `fitContent` | 15 | `true`, `false` |  |
| `stretch` | 13 | `true` |  |
| `layoutConfig` | 10 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `isToggleTabHeaderVisible` | 8 | `true`, `false` | **прихована**, toggle-режим, default `true`: показувати `tools` вкладки як заголовок |
| `visible` | 8 | `true` | спільна → [[Common view-element properties#visible]] |
| `visibilityStrategyMode` | 2 | `"hide"` | **прихована**: `"hide"` — при закритті toggle-панелі (`visible=false`) DOM ховається, а не знищується (потрібна фіча `UseHideVisibilityStrategy`) |

Додатково (з коду препроцесорів, у конфігах не зустрілись):

- `preserveContent` — **прихована**, default `true`: неактивні вкладки не знищуються, а ховаються класом `hide` (у `crt.ToggleContainer`)
- `slidingAnimation` — **прихована**, default `false`: анімація перегортання між вкладками

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `layoutConfig.maxWidth` | 5 | `368`, `550` |  |
| `layoutConfig.minWidth` | 5 | `368`, `400` |  |
| `layoutConfig.colSpan` | 2 | `7`, `1` |  |
| `layoutConfig.column` | 2 | `1` |  |
| `layoutConfig.row` | 2 | `2`, `1` |  |
| `layoutConfig.rowSpan` | 2 | `1` |  |
| `layoutConfig.width` | 1 | `368` |  |
| `selectedTab.value` | 10 | `"FeedsTab"`, `"ReminderTab"`, `"ListTabContainer"`, `"FieldMappingTabContainer"`, `"AdAccountsTabContainer"`, `"UsrFilters_TabContainer"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:[{position:20,icon:t(2550),caption:"Components.TabPanel.Caption",defaultPropertyValues:{items:[{defaultLocalizableStrings:{caption:"Components.TabPanel.DefaultTab1Name"},...M.getTabContainerConfig("TabContainer_"+_.N)},{defaultLocalizableStrings:{caption:"Components.TabPanel.DefaultTab2Name"},...M.getTabContainerConfig("TabContainer_"+_.N)}],mode:"tab",styleType:"default",bodyBackgroundColor:i.F.PrimaryContrast500,tabTitleColor:i.F.Auto,selectedTabTitleColor:i.F.Auto,headerBackgroundColor:i.F.Auto,underlineSelectedTabColor:i.F.Auto,fitContent:true}},{position:30,icon:t(71462),caption:"Components.TogglePanel.Caption",hint:"Components.TogglePanel.Hint",defaultPropertyValues:{items:[{defaultLocalizableStrings:{caption:"Components.TabPanel.DefaultTab1Name"},...M.getToggleContainerConfig("TabContainer_"+_.N,"Components.TabPanel.DefaultLabel1Name")},{defaultLocalizableStrings:{caption:"Components.TabPanel.DefaultTab2Name"},...M.getToggleContainerConfig("TabContainer_"+_.N,"Components.TabPanel.DefaultLabel2Name")}],mode:"toggle",fitContent:true}}],designControlConfig:{allowDesignContent:true,defaultValues:D},designViewItemCommands:{delete:"crt.RemoveTabPanelViewItemCommand",copy:"crt.CopyTabPanelViewItemCommand"},propertiesPanelComponentTypeName:"crt.TabPanelPropertiesPanel",viewElementGroupType:g.J.LayoutElements,typeCaption:"Components.TabPanel.Caption"}
```

## Приклад з реальної схеми

Джерело: `Contracts_FormPage.js`

```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 1,
						"rowSpan": 1
					},
					"type": "crt.TabPanel",
					"items": [],
					"mode": "tab",
					"styleType": "default",
					"bodyBackgroundColor": "primary-contrast-500",
					"tabTitleColor": "auto",
					"selectedTabTitleColor": "auto",
					"headerBackgroundColor": "auto",
					"underlineSelectedTabColor": "auto",
					"fitContent": true,
					"allowToggleClose": true
				}
```

## Нотатки

**Що робить препроцесор (`crtOnMetaDataInit`, фіча-вимикач `DisableTabPanelPreprocessing`):**
1. Для кожного `crt.TabContainer` виставляє `iconPosition` (`left-icon`, якщо є `icon`, інакше `only-text`), `iconSource`, `hint = caption`.
2. Будує хедер `crt.TabPanelHeader` з `crt.TabPanelHeaderItem` (беруться `caption, icon, iconPosition, hint, visible…` кожної вкладки).
3. Будує тіло `crt.ToggleContainer { preserveContent ?? true, slidingAnimation ?? false, visibilityStrategyMode, items: [...crt.ToggleContainerItem { backgroundColor: bodyBackgroundColor, allowToggleClose }] }`.
4. У `mode: "toggle"` **замінює** сам TabPanel на цей ToggleContainer (переносяться `name, visible, selectedTab, layoutConfig, stretch, classes, fitContent`).

**Якщо є `crt.ButtonToggleGroup { for: "<Name>" }`** (другий препроцесор, `crtOnModelInit`): створюються атрибути `<Name>_Items` і `<Name>_SelectedItem`, а на панель ставиться `selectedTab: "$<Name>_SelectedItem"` і **`visible: "$<Name>_SelectedItem | crt.ToBoolean"`** — тому закриття toggle-панелі за замовчуванням *знищує* її DOM (`crtIf` у режимі destroy), і при повторному відкритті вміст рендериться заново без подій зміни атрибутів. Ліки: `visibilityStrategyMode: "hide"` або перенесення стану у біндінги.

**Де сама Creatio використовує `visibilityStrategyMode: "hide"`:** у схемі `MainShell` (бандл `_bundle_8x_schema_0`) — `LeftNavigationPanel` (crt.NavigationPanel), `LeftPanelContainer` (crt.FlexContainer) і права панель `crt.TabPanel { mode: "toggle", isToggleTabHeaderVisible: false, visibilityStrategyMode: "hide" }`.

**Подія зміни вкладки** ловиться через `crt.HandleViewModelAttributeChangeRequest` з `attributeName === "<Name>_SelectedItem"` (toggle з ButtonToggleGroup) або власний атрибут у `selectedTab: "$MyAttr"`.

## Пов'язані

[[crt.TabContainer]], [[crt.ToggleContainer]], [[crt.ToggleContainerItem]], [[crt.TabPanelHeader]], [[crt.TabPanelHeaderItem]], [[crt.ButtonToggleGroup]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 280 згадок у конфігах. Мінімізовані імена класів не наводяться.*