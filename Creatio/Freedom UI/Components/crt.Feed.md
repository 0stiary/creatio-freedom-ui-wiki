---
type: crt.Feed
selector: crt-feed
group: "Timeline / Feed / Файли"
usage_in_configs: 4
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Feed

> Стрічка (коментарі) запису.

Angular-селектор: `<crt-feed>`  
Група: **Timeline / Feed / Файли**  
Слоти вкладених елементів (`contentSlots`): `selectionActions`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **4** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `allowExternalPost` |  |  |  |  |
| `cardState` |  | `<binding>` | 4 | `$CardState` |
| `dataSourceName` |  | `null`, `"PDS"` | 4 | `PDS` |
| `disableSelectionOptions` |  |  |  |  |
| `entitySchemaName` |  | `"#DataSourceEntityName()#"`, `"UsrFilterNodes"`, `"UsrPendingLines"` | 4 | об'єкт запису або `#DataSourceEntityName()#` |
| `feedMessages` | `[]` |  |  |  |
| `feedMessagesPage` | `[]` |  |  |  |
| `feedType` |  | `"Record"` | 4 | `Record` |
| `isReadOnly` |  |  |  |  |
| `offsetDate` |  |  |  |  |
| `primaryColumnValue` |  | `<binding>` | 4 | `$Id` |
| `primaryDisplayColumnValue` |  |  |  |  |
| `readingMode` |  |  |  |  |
| `selection` |  |  |  |  |
| `showBlankSlate` | `true` |  |  |  |
| `sortColumn` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `feedMessagesChange` |  |  |
| `offsetDateChange` |  |  |
| `selectionChange` |  |  |
| `sortColumnChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:90,icon:t(1372),defaultPropertyValues:{feedType:S.Q.Record,primaryColumnValue:"$Id",cardState:"$CardState",allowExternalPost:false},addCommandTypeName:"crt.AddFeedCommand"},propertiesPanelComponentTypeName:"crt.FeedPropertiesPanel",viewElementGroupType:U.J.Components,typeCaption:"Feed.Caption",placeholderSize:{height:"328px"}}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_1.js.завантаження`

```json
{type:"crt.Feed",feedType:"Record",primaryColumnValue:"$Id",cardState:"$CardState",dataSourceName:null,entitySchemaName:"#DataSourceEntityName()#"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (9596.hash=3da76c6a0b1e195f.js) + 20 згадок у конфігах. Мінімізовані імена класів не наводяться.*