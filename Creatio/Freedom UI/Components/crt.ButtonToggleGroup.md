---
type: crt.ButtonToggleGroup
selector: crt-button-toggle-group
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ButtonToggleGroup

> Група кнопок-перемикачів. З `for: "<TabPanelName>"` стає «зовнішнім хедером» toggle-панелі.

Angular-селектор: `<crt-button-toggle-group>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `allowUntoggle` | `true` | `false` | чи можна зняти вибір повторним кліком |
| `badgeConfig` |  |  | (успадковано від базового класу) |
| `contentAlign` |  | `"center"` | (успадковано від базового класу) |
| `direction` |  | `"column"` | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `fitContent` | `true` | `true` | (успадковано від базового класу) |
| `gap` |  | `"small"`, `"none"` | (успадковано від базового класу) |
| `iconSize` |  | `"extra-large"` | (успадковано від базового класу) |
| `menuButtonsMode` | `false` |  | (успадковано від базового класу) |
| `size` |  | `"extra-large"`, `"small"` | `small` / `medium` / `large` |
| `toggleViewMode` |  | `"button"` | `button` / `dropdown` (у dropdown `allowUntoggle` примусово false) |
| `value` |  |  | `{value: name}` вибраного елемента |
| `items` |  |  | масив `crt.ButtonToggleGroupItem` або біндінг |

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
| `for` | `"CardToggleTabPanel"`, `"LegacySidePanelItemsTabPanel"`, `"CommunicationsPanelItemsTabPanel"`, `"NotificationsPanelItemsTabPanel"`, `"MainTabPanel"`, `"TabPanel_5mknqd5"`, `"UsrFilters_TabPanel"` | **прихована**: ім'я `crt.TabPanel` (mode toggle). Препроцесор: `items = "$<Name>_Items"`, `value = "$<Name>_SelectedItem"`, панелі ставить `selectedTab`/`visible`; `allowUntoggle = TabPanel.allowToggleClose` |
| `tooltipPosition` |  |  |
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `tooltipPosition.originX` | `"end"` |  |
| `tooltipPosition.originY` | `"center"` |  |
| `tooltipPosition.overlayX` | `"start"` |  |
| `tooltipPosition.overlayY` | `"center"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:null,viewElementGroupType:null,designControlConfig:{allowDesignContent:true,selfSelect:true},designViewItemCommands:{delete:"crt.RemoveButtonToggleGroupViewItemCommand"}}
```

## Приклад з реальної схеми


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

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ButtonToggleGroup** → *BaseButtonToggleGroup* → *BaseToggleGroup* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ButtonToggleGroup** (власні) | — | — |  |
| *BaseButtonToggleGroup* | `allowUntoggle`, `badgeConfig`, `contentAlign`, `direction`, `disabled`, `fitContent`, `gap`, `iconSize`, `menuButtonsMode`, `size`, `toggleViewMode`, `value` | — | `menuButtonsMode, size, iconSize, allowUntoggle, badgeConfig, direction, gap, fitContent, contentAlign, disabled, toggleViewMode`; керує pressed-станом елементів |
| *BaseToggleGroup* | `items` | `valueChange` | `items, value`; `valueChange` |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

## Пов'язані

[[crt.ButtonToggleGroupItem]], [[crt.TabPanel]], [[crt.ToggleContainer]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 75 згадок у конфігах. Мінімізовані імена класів не наводяться.*