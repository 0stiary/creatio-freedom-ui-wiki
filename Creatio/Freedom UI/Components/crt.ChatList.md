---
type: crt.ChatList
selector: crt-chat-list
group: "Чати / Omnichannel / повідомлення"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ChatList

Angular-селектор: `<crt-chat-list>`  
Група: **Чати / Omnichannel / повідомлення**  
Слоти вкладених елементів (`contentSlots`): `chats`  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `chats` | `[]` |  |  |
| `currentPage` |  |  |  |
| `focusedChatId` |  |  |  |
| `isCombinedMode` |  |  |  |
| `menuItems` | `[]` |  |  |
| `searchDisableFeatureName` |  |  |  |
| `searchFilter` |  |  |  |
| `selectedChatId` |  |  |  |
| `showNoDataBlankState` | `true` |  |  |
| `borderRadius` |  |  | (успадковано від базового класу) |
| `color` |  |  | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` |  | (успадковано від базового класу) |
| `fitContent` | `true` |  | (успадковано від базового класу) |
| `items` | `[]` |  | (успадковано від базового класу) |
| `padding` |  |  | (успадковано від базового класу) |
| `responsiveWidth` |  |  | (успадковано від базового класу) |
| `stretch` | `false` |  | (успадковано від базового класу) |
| `visiblePadding` | `true` |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `chatClicked` |  |  |
| `chatsListChange` |  |  |
| `createChatClicked` |  |  |
| `currentPageChange` |  |  |
| `focusedChatIdChange` |  |  |
| `loadData` |  |  |
| `searchFilterChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2656.hash=2360e964a8a68b73.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*