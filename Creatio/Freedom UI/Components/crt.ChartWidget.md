---
type: crt.ChartWidget
selector: crt-chart-widget
group: "Дашборди та віджети"
usage_in_configs: 48
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ChartWidget

> Віджет-графік.

Angular-селектор: `<crt-chart-widget>`  
Група: **Дашборди та віджети**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **48** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `config` |  |  | 48 | серії, тип графіка, об'єкт |
| `isDesignTime` |  |  |  |  |
| `seriesData` |  |  |  |  |
| `listConfig` |  |  |  | (успадковано від базового класу) |
| `listData` |  |  |  | (успадковано від базового класу) |
| `pagingConfig` |  |  |  | (успадковано від базового класу) |
| `searchValue` | `""` |  |  | (успадковано від базового класу) |
| `sectionBindingColumnRecordId` |  | `<binding>` | 28 | (успадковано від базового класу) |
| `sortingConfig` | `null` |  |  | (успадковано від базового класу) |
| `toolbarMenuItems` | `[]` |  |  | (успадковано від базового класу) |
| `userProfileData` |  |  |  | (успадковано від базового класу) |

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

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 48 |  | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 19 | `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `config.color` | 48 | `"dark-blue"`, `"dark-turquoise"`, `"green"`, `"navy-blue"`, `"blue"`, `"coral"` |  |
| `config.scales` | 48 |  |  |
| `config.scales.stacked` | 48 | `false`, `true` |  |
| `config.scales.xAxis` | 48 |  |  |
| `config.scales.xAxis.formatting` | 48 |  |  |
| `config.scales.xAxis.name` | 48 | `""`, `<binding>` |  |
| `config.scales.yAxis` | 48 |  |  |
| `config.scales.yAxis.formatting` | 48 |  |  |
| `config.scales.yAxis.name` | 48 | `""`, `<binding>` |  |
| `config.series` | 48 |  |  |
| `config.seriesOrder` | 48 |  |  |
| `config.seriesOrder.direction` | 48 | `1`, `2` |  |
| `config.seriesOrder.type` | 48 | `"by-grouping-value"`, `"by-aggregation-value"` |  |
| `config.theme` | 48 | `"without-fill"`, `"partial-fill"`, `"glassmorphism"` |  |
| `config.title` | 48 | `<binding>`, `"#ResourceString(CountryChart_title)#"`, `"#ResourceString(ChannelsChart_title)#"` |  |
| `config.series[].data` | 47 |  |  |
| `config.series[].data.formatting` | 47 |  |  |
| `config.series[].data.providing` | 47 |  |  |
| `config.series[].label` | 47 | `<binding>` |  |
| `config.series[].legend` | 47 |  |  |
| `config.series[].legend.enabled` | 47 | `false`, `true` |  |
| `config.series[].type` | 47 | `"spline"`, `"horizontal-bar"`, `"doughnut"`, `"line"`, `"bar"` |  |
| `config.series[].color` | 37 | `"blue"`, `"coral"`, `"burnt-coral"`, `"dark-turquoise"`, `"celestial-blue"`, `"orange-red"` |  |
| `config.series[].dataLabel` | 27 |  |  |
| `config.series[].dataLabel.display` | 27 | `true`, `false`, `null` |  |
| `config.layout` | 25 | `{}` |  |
| `config.seriesOrder.seriesIndex` | 18 | `0` |  |
| `layoutConfig.colSpan` | 48 | `6`, `9`, `12`, `4`, `8`, `1` |  |
| `layoutConfig.column` | 48 | `1`, `7`, `5`, `9`, `6` |  |
| `layoutConfig.row` | 48 | `4`, `3`, `7`, `13`, `22`, `1` |  |
| `layoutConfig.rowSpan` | 48 | `4`, `9`, `8`, `5`, `10`, `6` |  |

## Приклад з реальної схеми

Джерело: `_bundle_default_0.js.завантаження`

```json
{layoutConfig:{column:1,row:3,colSpan:4,rowSpan:4},type:"crt.ChartWidget",config:{title:"#ResourceString(crtChartWidget2709e25260fee39e4e4d6a1cecdd7e34_title)#",color:"dark-green",theme:"partial-fill",scales:{stacked:false,xAxis:{name:"",formatting:{type:"string",maxLinesCount:2,maxLineLength:10}},yAxis:{name:"",formatting:{type:"number",thousandAbbreviation:{enabled:true}}}},series:[{type:"doughnut",label:"#ResourceString(crtChartWidget2709e25260fee39e4e4d6a1cecdd7e34_series_0)#",legend:{enabled:false},data:{providing:{schemaName:"Case",rowCount:50,grouping:{column:{expression:{expressionType:0,columnPath:"Status"}},type:"by-value"},aggregation:{column:{expression:{expressionType:1,functionType:2,aggregationType:1,aggregationEvalType:2,functionArgument:{expressionType:0,columnPath:"Id"}}}},filters:{filter:{items:{columnIsNotNullFilter:{comparisonType:2,filterType:2,isEnabled:true,isNull:false,trimDateTimeParameterToDate:false,leftExpression:{expressionType:0,columnPath:"Status"}}},logicalOperation:0,isEnabled:true,filterType:6,rootSchemaName:"Case"}}},formatting:{type:"number",decimalSeparator:".",thousandSeparator:","}}}],seriesOrder:{type:"by-grouping-value",direction:1}}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 143 згадок у конфігах. Мінімізовані імена класів не наводяться.*