---
type: crt.FeedComposer
selector: crt-feed-composer
group: "Timeline / Feed / Файли"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FeedComposer

Angular-селектор: `<crt-feed-composer>`  
Група: **Timeline / Feed / Файли**  
Слоти вкладених елементів (`contentSlots`): `channelsPanel`, `selectionActions`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `allowExternalPost` |  |  |  |  |
| `cardState` |  | `<binding>` | 2 |  |
| `composerEvent` |  |  |  |  |
| `entitySchemaName` |  | `"Account"` | 2 |  |
| `forExternal` |  |  |  |  |
| `forExternalDefault` |  |  |  |  |
| `message` |  |  |  |  |
| `messageId` |  |  |  |  |
| `parentMessageId` |  |  |  |  |
| `primaryColumnValue` |  | `<binding>` | 2 |  |
| `schemaUId` |  |  |  |  |
| `disableSelectionOptions` |  |  |  | (успадковано від базового класу) |
| `selection` |  |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `messageChangesCanceled` |  |  |
| `messagePosted` |  |  |
| `composerEventChange` |  |  |
| `selectionChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `sortedByColumn` | 2 | `"CreatedOn"` |  |
| `data` | 2 |  |  |
| `feedType` | 2 | `"Record"` |  |
| `dataSourceName` | 2 | `"PDS"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `data.caption` | 2 | `"Feed"` |  |
| `data.icon` | 2 | `"feed-composer-icon"` |  |
| `data.schemaType` | 2 | `"Feed"` |  |
| `data.sortedByColumn` | 2 | `"CreatedOn"` |  |
| `data.typeName` | 2 | `"crt.FeedComposer"` |  |
| `data.uId` | 2 | `"6d006667-3496-4e2d-adc0-3a42648dd97b"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{propertiesPanelComponentTypeName:"crt.FeedComposerPropertiesPanel",viewElementGroupType:$.J.CustomElements,typeCaption:"MessageComposer.Feed.Caption"}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_1.js.завантаження`

```json
{type:"crt.FeedComposer",classes:["view-element"],sortedByColumn:"CreatedOn",data:{uId:"6d006667-3496-4e2d-adc0-3a42648dd97b",schemaType:"Feed",caption:"Feed",sortedByColumn:"CreatedOn",typeName:"crt.FeedComposer",icon:"feed-composer-icon"},feedType:"Record",primaryColumnValue:"$Id",cardState:"$CardState",entitySchemaName:"Account",dataSourceName:"PDS"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (3789.hash=c07acffd1a475b43.js) + 16 згадок у конфігах. Мінімізовані імена класів не наводяться.*