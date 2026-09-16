---
type: crt.Timeline
selector: crt-timeline
group: "Timeline / Feed / Файли"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Timeline

> Таймлайн запису (активності, email, дзвінки, фід).

Angular-селектор: `<crt-timeline>`  
Група: **Timeline / Feed / Файли**  
Слоти вкладених елементів (`contentSlots`): `tools`, `customFilters`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `customFilters` |  | `[]` | слот (lazy) |
| `filterValues` |  | `<binding>` |  |
| `isTileReadOnly` |  |  |  |
| `masterEntity` |  |  |  |
| `masterEntitySchemaName` |  | `"Account"` | об'єкт запису |
| `masterSchemaId` |  | `<binding>` |  |
| `quickFilterByOwnerConfig` |  |  |  |
| `tools` |  | `[]` | слот (lazy) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `items` | `[]` |  |
| `caption` | `"#ResourceString(Timeline_caption)#"`, `<binding>` |  |
| `label` | `"#ResourceString(Timeline_label)#"`, `<binding>` |  |
| `timelineName` | `"Timeline"`, `"NewsAndInsightsTimeline"` |  |
| `filters` | `[]` |  |
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `hideTools` | `false` |  |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `labelPosition` | `"auto"` |  |
| `placeholder` | `""` |  |
| `tooltip` | `""` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `layoutConfig.colSpan` | `2` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `1` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:260,groupType:Bt.h.Components,hint:"Components.Timeline.Hint",icon:l(6117),defaultPropertyValues:{items:[],tools:[],customFilters:[],hideTools:false,masterSchemaId:"$Id"},defaultLocalizableStrings:{caption:"Components.Timeline.Caption",label:"Components.Timeline.Caption"}},propertiesPanelComponentTypeName:"crt.TimelinePropertiesPanel",viewElementGroupType:pt.J.Components,typeCaption:"Components.Timeline.Caption",designControlConfig:{allowDesignContent:true}}
```

## Приклад з реальної схеми


```json
{type:"crt.Timeline",items:[],tools:[],customFilters:[],hideTools:false,masterSchemaId:"$Id",caption:"#ResourceString(NewsAndInsightsTimeline_caption)#",label:"#ResourceString(NewsAndInsightsTimeline_label)#",filters:[],masterEntitySchemaName:"Account",visible:true,labelPosition:"auto",placeholder:"",tooltip:"",timelineName:"NewsAndInsightsTimeline",filterValues:"$NewsAndInsightsTimeline_AllTileFilters"}
```

## Пов'язані

[[crt.TimelineTile]], [[crt.TimelineLabel]], [[crt.Feed]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7910.hash=7aee5aadbf21d80e.js) + 66 згадок у конфігах. Мінімізовані імена класів не наводяться.*