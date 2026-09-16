---
type: crt.Approval
selector: crt-approval
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Approval

Angular-селектор: `<crt-approval>`  
Група: **Бізнес-компоненти**  
Слоти вкладених елементів (`contentSlots`): `items`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `activeColor` |  | `"white"` |  |
| `approval` |  |  |  |
| `approvalChangedHandler` |  |  |  |
| `approvalEntityName` |  | `"SysApproval"` |  |
| `approvalsMetrics` |  |  |  |
| `dataLoaded` |  |  |  |
| `entityName` |  | `"UsrPIMRequest"` |  |
| `hiddenWhenNoData` |  | `true` |  |
| `inactiveColor` |  | `"white"` |  |
| `linkedSchemaColumnName` |  |  |  |
| `linkedSchemaName` |  |  |  |
| `recordId` |  |  |  |

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

| Властивість | Значення | Що робить |
|---|---|---|
| `items` | `[]` |  |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{icon:o(20875),defaultPropertyValues:{activeColor:"white",inactiveColor:"white",items:[]},position:120},typeCaption:"Components.Approval.Caption",propertiesPanelComponentTypeName:"crt.ApprovalPropertiesPanel",viewElementGroupType:ft.J.Components}
```

## Приклад з реальної схеми


```json
{type:"crt.Approval",activeColor:"white",inactiveColor:"white",items:[],entityName:"UsrPIMRequest",approvalEntityName:"SysApproval",visible:true,hiddenWhenNoData:true}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.Approval** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.Approval** (власні) | `activeColor`, `approval`, `approvalChangedHandler`, `approvalEntityName`, `approvalsMetrics`, `dataLoaded`, `entityName`, `hiddenWhenNoData`, `inactiveColor`, `linkedSchemaColumnName`, `linkedSchemaName`, `recordId` | `approve`, `createApproval`, `loadData`, `reject` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (5423.hash=0147d731c99b363a.js) + 7 згадок у конфігах. Мінімізовані імена класів не наводяться.*