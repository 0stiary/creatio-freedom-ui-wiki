---
type: crt.FeedItem
selector: crt-feed-item
group: "Timeline / Feed / Файли"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FeedItem

Angular-селектор: `<crt-feed-item>`  
Група: **Timeline / Feed / Файли**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `allowExternalPost` |  |  |  |
| `customVisibleItemActionsMenu` |  |  |  |
| `disableLikesComments` | `false` |  |  |
| `disableSelectionOptions` |  |  |  |
| `feedType` |  |  |  |
| `isDraftItem` | `false` |  |  |
| `isEditMode` | `false` |  |  |
| `isTheLastComment` | `false` |  |  |
| `item` |  |  |  |
| `itemActionItems` |  |  |  |
| `readingMode` |  |  |  |
| `schemaName` |  |  |  |
| `showMenuActionItems` | `true` |  |  |
| `useCustomHead` | `false` |  |  |
| `useCustomPhoto` | `false` |  |  |

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `messageDeleted` |  |  |
| `messageEdited` |  |  |
| `selectionChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (9596.hash=3da76c6a0b1e195f.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*