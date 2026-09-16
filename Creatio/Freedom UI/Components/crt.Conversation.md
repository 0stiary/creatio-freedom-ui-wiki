---
type: crt.Conversation
selector: crt-conversation
group: "Layout"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Conversation

Angular-селектор: `<crt-conversation>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `actions`, `information`, `typing`, `tools`, `placeholder`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `actions` | `[]` |  |  |
| `conversationEvent` |  |  |  |
| `conversationId` |  |  |  |
| `disableAutoScroll` | `false` |  |  |
| `hasPreviousMessages` | `false` |  |  |
| `information` | `[]` |  |  |
| `isEmbeddedMode` | `false` |  |  |
| `isTyping` | `false` |  |  |
| `messages` | `[]` |  |  |
| `placeholder` | `[]` |  |  |
| `previewMessageId` | `""` |  |  |
| `searchFilter` |  |  |  |
| `tools` | `[]` |  |  |
| `typing` | `[]` |  |  |
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
| `conversationEventChange` |  |  |
| `loadPreviousMessages` |  |  |
| `messageEvent` |  |  |
| `paginationChange` |  |  |
| `previewMessageIdChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{requiredFeatures:{ShowDesignerDemoItems:true},position:110,groupType:m.h.Components,icon:e(70807),defaultPropertyValues:{actions:[],information:[],messages:[],tools:[{name:"MessageEditor_"+s.N,type:"crt.MessageEditor",items:[{name:"MessageEditorBody_"+s.N,type:"crt.MessageEditorBody",inputs:[{name:"MessageEditorInput_"+s.N,type:"crt.MessageEditorInput"}]}]}],placeholder:[],typing:[]},addCommandTypeName:"crt.AddConversationCommand"},designControlConfig:{allowDesignContent:true},propertiesPanelComponentTypeName:"crt.ConversationPropertiesPanel",viewElementGroupType:h.J.LayoutElements,typeCaption:"Conversation.Caption",placeholderSize:{height:"1000px"}}
```

## Приклад з реальної схеми


```json
{"type":"crt.Conversation","contentSlots":["actions","information","typing","tools","placeholder"]}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2656.hash=2360e964a8a68b73.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*