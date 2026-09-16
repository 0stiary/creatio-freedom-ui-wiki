---
type: crt.ChartWidget
selector: crt-chart-widget
group: "Дашборди та віджети"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ChartWidget

> Віджет-графік.

Angular-селектор: `<crt-chart-widget>`  
Група: **Дашборди та віджети**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `config` |  |  | серії, тип графіка, об'єкт |
| `isDesignTime` |  |  |  |
| `seriesData` |  |  |  |
| `listConfig` |  |  | (успадковано від базового класу) |
| `listData` |  |  | (успадковано від базового класу) |
| `pagingConfig` |  |  | (успадковано від базового класу) |
| `searchValue` | `""` |  | (успадковано від базового класу) |
| `sectionBindingColumnRecordId` |  | `<binding>` | (успадковано від базового класу) |
| `sortingConfig` | `null` |  | (успадковано від базового класу) |
| `toolbarMenuItems` | `[]` |  | (успадковано від базового класу) |
| `userProfileData` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `seriesConfigsChanged` |  |  |
| `columnsChange` |  |  |
| `drillDown` |  |  |
| `fullScreenStateChanged` |  |  |
| `getProfileColumns` |  |  |
| `paginationChange` |  |  |
| `resetToDefault` |  |  |
| `searchFilterChange` |  |  |
| `sortingChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `config.color` | `"dark-blue"`, `"dark-turquoise"`, `"green"`, `"navy-blue"`, `"blue"`, `"coral"` |  |
| `config.scales` |  |  |
| `config.scales.stacked` | `false`, `true` |  |
| `config.scales.xAxis` |  |  |
| `config.scales.xAxis.formatting` |  |  |
| `config.scales.xAxis.name` | `""`, `<binding>` |  |
| `config.scales.yAxis` |  |  |
| `config.scales.yAxis.formatting` |  |  |
| `config.scales.yAxis.name` | `""`, `<binding>` |  |
| `config.series` |  |  |
| `config.seriesOrder` |  |  |
| `config.seriesOrder.direction` | `1`, `2` |  |
| `config.seriesOrder.type` | `"by-grouping-value"`, `"by-aggregation-value"` |  |
| `config.theme` | `"without-fill"`, `"partial-fill"`, `"glassmorphism"` |  |
| `config.title` | `<binding>`, `"#ResourceString(CountryChart_title)#"`, `"#ResourceString(ChannelsChart_title)#"` |  |
| `config.series[].data` |  |  |
| `config.series[].data.formatting` |  |  |
| `config.series[].data.providing` |  |  |
| `config.series[].label` | `<binding>` |  |
| `config.series[].legend` |  |  |
| `config.series[].legend.enabled` | `false`, `true` |  |
| `config.series[].type` | `"spline"`, `"horizontal-bar"`, `"doughnut"`, `"line"`, `"bar"` |  |
| `config.series[].color` | `"blue"`, `"coral"`, `"burnt-coral"`, `"dark-turquoise"`, `"celestial-blue"`, `"orange-red"` |  |
| `config.series[].dataLabel` |  |  |
| `config.series[].dataLabel.display` | `true`, `false`, `null` |  |
| `config.layout` | `{}` |  |
| `config.seriesOrder.seriesIndex` | `0` |  |
| `layoutConfig.colSpan` | `6`, `9`, `12`, `4`, `8`, `1` |  |
| `layoutConfig.column` | `1`, `7`, `5`, `9`, `6` |  |
| `layoutConfig.row` | `4`, `3`, `7`, `13`, `22`, `1` |  |
| `layoutConfig.rowSpan` | `4`, `9`, `8`, `5`, `10`, `6` |  |

## Приклад з реальної схеми


```json
{layoutConfig:{column:1,row:3,colSpan:4,rowSpan:4},type:"crt.ChartWidget",config:{title:"#ResourceString(crtChartWidget2709e25260fee39e4e4d6a1cecdd7e34_title)#",color:"dark-green",theme:"partial-fill",scales:{stacked:false,xAxis:{name:"",formatting:{type:"string",maxLinesCount:2,maxLineLength:10}},yAxis:{name:"",formatting:{type:"number",thousandAbbreviation:{enabled:true}}}},series:[{type:"doughnut",label:"#ResourceString(crtChartWidget2709e25260fee39e4e4d6a1cecdd7e34_series_0)#",legend:{enabled:false},data:{providing:{schemaName:"Case",rowCount:50,grouping:{column:{expression:{expressionType:0,columnPath:"Status"}},type:"by-value"},aggregation:{column:{expression:{expressionType:1,functionType:2,aggregationType:1,aggregationEvalType:2,functionArgument:{expressionType:0,columnPath:"Id"}}}},filters:{filter:{items:{columnIsNotNullFilter:{comparisonType:2,filterType:2,isEnabled:true,isNull:false,trimDateTimeParameterToDate:false,leftExpression:{expressionType:0,columnPath:"Status"}}},logicalOperation:0,isEnabled:true,filterType:6,rootSchemaName:"Case"}}},formatting:{type:"number",decimalSeparator:".",thousandSeparator:","}}}],seriesOrder:{type:"by-grouping-value",direction:1}}}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ChartWidget** → *BaseWidget* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ChartWidget** (власні) | `config`, `isDesignTime`, `seriesData` | `seriesConfigsChanged` |  |
| *BaseWidget* | `listConfig`, `listData`, `pagingConfig`, `searchValue`, `sectionBindingColumnRecordId`, `sortingConfig`, `toolbarMenuItems`, `userProfileData` | `columnsChange`, `drillDown`, `fullScreenStateChanged`, `getProfileColumns`, `paginationChange`, `resetToDefault`, `searchFilterChange`, `sortingChange` | віджет дашборда: `sectionBindingColumnRecordId, toolbarMenuItems, listConfig, userProfileData, listData, searchValue, pagingConfig, sortingConfig`; події `drillDown, paginationChange, columnsChange, resetToDefault, getProfileColumns, sortingChange, searchFilterChange, fullScreenStateChanged` |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 143 згадок у конфігах. Мінімізовані імена класів не наводяться.*