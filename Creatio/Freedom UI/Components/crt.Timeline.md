---
type: crt.Timeline
selector: crt-timeline
group: "Timeline / Feed / Файли"
usage_in_configs: 6
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Timeline

> Таймлайн запису (активності, email, дзвінки, фід).

Angular-селектор: `<crt-timeline>`  
Група: **Timeline / Feed / Файли**  
Слоти вкладених елементів (`contentSlots`): `tools`, `customFilters`  
Зустрічається в реальних конфігах: **6** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `customFilters` |  | `[]` | 4 | слот (lazy) |
| `filterValues` |  | `<binding>` | 2 |  |
| `isTileReadOnly` |  |  |  |  |
| `masterEntity` |  |  |  |  |
| `masterEntitySchemaName` |  | `"Account"` | 4 | об'єкт запису |
| `masterSchemaId` |  | `<binding>` | 6 |  |
| `quickFilterByOwnerConfig` |  |  |  |  |
| `tools` |  | `[]` | 6 | слот (lazy) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `items` | 6 | `[]` |  |
| `caption` | 6 | `"#ResourceString(Timeline_caption)#"`, `<binding>` |  |
| `label` | 6 | `"#ResourceString(Timeline_label)#"`, `<binding>` |  |
| `timelineName` | 6 | `"Timeline"`, `"NewsAndInsightsTimeline"` |  |
| `filters` | 6 | `[]` |  |
| `layoutConfig` | 4 |  | спільна → [[Common view-element properties#layoutConfig]] |
| `hideTools` | 2 | `false` |  |
| `visible` | 2 | `true` | спільна → [[Common view-element properties#visible]] |
| `labelPosition` | 2 | `"auto"` |  |
| `placeholder` | 2 | `""` |  |
| `tooltip` | 2 | `""` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `layoutConfig.colSpan` | 4 | `2` |  |
| `layoutConfig.column` | 4 | `1` |  |
| `layoutConfig.row` | 4 | `1` |  |
| `layoutConfig.rowSpan` | 4 | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:260,groupType:Bt.h.Components,hint:"Components.Timeline.Hint",icon:l(6117),defaultPropertyValues:{items:[],tools:[],customFilters:[],hideTools:false,masterSchemaId:"$Id"},defaultLocalizableStrings:{caption:"Components.Timeline.Caption",label:"Components.Timeline.Caption"}},propertiesPanelComponentTypeName:"crt.TimelinePropertiesPanel",viewElementGroupType:pt.J.Components,typeCaption:"Components.Timeline.Caption",designControlConfig:{allowDesignContent:true}}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_1.js.завантаження`

```json
{type:"crt.Timeline",items:[],tools:[],customFilters:[],hideTools:false,masterSchemaId:"$Id",caption:"#ResourceString(NewsAndInsightsTimeline_caption)#",label:"#ResourceString(NewsAndInsightsTimeline_label)#",filters:[],masterEntitySchemaName:"Account",visible:true,labelPosition:"auto",placeholder:"",tooltip:"",timelineName:"NewsAndInsightsTimeline",filterValues:"$NewsAndInsightsTimeline_AllTileFilters"}
```

## Пов'язані

[[crt.TimelineTile]], [[crt.TimelineLabel]], [[crt.Feed]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7910.hash=7aee5aadbf21d80e.js) + 66 згадок у конфігах. Мінімізовані імена класів не наводяться.*