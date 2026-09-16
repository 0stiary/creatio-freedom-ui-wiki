---
type: crt.DataTableEditLookupCell
selector: crt-data-table-edit-lookup-cell
group: "Комірки гріда"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.DataTableEditLookupCell

Angular-селектор: `<crt-data-table-edit-lookup-cell>`  
Група: **Комірки гріда**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `control` |  |  | 1 |  |
| `items` |  | `<binding>` | 2 |  |
| `listActions` |  |  |  |  |
| `mode` |  |  |  |  |
| `readonly` | `false` |  |  |  |
| `useStaticFiltering` | `false` | `true` | 2 |  |
| `value` |  | `<binding>` | 2 |  |

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

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |
| `valueChange.params` | 2 |  |  |
| `valueChange.params.collectionName` | 2 | `"SelectedFormFieldsCollection"` |  |
| `valueChange.params.fieldName` | 2 | `<binding>` |  |
| `valueChange.params.value` | 2 | `"@event"` |  |
| `valueChange.request` | 2 | `"crt.EditFormFieldRecordRequest"` |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_18.js.завантаження`

```json
{type:"crt.DataTableEditLookupCell",value:"$SelectedFormFieldsCollection.Caption",valueChange:{request:"crt.EditFormFieldRecordRequest",params:{fieldName:"$SelectedFormFieldsList_ActiveRow",collectionName:"SelectedFormFieldsCollection",value:"@event"}},items:"$AvailableFormFields",useStaticFiltering:true}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 10 згадок у конфігах. Мінімізовані імена класів не наводяться.*