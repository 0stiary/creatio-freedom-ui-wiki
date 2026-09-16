---
type: crt.BaseMessageComposer
selector: crt-base-message-composer
group: "Чати / Omnichannel / повідомлення"
usage_in_configs: 0
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.BaseMessageComposer

Angular-селектор: `<crt-base-message-composer>`  
Група: **Чати / Omnichannel / повідомлення**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `channelSelector` |  |  |  |  |
| `composerCacheCode` |  |  |  |  |
| `dataCachingService` |  |  |  |  |
| `disableSelectionOptions` |  |  |  |  |
| `disabled` | `false` |  |  |  |
| `discardBtnVisible` | `false` |  |  |  |
| `footerPanelExpanded` | `false` |  |  |  |
| `footerPanelIndent` | `0` |  |  |  |
| `footerPanelOptions` |  |  |  |  |
| `height` |  |  |  |  |
| `inputPlaceHolder` |  |  |  |  |
| `maxAttachmentsSize` | `0` |  |  |  |
| `mentionsService` |  |  |  |  |
| `selectionActions` |  |  |  |  |
| `sendButtonIcon` |  |  |  |  |
| `sendingButtonDisabled` | `false` |  |  |  |
| `useDrafts` | `false` |  |  |  |
| `useTemplates` | `false` |  |  |  |

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `attachmentAdded` |  |  |
| `composerCleared` |  |  |
| `messageChanged` |  |  |
| `messageChangesCancel` |  |  |
| `messageInputBlur` |  |  |
| `messageInputClick` |  |  |
| `messageInputFocus` |  |  |
| `messagePublish` |  |  |
| `newMention` |  |  |
| `saveDraft` |  |  |
| `selectTemplate` |  |  |
| `selectionChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (3789.hash=c07acffd1a475b43.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*