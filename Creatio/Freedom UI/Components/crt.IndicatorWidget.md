---
type: crt.IndicatorWidget
selector: crt-indicator-widget
group: "Дашборди та віджети"
usage_in_configs: 118
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.IndicatorWidget

> Віджет-показник (аналітика).

Angular-селектор: `<crt-indicator-widget>`  
Група: **Дашборди та віджети**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **118** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `config` |  |  | 118 | конфіг віджета (об'єкт, агрегація, колонка, фільтр) |
| `data` |  |  |  |  |
| `drilldownEnabled` | `true` |  |  |  |
| `isDesignTime` |  |  |  |  |
| `listConfig` |  |  |  | (успадковано від базового класу) |
| `listData` |  |  |  | (успадковано від базового класу) |
| `pagingConfig` |  |  |  | (успадковано від базового класу) |
| `searchValue` | `""` |  |  | (успадковано від базового класу) |
| `sectionBindingColumnRecordId` |  | `<binding>` | 12 | (успадковано від базового класу) |
| `sortingConfig` | `null` |  |  | (успадковано від базового класу) |
| `toolbarMenuItems` | `[]` |  |  | (успадковано від базового класу) |
| `userProfileData` |  |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
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
| `layoutConfig` | 118 |  | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 88 | `true` | спільна → [[Common view-element properties#visible]] |
| `_filterableOptions` | 4 |  | **прихована** |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `_filterableOptions[].caption` | 4 | `<binding>` |  |
| `_filterableOptions[].entitySchemaName` | 4 | `"BulkEmail"` |  |
| `_filterableOptions[].filterAttributeName` | 4 |  |  |
| `_filterableOptions[].filterAttributes` | 4 | `[]` |  |
| `config.data` | 118 |  |  |
| `config.data.formatting` | 118 |  |  |
| `config.data.formatting.type` | 118 | `"number"`, `"datetime"` |  |
| `config.data.providing` | 118 |  |  |
| `config.layout` | 118 |  |  |
| `config.layout.color` | 118 | `"transparent"`, `"navy-blue"`, `"vivid-purple"`, `"dark-turquoise"`, `"green"`, `"blue"` |  |
| `config.text` | 118 |  |  |
| `config.text.fontSizeMode` | 118 | `"medium"`, `"large"`, `"extra-small"` |  |
| `config.text.metricMacros` | 118 | `"{0}"` |  |
| `config.text.template` | 118 | `<binding>` |  |
| `config.theme` | 118 | `"without-fill"`, `"full-fill"`, `"glassmorphism"` |  |
| `config.title` | 118 | `<binding>` |  |
| `config.data.providing.aggregation` | 114 |  |  |
| `config.data.providing.filters` | 114 | `null` |  |
| `config.data.providing.schemaName` | 114 | `"FormSubmit"`, `"Lead"`, `"UsrVwWaterfallData"`, `"BulkEmail"`, `"Case"`, `"VwSysProcessLog"` |  |
| `config.data.formatting.decimalSeparator` | 113 | `"."`, `","` |  |
| `config.data.formatting.thousandSeparator` | 113 | `","`, `" "` |  |
| `config.data.formatting.decimalPrecision` | 89 | `0`, `2` |  |
| `config.data.providing.attribute` | 82 | `"TotalLPsubmissionsIndicatorWidget_Data"`, `"IndicatorWidget_oj1378v_Data"`, `"IndicatorWidget_lyr7msq_Data"`, `"IndicatorWidget_fenauxs_Data"`, `"IndicatorWidget_lfqc1b1_Data"`, `"IndicatorWidget_r8kuhe0_Data"` |  |
| `config.data.providing.dependencies` | 78 | `[]` |  |
| `config.text.labelPosition` | 70 | `"above-under"`, `"before-after"` |  |
| `config.hideTitle` | 33 | `false` |  |
| `config.layout.icon` | 22 |  |  |
| `config.layout.icon.iconName` | 22 | `"calendar-icon"`, `"flag-icon"`, `"document-contact-icon"`, `"clock-icon"`, `"globe-icon"`, `"contact-icon"` |  |
| `config.comparison` | 12 |  |  |
| `config.comparison.text` | 12 | `""` |  |
| `config.comparison.type` | 12 | `null` |  |
| `config.data.comparisonProviding` | 12 | `null` |  |
| `config.data.providing.sectionBindingColumn` | 12 | `{}` |  |
| `config.dataSourceConfig` | 12 |  |  |
| `config.dataSourceConfig.entitySchemaName` | 12 | `"Event"`, `"AdCampaign"` |  |
| `config.layout.icon.color` | 6 | `"blue"`, `"dark-turquoise"`, `"cadmium-red"` |  |
| `config.data.formatting.date` | 5 |  |  |
| `config.data.formatting.time` | 5 |  |  |
| `config.data.providing.expressionSchema` | 4 |  |  |
| `config.dataSourceConfig.attributes` | 4 |  |  |
| `config.dataSourceConfig.attributes.CPC` | 4 |  |  |
| `config.dataSourceConfig.attributes.CPM` | 4 |  |  |
| `config.dataSourceConfig.attributes.CTR` | 4 |  |  |
| `config.dataSourceConfig.attributes.CampaignName` | 4 |  |  |
| `config.dataSourceConfig.attributes.Clicks` | 4 |  |  |
| `config.dataSourceConfig.attributes.Impressions` | 4 |  |  |
| `config.dataSourceConfig.attributes.Status` | 4 |  |  |
| `config.dataSourceConfig.attributes.PrimaryAmountSpent` | 3 |  |  |
| `config.dataSourceConfig.attributes.AdAccountCurrency` | 2 |  |  |
| `config.dataSourceConfig.attributes.Platform` | 2 |  |  |
| `config.dataSourceConfig.attributes.AmountSpent` | 1 |  |  |
| `layoutConfig.colSpan` | 118 | `3`, `2`, `1`, `4` |  |
| `layoutConfig.column` | 118 | `1`, `10`, `7`, `4`, `3`, `5` |  |
| `layoutConfig.row` | 118 | `1`, `2`, `3`, `4`, `7`, `5` |  |
| `layoutConfig.rowSpan` | 118 | `2`, `1`, `3`, `4` |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_0.js.завантаження`

```json
{layoutConfig:{column:4,row:1,colSpan:3,rowSpan:2},type:"crt.IndicatorWidget",config:{title:"#ResourceString(crtIndicatorWidget36551d0719c71252aea435e530446ecf_title)#",data:{providing:{schemaName:"VwExpiringLicense",aggregation:{column:{expression:{expressionType:1,functionType:2,aggregationType:1,aggregationEvalType:2,functionArgument:{expressionType:0,columnPath:"Id"}}}},filters:{filter:{items:{},logicalOperation:0,isEnabled:true,filterType:6,rootSchemaName:"VwExpiringLicense"}}},formatting:{type:"number",decimalSeparator:".",thousandSeparator:","}},text:{template:"#ResourceString(crtIndicatorWidget36551d0719c71252aea435e530446ecf_template)#",metricMacros:"{0}",fontSizeMode:"large"},layout:{color:"navy-blue"},theme:"full-fill"}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 340 згадок у конфігах. Мінімізовані імена класів не наводяться.*