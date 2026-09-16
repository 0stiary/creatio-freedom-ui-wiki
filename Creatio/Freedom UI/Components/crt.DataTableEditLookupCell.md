---
type: crt.DataTableEditLookupCell
selector: crt-data-table-edit-lookup-cell
group: "Комірки гріда"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.DataTableEditLookupCell

Angular-селектор: `<crt-data-table-edit-lookup-cell>`  
Група: **Комірки гріда**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `control` |  |  |  |
| `items` |  | `<binding>` |  |
| `listActions` |  |  |  |
| `mode` |  |  |  |
| `readonly` | `false` |  |  |
| `useStaticFiltering` | `false` | `true` |  |
| `value` |  | `<binding>` |  |

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `paginationChange` |  |  |
| `selectionWindowIconPressed` |  |  |
| `showList` |  |  |
| `valueChange` | `"crt.EditFormFieldRecordRequest"` |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `formControlConfig` |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `formControlConfig.relatesTo` | `"control"` |  |
| `valueChange.params` |  |  |
| `valueChange.params.collectionName` | `"SelectedFormFieldsCollection"` |  |
| `valueChange.params.fieldName` | `<binding>` |  |
| `valueChange.params.value` | `"@event"` |  |
| `valueChange.request` | `"crt.EditFormFieldRecordRequest"` |  |

## Приклад з реальної схеми


```json
{type:"crt.DataTableEditLookupCell",value:"$SelectedFormFieldsCollection.Caption",valueChange:{request:"crt.EditFormFieldRecordRequest",params:{fieldName:"$SelectedFormFieldsList_ActiveRow",collectionName:"SelectedFormFieldsCollection",value:"@event"}},items:"$AvailableFormFields",useStaticFiltering:true}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.DataTableEditLookupCell** → *(базовий клас не розв'язано — його модуль відсутній у збережених чанках Shell; за архітектурою це BaseViewElement)*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.DataTableEditLookupCell** (власні) | `control`, `items`, `listActions`, `mode`, `readonly`, `useStaticFiltering`, `value` | `paginationChange`, `selectionWindowIconPressed`, `showList`, `valueChange` |  |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 10 згадок у конфігах. Мінімізовані імена класів не наводяться.*