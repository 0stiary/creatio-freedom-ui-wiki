---
type: crt.Chat
selector: crt-chat
group: "Чати / Omnichannel / повідомлення"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Chat

Angular-селектор: `<crt-chat>`  
Група: **Чати / Omnichannel / повідомлення**  
Слоти вкладених елементів (`contentSlots`): `items`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `combinedModeButtonVisible` |  |  |  |
| `combinedModeEnabled` | `true` |  |  |
| `isCombinedMode` |  |  |  |
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
| `changeCombinedMode` |  |  |
| `chatViewInit` |  |  |
| `combinedModeButtonVisibleChange` |  |  |
| `combinedModeEnabledChange` |  |  |
| `openChatSession` |  |  |
| `openChatSessionWithMessage` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{requiredFeatures:{ShowDesignerDemoItems:true},position:261,groupType:U.h.Components,icon:e(15208),hint:"Components.Chat.Hint",defaultPropertyValues:{masterSchemaId:"$Id",items:[]},defaultLocalizableStrings:{caption:"Components.Chat.Caption",label:"Components.Chat.Caption"}},propertiesPanelComponentTypeName:"crt.ChatPropertiesPanel",viewElementGroupType:a.J.Components,typeCaption:"Components.Chat.Caption",designControlConfig:{allowDesignContent:true},designViewItemCommands:{create:"crt.CreateChatCommand"}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2656.hash=2360e964a8a68b73.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*