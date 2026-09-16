---
type: crt.ApprovalList
selector: crt-approval-list
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ApprovalList

Angular-селектор: `<crt-approval-list>`  
Група: **Бізнес-компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `recordId` |  |  |  |
| `activeRow` |  |  | (успадковано від базового класу) |
| `bulkActions` | `[]` |  | (успадковано від базового класу) |
| `columns` |  |  | (успадковано від базового класу) |
| `editingCells` |  |  | (успадковано від базового класу) |
| `features` |  |  | (успадковано від базового класу) |
| `fitContent` |  |  | (успадковано від базового класу) |
| `header` |  |  | (успадковано від базового класу) |
| `headerToolbarItems` |  |  | (успадковано від базового класу) |
| `hierarchicalColumnName` |  |  | (успадковано від базового класу) |
| `items` |  |  | (успадковано від базового класу) |
| `maxHeight` |  |  | (успадковано від базового класу) |
| `primaryColumnName` |  |  | (успадковано від базового класу) |
| `rowToolbarItems` | `[]` |  | (успадковано від базового класу) |
| `selectedRows` |  |  | (успадковано від базового класу) |
| `selectionState` |  |  | (успадковано від базового класу) |
| `sorting` |  |  | (успадковано від базового класу) |
| `stretch` | `false` |  | (успадковано від базового класу) |
| `title` |  |  | (успадковано від базового класу) |
| `totalItemsCount` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `reloadData` |  |  |
| `activeRowChange` |  |  |
| `cancelItemsChanges` |  |  |
| `columnsChange` |  |  |
| `createItem` |  |  |
| `deleteItem` |  |  |
| `paginationChange` |  |  |
| `rowDoubleClick` |  |  |
| `saveItemsChanges` |  |  |
| `selectedRowsChange` |  |  |
| `selectionStateChange` |  |  |
| `sortingChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `masterRecordColumnValue` | `<binding>` |  |
| `recordColumnName` | `"RecordId"` |  |
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |

## Приклад з реальної схеми


```json
{name:"ApprovalList_"+c.N,type:"crt.ApprovalList",masterRecordColumnValue:"$Id",recordColumnName:"RecordId",layoutConfig:it(10)}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ApprovalList** → [[crt.DataGrid]] → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ApprovalList** (власні) | `recordId` | `reloadData` |  |
| [[crt.DataGrid]] | `activeRow`, `bulkActions`, `columns`, `editingCells`, `features`, `fitContent`, `header`, `headerToolbarItems`, `hierarchicalColumnName`, `items`, `maxHeight`, `primaryColumnName`, `rowToolbarItems`, `selectedRows`, `selectionState`, `sorting`, `stretch`, `title`, `totalItemsCount` | `activeRowChange`, `cancelItemsChanges`, `columnsChange`, `createItem`, `deleteItem`, `paginationChange`, `rowDoubleClick`, `saveItemsChanges`, `selectedRowsChange`, `selectionStateChange`, `sortingChange` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (5423.hash=0147d731c99b363a.js) + 4 згадок у конфігах. Мінімізовані імена класів не наводяться.*