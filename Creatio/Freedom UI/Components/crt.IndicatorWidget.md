---
type: crt.IndicatorWidget
selector: crt-indicator-widget
group: "Дашборди та віджети"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.IndicatorWidget

> Віджет-показник (аналітика).

Angular-селектор: `<crt-indicator-widget>`  
Група: **Дашборди та віджети**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `config` |  |  | конфіг віджета (об'єкт, агрегація, колонка, фільтр) |
| `data` |  |  |  |
| `drilldownEnabled` | `true` |  |  |
| `isDesignTime` |  |  |  |
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
| `_filterableOptions` |  | **прихована** |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_filterableOptions[].caption` | `<binding>` |  |
| `_filterableOptions[].entitySchemaName` | `"BulkEmail"` |  |
| `_filterableOptions[].filterAttributeName` |  |  |
| `_filterableOptions[].filterAttributes` | `[]` |  |
| `config.data` |  |  |
| `config.data.formatting` |  |  |
| `config.data.formatting.type` | `"number"`, `"datetime"` |  |
| `config.data.providing` |  |  |
| `config.layout` |  |  |
| `config.layout.color` | `"transparent"`, `"navy-blue"`, `"vivid-purple"`, `"dark-turquoise"`, `"green"`, `"blue"` |  |
| `config.text` |  |  |
| `config.text.fontSizeMode` | `"medium"`, `"large"`, `"extra-small"` |  |
| `config.text.metricMacros` | `"{0}"` |  |
| `config.text.template` | `<binding>` |  |
| `config.theme` | `"without-fill"`, `"full-fill"`, `"glassmorphism"` |  |
| `config.title` | `<binding>` |  |
| `config.data.providing.aggregation` |  |  |
| `config.data.providing.filters` | `null` |  |
| `config.data.providing.schemaName` | `"FormSubmit"`, `"Lead"`, `"UsrVwWaterfallData"`, `"BulkEmail"`, `"Case"`, `"VwSysProcessLog"` |  |
| `config.data.formatting.decimalSeparator` | `"."`, `","` |  |
| `config.data.formatting.thousandSeparator` | `","`, `" "` |  |
| `config.data.formatting.decimalPrecision` | `0`, `2` |  |
| `config.data.providing.attribute` | `"TotalLPsubmissionsIndicatorWidget_Data"`, `"IndicatorWidget_oj1378v_Data"`, `"IndicatorWidget_lyr7msq_Data"`, `"IndicatorWidget_fenauxs_Data"`, `"IndicatorWidget_lfqc1b1_Data"`, `"IndicatorWidget_r8kuhe0_Data"` |  |
| `config.data.providing.dependencies` | `[]` |  |
| `config.text.labelPosition` | `"above-under"`, `"before-after"` |  |
| `config.hideTitle` | `false` |  |
| `config.layout.icon` |  |  |
| `config.layout.icon.iconName` | `"calendar-icon"`, `"flag-icon"`, `"document-contact-icon"`, `"clock-icon"`, `"globe-icon"`, `"contact-icon"` |  |
| `config.comparison` |  |  |
| `config.comparison.text` | `""` |  |
| `config.comparison.type` | `null` |  |
| `config.data.comparisonProviding` | `null` |  |
| `config.data.providing.sectionBindingColumn` | `{}` |  |
| `config.dataSourceConfig` |  |  |
| `config.dataSourceConfig.entitySchemaName` | `"Event"`, `"AdCampaign"` |  |
| `config.layout.icon.color` | `"blue"`, `"dark-turquoise"`, `"cadmium-red"` |  |
| `config.data.formatting.date` |  |  |
| `config.data.formatting.time` |  |  |
| `config.data.providing.expressionSchema` |  |  |
| `config.dataSourceConfig.attributes` |  |  |
| `config.dataSourceConfig.attributes.CPC` |  |  |
| `config.dataSourceConfig.attributes.CPM` |  |  |
| `config.dataSourceConfig.attributes.CTR` |  |  |
| `config.dataSourceConfig.attributes.CampaignName` |  |  |
| `config.dataSourceConfig.attributes.Clicks` |  |  |
| `config.dataSourceConfig.attributes.Impressions` |  |  |
| `config.dataSourceConfig.attributes.Status` |  |  |
| `config.dataSourceConfig.attributes.PrimaryAmountSpent` |  |  |
| `config.dataSourceConfig.attributes.AdAccountCurrency` |  |  |
| `config.dataSourceConfig.attributes.Platform` |  |  |
| `config.dataSourceConfig.attributes.AmountSpent` |  |  |
| `layoutConfig.colSpan` | `3`, `2`, `1`, `4` |  |
| `layoutConfig.column` | `1`, `10`, `7`, `4`, `3`, `5` |  |
| `layoutConfig.row` | `1`, `2`, `3`, `4`, `7`, `5` |  |
| `layoutConfig.rowSpan` | `2`, `1`, `3`, `4` |  |

## Приклад з реальної схеми


```json
{layoutConfig:{column:4,row:1,colSpan:3,rowSpan:2},type:"crt.IndicatorWidget",config:{title:"#ResourceString(crtIndicatorWidget36551d0719c71252aea435e530446ecf_title)#",data:{providing:{schemaName:"VwExpiringLicense",aggregation:{column:{expression:{expressionType:1,functionType:2,aggregationType:1,aggregationEvalType:2,functionArgument:{expressionType:0,columnPath:"Id"}}}},filters:{filter:{items:{},logicalOperation:0,isEnabled:true,filterType:6,rootSchemaName:"VwExpiringLicense"}}},formatting:{type:"number",decimalSeparator:".",thousandSeparator:","}},text:{template:"#ResourceString(crtIndicatorWidget36551d0719c71252aea435e530446ecf_template)#",metricMacros:"{0}",fontSizeMode:"large"},layout:{color:"navy-blue"},theme:"full-fill"}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 340 згадок у конфігах. Мінімізовані імена класів не наводяться.*