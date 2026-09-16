---
type: crt.AppToolbar
selector: crt-app-toolbar
group: "Shell / службові"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.AppToolbar

Angular-селектор: `<crt-app-toolbar>`  
Група: **Shell / службові**  
reuseStrategy: `Reuse`  
`classes`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `communicationItemsInfo` | `[]` | `<binding>` |  |
| `communicationsPanelHasNewMessages` |  | `<binding>` |  |
| `currentRightPanelTab` |  |  |  |
| `globalSearchVisible` | `true` |  |  |
| `helpMenuButtonVisible` | `true` |  |  |
| `navigationPanelVisible` | `false` | `<binding>` |  |
| `notificationsPanelHasNewNotifications` |  | `<binding>` |  |
| `quickAddMenuButtonVisible` | `true` |  |  |
| `rightPanelButtonsVisible` | `true` |  |  |
| `runProcessButtonVisible` | `true` |  |  |
| `showLegacySidebarsButton` | `false` |  |  |

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

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `communicationIndicatorClicked.params` |  |  |
| `communicationIndicatorClicked.params.communicationItemInfo` | `"@event"` |  |
| `communicationIndicatorClicked.request` |  |  |
| `createRecord.params` |  |  |
| `createRecord.params.defaultValues` | `"@event.defaultValues"` |  |
| `createRecord.params.entityName` | `"@event.entityName"` |  |
| `createRecord.params.entityPageName` | `"@event.entityPageName"` |  |
| `createRecord.request` | `"crt.CreateRecordRequest"` |  |
| `navigationPanelVisibleChange.params` |  |  |
| `navigationPanelVisibleChange.params.isVisible` | `"@event"` |  |
| `navigationPanelVisibleChange.request` |  |  |

## Приклад з реальної схеми


```json
{type:"crt.AppToolbar",createRecord:{request:"crt.CreateRecordRequest",params:{entityName:"@event.entityName",entityPageName:"@event.entityPageName",defaultValues:"@event.defaultValues"}},navigationPanelVisibleChange:{request:"crt.NavigationPanelChangeVisibleRequest",params:{isVisible:"@event"}},navigationPanelVisible:"$WorkplaceNavigationPanelVisibleAttribute",notificationsPanelHasNewNotifications:"$NotificationsPanelHasNewNotifications",communicationsPanelHasNewMessages:"$CommunicationsPanelHasNewMessages",communicationItemsInfo:"$ActiveCommunicationsInfo",communicationIndicatorClicked:{request:"crt.CommunicationIndicatorClickedRequest",params:{communicationItemInfo:"@event"}}}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.AppToolbar** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.AppToolbar** (власні) | `communicationItemsInfo`, `communicationsPanelHasNewMessages`, `currentRightPanelTab`, `globalSearchVisible`, `helpMenuButtonVisible`, `navigationPanelVisible`, `notificationsPanelHasNewNotifications`, `quickAddMenuButtonVisible`, `rightPanelButtonsVisible`, `runProcessButtonVisible`, `showLegacySidebarsButton` | `communicationIndicatorClicked`, `createRecord`, `navigationPanelVisibleChange`, `rightPanelButtonClicked` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 14 згадок у конфігах. Мінімізовані імена класів не наводяться.*