---
type: crt.Approval
selector: crt-approval
group: "Бізнес-компоненти"
usage_in_configs: 1
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Approval

Angular-селектор: `<crt-approval>`  
Група: **Бізнес-компоненти**  
Слоти вкладених елементів (`contentSlots`): `items`  
Зустрічається в реальних конфігах: **1** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `activeColor` |  | `"white"` | 1 |  |
| `approval` |  |  |  |  |
| `approvalChangedHandler` |  |  |  |  |
| `approvalEntityName` |  | `"SysApproval"` | 1 |  |
| `approvalsMetrics` |  |  |  |  |
| `dataLoaded` |  |  |  |  |
| `entityName` |  | `"UsrPIMRequest"` | 1 |  |
| `hiddenWhenNoData` |  | `true` | 1 |  |
| `inactiveColor` |  | `"white"` | 1 |  |
| `linkedSchemaColumnName` |  |  |  |  |
| `linkedSchemaName` |  |  |  |  |
| `recordId` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `approve` |  |  |
| `createApproval` |  |  |
| `loadData` |  |  |
| `reject` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `items` | 1 | `[]` |  |
| `visible` | 1 | `true` | спільна → [[Common view-element properties#visible]] |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{icon:o(20875),defaultPropertyValues:{activeColor:"white",inactiveColor:"white",items:[]},position:120},typeCaption:"Components.Approval.Caption",propertiesPanelComponentTypeName:"crt.ApprovalPropertiesPanel",viewElementGroupType:ft.J.Components}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_26.js.завантаження`

```json
{type:"crt.Approval",activeColor:"white",inactiveColor:"white",items:[],entityName:"UsrPIMRequest",approvalEntityName:"SysApproval",visible:true,hiddenWhenNoData:true}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (5423.hash=0147d731c99b363a.js) + 7 згадок у конфігах. Мінімізовані імена класів не наводяться.*