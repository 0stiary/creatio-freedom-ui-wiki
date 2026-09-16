---
type: crt.EditTypedValueCell
selector: crt-edit-typed-value-cell
group: "Комірки гріда"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.EditTypedValueCell

Angular-селектор: `<crt-edit-typed-value-cell>`  
Група: **Комірки гріда**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `config` |  |  | 2 |  |
| `dataValueType` |  | `<binding>` | 2 |  |
| `valueAttribute` |  |  | 2 |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `config.items` | 2 | `<binding>` |  |
| `config.showList` | 2 |  |  |
| `config.showList.params` | 2 |  |  |
| `config.showList.params.itemsAttributeName` | 2 | `"DynamicLookupValuesList"` |  |
| `config.showList.params.referenceSchemaName` | 2 | `<binding>` |  |
| `config.showList.request` | 2 | `"crt.LoadDefaultValueLookupListRequest"` |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_18.js.завантаження`

```json
{type:"crt.EditTypedValueCell",config:{items:"$DynamicLookupValuesList",showList:{request:"crt.LoadDefaultValueLookupListRequest",params:{referenceSchemaName:"$SelectedFormFieldsCollection.ReferenceSchemaName",itemsAttributeName:"DynamicLookupValuesList"}}},dataValueType:"$SelectedFormFieldsCollection.Type",valueAttribute:"SelectedFormFieldsCollection.DefaultValue"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 6 згадок у конфігах. Мінімізовані імена класів не наводяться.*