---
type: crt.GaugeWidget
selector: crt-gauge-widget
group: "Дашборди та віджети"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.GaugeWidget

Angular-селектор: `<crt-gauge-widget>`  
Група: **Дашборди та віджети**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `config` |  |  |  |
| `isDesignTime` |  |  |  |
| `data` |  |  | (успадковано від базового класу) |
| `drilldownEnabled` | `true` |  | (успадковано від базового класу) |
| `listConfig` |  |  | (успадковано від базового класу) |
| `listData` |  |  | (успадковано від базового класу) |
| `pagingConfig` |  |  | (успадковано від базового класу) |
| `searchValue` | `""` |  | (успадковано від базового класу) |
| `sectionBindingColumnRecordId` |  |  | (успадковано від базового класу) |
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

У реальних конфігах додаткових властивостей не знайдено.

## Приклад з реальної схеми


```json
{type:"crt.GaugeWidget",reuseStrategy:u.B.Reuse,renderStrategy:g.D.OnViewport,placeholderSize:{height:"98px"},compatibleAPIs:{[_.I.Filtration]:{enable:true,aggregation:true}}}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.GaugeWidget** → [[crt.IndicatorWidget]] → *BaseWidget* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.GaugeWidget** (власні) | `config`, `isDesignTime` | — |  |
| [[crt.IndicatorWidget]] | `data`, `drilldownEnabled` | — |  |
| *BaseWidget* | `listConfig`, `listData`, `pagingConfig`, `searchValue`, `sectionBindingColumnRecordId`, `sortingConfig`, `toolbarMenuItems`, `userProfileData` | `columnsChange`, `drillDown`, `fullScreenStateChanged`, `getProfileColumns`, `paginationChange`, `resetToDefault`, `searchFilterChange`, `sortingChange` | віджет дашборда: `sectionBindingColumnRecordId, toolbarMenuItems, listConfig, userProfileData, listData, searchValue, pagingConfig, sortingConfig`; події `drillDown, paginationChange, columnsChange, resetToDefault, getProfileColumns, sortingChange, searchFilterChange, fullScreenStateChanged` |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*