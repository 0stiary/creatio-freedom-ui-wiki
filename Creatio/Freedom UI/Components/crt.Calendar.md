---
type: crt.Calendar
selector: crt-calendar
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Calendar

Angular-селектор: `<crt-calendar>`  
Група: **Бізнес-компоненти**  
Слоти вкладених елементів (`contentSlots`): `tileContent`  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `colorizationType` |  |  |  |
| `dateRangeLimitInDays` |  |  |  |
| `endBusinessTime` |  |  |  |
| `filters` |  |  |  |
| `items` |  | `<binding>` |  |
| `lightweightModeLimit` |  |  |  |
| `maxDuplicatesByOwner` | `16` |  |  |
| `miniPageSchemaName` |  | `"AddTaskMiniPage"` |  |
| `pageSize` | `150` |  |  |
| `participantFilters` |  |  |  |
| `showWeekends` |  | `<binding>` |  |
| `startBusinessTime` |  |  |  |
| `templateValuesMapping` |  |  |  |
| `timeScale` |  | `<binding>` |  |
| `useAllDayMeeting` | `true` |  |  |
| `useAutoScrollToCurrentTime` | `true` | `true` |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `endBusinessTimeChange` |  |  |
| `highlightArea` |  |  |
| `loadNextPage` |  |  |
| `openEditPage` |  |  |
| `openPositionedMiniPage` |  |  |
| `silenceCreate` |  |  |
| `startBusinessTimeChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `highlightedStartDate` | `"Calendar_n8j0xn9_highlightedStartDate"` |  |
| `hightlightedEndDate` | `"Calendar_n8j0xn9_highlightedEndDate"` |  |
| `tileContent` | `[]` |  |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `fitContent` | `true` |  |
| `primaryColumnName` | `"Calendar_n8j0xn9DS_Id"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `templateValuesMapping.Label_11cnx3j` | `"Calendar_n8j0xn9DS_Location"` |  |
| `templateValuesMapping.Label_t6oa43h` | `"Calendar_n8j0xn9DS_Account"` |  |
| `templateValuesMapping.endColumn` | `"Calendar_n8j0xn9DS_DueDate"` |  |
| `templateValuesMapping.notesColumn` | `"Calendar_n8j0xn9DS_Notes"` |  |
| `templateValuesMapping.startColumn` | `"Calendar_n8j0xn9DS_StartDate"` |  |
| `templateValuesMapping.titleColumn` | `"Calendar_n8j0xn9DS_Title"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:310,icon:c(95226),defaultPropertyValues:{tileContent:[]}},propertiesPanelComponentTypeName:"crt.CalendarPropertiesPanelComponent",designViewItemCommands:{delete:"crt.RemoveCalendarCommand",create:"crt.AddCalendarCommand"},viewElementGroupType:dt.J.Components,typeCaption:"Components.CalendarCaption"}
```

## Приклад з реальної схеми


```json
{layoutConfig:{},showWeekends:"$Calendar_showweekends",highlightedStartDate:"Calendar_n8j0xn9_highlightedStartDate",hightlightedEndDate:"Calendar_n8j0xn9_highlightedEndDate",type:"crt.Calendar",tileContent:[],templateValuesMapping:{startColumn:"Calendar_n8j0xn9DS_StartDate",endColumn:"Calendar_n8j0xn9DS_DueDate",titleColumn:"Calendar_n8j0xn9DS_Title",Label_t6oa43h:"Calendar_n8j0xn9DS_Account",Label_11cnx3j:"Calendar_n8j0xn9DS_Location",notesColumn:"Calendar_n8j0xn9DS_Notes"},useAutoScrollToCurrentTime:true,miniPageSchemaName:"AddTaskMiniPage",visible:true,fitContent:true,items:"$Calendar_n8j0xn9",primaryColumnName:"Calendar_n8j0xn9DS_Id",timeScale:"$Calendar_Tasks_TimeScale"}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.Calendar** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.Calendar** (власні) | `colorizationType`, `dateRangeLimitInDays`, `endBusinessTime`, `filters`, `items`, `lightweightModeLimit`, `maxDuplicatesByOwner`, `miniPageSchemaName`, `pageSize`, `participantFilters`, `showWeekends`, `startBusinessTime`, `templateValuesMapping`, `timeScale`, `useAllDayMeeting`, `useAutoScrollToCurrentTime` | `endBusinessTimeChange`, `highlightArea`, `loadNextPage`, `openEditPage`, `openPositionedMiniPage`, `silenceCreate`, `startBusinessTimeChange` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (9517.hash=586d2d36fceb19fd.js) + 13 згадок у конфігах. Мінімізовані імена класів не наводяться.*