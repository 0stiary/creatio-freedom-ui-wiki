---
type: crt.TemplateList
selector: crt-template-list
group: "Списки і дані"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TemplateList

> Список, що рендерить `template` для кожного елемента колекції view-моделей. Подій не має; перемальовується на `items.changed`.

Angular-селектор: `<crt-template-list>`  
Група: **Списки і дані**  
Слоти вкладених елементів (`contentSlots`): `template`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `direction` |  | `"column"` | 2 | `row` / `column` — прокидається у внутрішній `crt-flex` |
| `gap` |  | `2`, `0` | 2 | відстань між рядками |
| `items` |  | `<binding>` | 2 | `"$Collection"` — атрибут з `isCollection: true` |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `template` | 2 |  | **слот** (`contentSlots: template`, lazy) — масив view-конфігу одного рядка; всередині біндінги `$Collection.Attr` |
| `layoutConfig` | 2 |  | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `layoutConfig.colSpan` | 2 | `1` |  |
| `layoutConfig.column` | 2 | `1` |  |
| `layoutConfig.row` | 2 | `1` |  |
| `layoutConfig.rowSpan` | 2 | `1` |  |
| `template[].alignItems` | 1 | `"stretch"` |  |
| `template[].borderRadius` | 1 | `"none"` |  |
| `template[].color` | 1 | `"transparent"` |  |
| `template[].columns` | 1 |  |  |
| `template[].gap` | 1 |  |  |
| `template[].gap.columnGap` | 1 | `"large"` |  |
| `template[].gap.rowGap` | 1 | `"none"` |  |
| `template[].items` | 1 |  |  |
| `template[].items[].alignItems` | 1 | `"center"` |  |
| `template[].items[].borderRadius` | 1 | `"none"` |  |
| `template[].items[].classes` | 1 | `<binding>` |  |
| `template[].items[].color` | 1 | `"transparent"` |  |
| `template[].items[].direction` | 1 | `"row"` |  |
| `template[].items[].fitContent` | 1 | `true` |  |
| `template[].items[].gap` | 1 | `"small"` |  |
| `template[].items[].items` | 1 |  |  |
| `template[].items[].items[].alignItems` | 1 | `"stretch"` |  |
| `template[].items[].items[].borderRadius` | 1 | `"none"` |  |
| `template[].items[].items[].classes` | 1 |  |  |
| `template[].items[].items[].color` | 1 | `"transparent"` |  |
| `template[].items[].items[].direction` | 1 | `"row"` |  |
| `template[].items[].items[].fitContent` | 1 | `true` |  |
| `template[].items[].items[].gap` | 1 | `"extra-small"` |  |
| `template[].items[].items[].items` | 1 |  |  |
| `template[].items[].items[].justifyContent` | 1 | `"center"` |  |
| `template[].items[].items[].padding` | 1 |  |  |
| `template[].items[].items[].type` | 1 | `"crt.FlexContainer"` |  |
| `template[].items[].items[].visible` | 1 | `true` |  |
| `template[].items[].items[].wrap` | 1 | `"nowrap"` |  |
| `template[].items[].justifyContent` | 1 | `"space-between"` |  |
| `template[].items[].layoutConfig` | 1 |  |  |
| `template[].items[].layoutConfig.colSpan` | 1 | `1` |  |
| `template[].items[].layoutConfig.column` | 1 | `1` |  |
| `template[].items[].layoutConfig.row` | 1 | `1` |  |
| `template[].items[].layoutConfig.rowSpan` | 1 | `1` |  |
| `template[].items[].padding` | 1 |  |  |
| `template[].items[].padding.bottom` | 1 | `"none"` |  |
| `template[].items[].padding.left` | 1 | `"none"` |  |
| `template[].items[].padding.right` | 1 | `"none"` |  |
| `template[].items[].padding.top` | 1 | `"none"` |  |
| `template[].items[].type` | 1 | `"crt.FlexContainer"` |  |
| `template[].items[].visible` | 1 | `true` |  |
| `template[].items[].wrap` | 1 | `"wrap"` |  |
| `template[].padding` | 1 |  |  |
| `template[].padding.bottom` | 1 | `"none"` |  |
| `template[].padding.left` | 1 | `"none"` |  |
| `template[].padding.right` | 1 | `"medium"` |  |
| `template[].padding.top` | 1 | `"none"` |  |
| `template[].rows` | 1 | `"minmax(max-content, 32px)"` |  |
| `template[].styles` | 1 |  |  |
| `template[].type` | 1 | `"crt.GridContainer"` |  |
| `template[].visible` | 1 | `true` |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_2.js.завантаження`

```json
{type:"crt.TemplateList",items:"$UsrCaseFilterNodes",direction:"column",gap:2,template:[{type:"crt.GridContainer",rows:"minmax(max-content, 32px)",columns:["minmax(32px, 1fr)"],gap:{columnGap:"large",rowGap:"none"},styles:{"overflow-x":"hidden"},items:[{type:"crt.FlexContainer",direction:"row",items:[{type:"crt.FlexContainer",direction:"row",items:[{type:"crt.Button",caption:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_Parent | usr.FilterNodeCaptionConverter",color:"default",disabled:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_Parent | usr.FilterNodeIconButtonDisabled",size:"medium",iconPosition:"only-text",visible:true,classes:["usr-filter-nodes-list-item-icon-button"],clicked:{request:"usr.ToggleSelectionGroupRequest",params:{nodeId:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_Id"}}},{type:"crt.Button",caption:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_Name",color:"default",disabled:false,size:"medium",iconPosition:"only-text",visible:true,classes:["usr-filter-nodes-list-item-caption-button"],clicked:{request:"usr.SelectFilterNode",params:{nodeId:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_Id"}}}],fitContent:true,visible:true,color:"transparent",borderRadius:"none",padding:{top:"none",right:"none",bottom:"none",left:"none"},alignItems:"stretch",justifyContent:"center",gap:"extra-small",wrap:"nowrap",classes:["usr-filter-nodes-list-row-content"]},{type:"crt.Label",caption:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_RecordsCount | usr.FilterNodeCountCaptionConverter",labelType:"caption-large",labelThickness:"default",labelEllipsis:false,labelColor:"auto",labelBackgroundColor:"transparent",labelTextAlign:"center",headingLevel:"label",visible:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_RecordsCount | crt.IsEqual : 0 | crt.InvertBooleanValue"}],fitContent:true,visible:true,color:"transparent",borderRadius:"none",padding:{top:"none",right:"none",bottom:"none",left:"none"},alignItems:"center",justifyContent:"space-between",gap:"small",wrap:"wrap",layoutConfig:{column:1,colSpan:1,row:1,rowSpan:1},classes:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_Id | usr.FilterNodeClassesConverter"}],visible:true,color:"transparent",borderRadius:"none",padding:{top:"none",right:"medium",bottom:"none",left:"none"},alignItems:"stretch"}],classes:["usr-filter-nodes-list"],layoutConfig:{colSpan:1,column:1,row:1,rowSpan:1}}
```

## Нотатки

- Контекст кожного рядка = view-модель елемента колекції: у конвертерах другий аргумент — саме вона (`(value, itemVm, ...args)`), тому `itemVm.attributes.X` доступні.
- Компонент **не** емітить подій «відрендерено»; перемальовка відбувається лише коли колекція `changed` (load/reload). Якщо контейнер (вкладка) знищується і створюється знову — рядки рендеряться заново без будь-якої події у схемі.
- Для стану рядків (виділення, розгортання) використовуйте біндінги `classes`/`styles`/`visible` з конвертерами замість DOM-маніпуляцій.

## Пов'язані

[[crt.DataGrid]], [[crt.FlexContainer]], [[crt.GridContainer]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 12 згадок у конфігах. Мінімізовані імена класів не наводяться.*