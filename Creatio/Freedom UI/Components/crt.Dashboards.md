---
type: crt.Dashboards
selector: crt-dashboards
group: "Дашборди та віджети"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Dashboards

> Вбудовані дашборди розділу.

Angular-селектор: `<crt-dashboards>`  
Група: **Дашборди та віджети**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `canManage` |  |  |  |  |
| `dashboards` |  |  |  |  |
| `filter` |  |  |  |  |
| `headerToolbarItems` | `[]` |  |  |  |
| `hierarchicalColumnValue` |  |  |  |  |
| `hierarchicalFilter` |  |  |  |  |
| `selectedDashboard` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `createDashboard` |  |  |
| `dashboardsOutdated` |  |  |
| `selectedDashboardChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `placeholder` | 2 | `true` | показувати заглушку |
| `_designOptions` | 2 |  | **прихована**: `{entitySchemaName, dependencies:[{attributePath, relationPath}], filters:[{attribute, loadOnChange}], hierarchyConfig}` — з цього препроцесор генерує атрибути `<Name>_Filter`/`_HierarchicalFilter` |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `_designOptions.dependencies` | 2 | `[]` |  |
| `_designOptions.filters` | 2 | `[]` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{hint:"Components.Dashboards.Hint",position:300,requiredFeatures:{FreedomUIDashboardsEnabled:true},icon:s(95141)},propertiesPanelComponentTypeName:"crt.DashboardsPropertiesPanel",typeCaption:"Components.Dashboards.Caption",viewElementGroupType:Me.J.Components,designViewItemCommands:{copy:"crt.CopyDataGridItemCommand",delete:"crt.RemoveDashboardsCommand"}}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_18.js.завантаження`

```json
{type:"crt.Dashboards",placeholder:true,_designOptions:{dependencies:[],filters:[]}}
```

## Пов'язані

[[crt.ChartWidget]], [[crt.IndicatorWidget]], [[crt.GaugeWidget]], [[crt.FunnelWidget]], [[crt.ListWidget]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2985.hash=c346ad02b7afdc2a.js) + 4 згадок у конфігах. Мінімізовані імена класів не наводяться.*