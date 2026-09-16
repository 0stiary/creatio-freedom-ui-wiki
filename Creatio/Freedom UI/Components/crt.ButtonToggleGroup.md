---
type: crt.ButtonToggleGroup
selector: crt-button-toggle-group
group: "Базові компоненти"
usage_in_configs: 16
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ButtonToggleGroup

> Група кнопок-перемикачів. З `for: "<TabPanelName>"` стає «зовнішнім хедером» toggle-панелі.

Angular-селектор: `<crt-button-toggle-group>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **16** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `allowUntoggle` | `true` | `false` | 8 | чи можна зняти вибір повторним кліком |
| `badgeConfig` |  |  |  | (успадковано від базового класу) |
| `contentAlign` |  | `"center"` | 6 | (успадковано від базового класу) |
| `direction` |  | `"column"` | 6 | (успадковано від базового класу) |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `fitContent` | `true` | `true` | 7 | (успадковано від базового класу) |
| `gap` |  | `"small"`, `"none"` | 6 | (успадковано від базового класу) |
| `iconSize` |  | `"extra-large"` | 6 | (успадковано від базового класу) |
| `menuButtonsMode` | `false` |  |  | (успадковано від базового класу) |
| `size` |  | `"extra-large"`, `"small"` | 8 | `small` / `medium` / `large` |
| `toggleViewMode` |  | `"button"` | 5 | `button` / `dropdown` (у dropdown `allowUntoggle` примусово false) |
| `value` |  |  |  | `{value: name}` вибраного елемента |
| `items` |  |  |  | масив `crt.ButtonToggleGroupItem` або біндінг |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `valueChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `for` | 16 | `"CardToggleTabPanel"`, `"LegacySidePanelItemsTabPanel"`, `"CommunicationsPanelItemsTabPanel"`, `"NotificationsPanelItemsTabPanel"`, `"MainTabPanel"`, `"TabPanel_5mknqd5"`, `"UsrFilters_TabPanel"` | **прихована**: ім'я `crt.TabPanel` (mode toggle). Препроцесор: `items = "$<Name>_Items"`, `value = "$<Name>_SelectedItem"`, панелі ставить `selectedTab`/`visible`; `allowUntoggle = TabPanel.allowToggleClose` |
| `tooltipPosition` | 6 |  |  |
| `layoutConfig` | 1 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `tooltipPosition.originX` | 6 | `"end"` |  |
| `tooltipPosition.originY` | 6 | `"center"` |  |
| `tooltipPosition.overlayX` | 6 | `"start"` |  |
| `tooltipPosition.overlayY` | 6 | `"center"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:null,viewElementGroupType:null,designControlConfig:{allowDesignContent:true,selfSelect:true},designViewItemCommands:{delete:"crt.RemoveButtonToggleGroupViewItemCommand"}}
```

## Приклад з реальної схеми

Джерело: `UsrOpenCaseSection_ListPage.js`

```json
{
					"for": "TabPanel_5mknqd5",
					"fitContent": true,
					"toggleViewMode": "button",
					"type": "crt.ButtonToggleGroup"
				}
```

## Нотатки

Вибір зберігається у профіль (`DisableSaveToProfileToggleGroupSelectedTab`). Ліцензійні вкладки (`CtiTab`, `EmailsTab`, `ChatsTab`) прибираються автоматично, якщо немає ліцензії.

## Пов'язані

[[crt.ButtonToggleGroupItem]], [[crt.TabPanel]], [[crt.ToggleContainer]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 75 згадок у конфігах. Мінімізовані імена класів не наводяться.*