---
type: crt.TabContainer
selector: crt-tab
group: "Layout"
usage_in_configs: 169
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TabContainer

> Одна вкладка всередині `crt.TabPanel`. Має слоти `items` (вміст) і `tools` (елементи хедера/заголовка).

Angular-селектор: `<crt-tab>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **169** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `tools` | `[]` | `[]` | 52 | елементи, що рендеряться у хедері toggle-панелі (`isToggleTabHeaderVisible`) — зазвичай `crt.FlexContainer` з `crt.Label`+кнопки |
| `borderRadius` |  |  |  | (успадковано від базового класу) |
| `color` |  |  |  | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` |  |  | (успадковано від базового класу) |
| `fitContent` | `true` |  |  | (успадковано від базового класу) |
| `items` | `[]` | `[]` | 169 | (успадковано від базового класу) |
| `padding` |  |  | 4 | внутрішні відступи (`{top,right,bottom,left}` = none/small/medium/large) |
| `responsiveWidth` |  |  |  | (успадковано від базового класу) |
| `stretch` | `false` |  |  | (успадковано від базового класу) |
| `visiblePadding` | `true` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `iconPosition` | 164 | `"only-text"`, `"only-icon"`, `"left-icon"` | `left-icon` / `only-icon` / `only-text`; якщо не задано — обчислюється з наявності `icon` |
| `caption` | 162 | `<binding>`, `""`, `"#ResourceString(TimelineTab_caption)#"`, `"#ResourceString(ServiceTab_caption)#"`, `"#ResourceString(SalesTab_caption)#"`, `"Notifications"`, `"#ResourceString(MarketingTab_caption)#"` | **читає препроцесор TabPanel** → заголовок вкладки (`TabPanelHeaderItem.caption`); також стає `hint` |
| `visible` | 145 | `true`, `<binding>`, `false` | приховує і вкладку, і її заголовок |
| `icon` | 50 | `"tiles-tab-icon"`, `"open-book-tab-icon"`, `"settings-tab-icon"`, `"right-panel-feeds"`, `"right-panel-calls"`, `"right-panel-emails"`, `"right-panel-chats"`, `"bell-tab-icon"` | іконка вкладки (системна назва або URL) |
| `title` | 20 | `<binding>`, `"#ResourceString(FeedsTab_caption)#"`, `"#ResourceString(CtiTab_caption)#"`, `"#ResourceString(EmailsTab_caption)#"`, `"#ResourceString(ChatsTab_caption)#"`, `"#ResourceString(ReminderTab_caption)#"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `items[].items` | 3 | `[]` |  |
| `items[].name` | 3 | `"GridContainer_"+_.N`, `"MainTabContainer_"+_.N`, `"FlexContainer_"+_.N` |  |
| `items[].type` | 3 | `"crt.GridContainer"`, `"crt.FlexContainer"` |  |
| `items[].gap` | 2 |  |  |
| `items[].gap.rowGap` | 2 | `0` |  |
| `items[].alignItems` | 1 | `"stretch"` |  |
| `items[].columns` | 1 |  |  |
| `items[].direction` | 1 | `"column"` |  |
| `items[].gap.columnGap` | 1 | `"large"` |  |
| `items[].items[].name` | 1 | `"GridContainer_"+_.N` |  |
| `items[].items[].type` | 1 | `"crt.GridContainer"` |  |
| `items[].padding` | 1 |  |  |
| `items[].padding.bottom` | 1 |  |  |
| `items[].rows` | 1 | `"minmax(32px, max-content)"` |  |
| `padding.bottom` | 4 | `"none"`, `"extra-small"` |  |
| `padding.left` | 4 | `"none"`, `"large"` |  |
| `padding.right` | 4 | `"none"`, `"large"` |  |
| `padding.top` | 4 | `"none"`, `"extra-small"` |  |
| `tools[].alignItems` | 1 | `"center"` |  |
| `tools[].direction` | 1 | `"row"` |  |
| `tools[].items` | 1 |  |  |
| `tools[].items[].caption` | 1 | `""` |  |
| `tools[].items[].defaultLocalizableStrings` | 1 |  |  |
| `tools[].items[].defaultLocalizableStrings.caption` | 1 |  |  |
| `tools[].items[].labelBackgroundColor` | 1 | `"transparent"` |  |
| `tools[].items[].labelColor` | 1 | `"#0D2E4E"` |  |
| `tools[].items[].labelEllipsis` | 1 | `false` |  |
| `tools[].items[].labelTextAlign` | 1 | `"start"` |  |
| `tools[].items[].labelThickness` | 1 | `"default"` |  |
| `tools[].items[].labelType` | 1 | `"headline-3"` |  |
| `tools[].items[].name` | 1 | `"Label_"+_.N` |  |
| `tools[].items[].type` | 1 | `"crt.Label"` |  |
| `tools[].name` | 1 | `"FlexContainer_"+_.N` |  |
| `tools[].type` | 1 | `"crt.FlexContainer"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{propertiesPanelComponentTypeName:"crt.TabItemPropertiesPanel",viewElementGroupType:m.J.LayoutElements,typeCaption:"TypeCaptions.TabContainer",collectionPropertyNames:["items","tools"],designControlConfig:{selfSelect:false}}
```

## Приклад з реальної схеми

Джерело: `UsrBillingLines_FormPage.js`

```json
{
					"type": "crt.TabContainer",
					"items": [],
					"caption": "#ResourceString(TabContainer_9dmsc7n_caption)#",
					"iconPosition": "only-text",
					"visible": "$UsrIsSystemAdministrator"
				}
```

## Нотатки

Іконки: системні імена (`contact-icon`, `catalog`, `dashboards-icon`, `filter-column-icon`, …) або URL/data-URI (`iconSource` = system-icon | url).

## Пов'язані

[[crt.TabPanel]], [[crt.ToggleContainerItem]], [[crt.TabPanelHeaderItem]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 770 згадок у конфігах. Мінімізовані імена класів не наводяться.*