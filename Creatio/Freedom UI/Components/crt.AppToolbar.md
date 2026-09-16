---
type: crt.AppToolbar
selector: crt-app-toolbar
group: "Shell / службові"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.AppToolbar

Angular-селектор: `<crt-app-toolbar>`  
Група: **Shell / службові**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `communicationItemsInfo` | `[]` | `<binding>` | 2 |  |
| `communicationsPanelHasNewMessages` |  | `<binding>` | 2 |  |
| `currentRightPanelTab` |  |  |  |  |
| `globalSearchVisible` | `true` |  |  |  |
| `helpMenuButtonVisible` | `true` |  |  |  |
| `navigationPanelVisible` | `false` | `<binding>` | 2 |  |
| `notificationsPanelHasNewNotifications` |  | `<binding>` | 2 |  |
| `quickAddMenuButtonVisible` | `true` |  |  |  |
| `rightPanelButtonsVisible` | `true` |  |  |  |
| `runProcessButtonVisible` | `true` |  |  |  |
| `showLegacySidebarsButton` | `false` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `communicationIndicatorClicked` |  |  |
| `createRecord` | `"crt.CreateRecordRequest"` |  |
| `navigationPanelVisibleChange` |  |  |
| `rightPanelButtonClicked` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `communicationIndicatorClicked.params` | 2 |  |  |
| `communicationIndicatorClicked.params.communicationItemInfo` | 2 | `"@event"` |  |
| `communicationIndicatorClicked.request` | 2 |  |  |
| `createRecord.params` | 2 |  |  |
| `createRecord.params.defaultValues` | 2 | `"@event.defaultValues"` |  |
| `createRecord.params.entityName` | 2 | `"@event.entityName"` |  |
| `createRecord.params.entityPageName` | 2 | `"@event.entityPageName"` |  |
| `createRecord.request` | 2 | `"crt.CreateRecordRequest"` |  |
| `navigationPanelVisibleChange.params` | 2 |  |  |
| `navigationPanelVisibleChange.params.isVisible` | 2 | `"@event"` |  |
| `navigationPanelVisibleChange.request` | 2 |  |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_0.js.завантаження`

```json
{type:"crt.AppToolbar",createRecord:{request:"crt.CreateRecordRequest",params:{entityName:"@event.entityName",entityPageName:"@event.entityPageName",defaultValues:"@event.defaultValues"}},navigationPanelVisibleChange:{request:"crt.NavigationPanelChangeVisibleRequest",params:{isVisible:"@event"}},navigationPanelVisible:"$WorkplaceNavigationPanelVisibleAttribute",notificationsPanelHasNewNotifications:"$NotificationsPanelHasNewNotifications",communicationsPanelHasNewMessages:"$CommunicationsPanelHasNewMessages",communicationItemsInfo:"$ActiveCommunicationsInfo",communicationIndicatorClicked:{request:"crt.CommunicationIndicatorClickedRequest",params:{communicationItemInfo:"@event"}}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 14 згадок у конфігах. Мінімізовані імена класів не наводяться.*