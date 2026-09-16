---
type: crt.EditTypedValueCell
selector: crt-edit-typed-value-cell
group: "Комірки гріда"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.EditTypedValueCell

Angular-селектор: `<crt-edit-typed-value-cell>`  
Група: **Комірки гріда**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `config` |  |  |  |
| `dataValueType` |  | `<binding>` |  |
| `valueAttribute` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `config.items` | `<binding>` |  |
| `config.showList` |  |  |
| `config.showList.params` |  |  |
| `config.showList.params.itemsAttributeName` | `"DynamicLookupValuesList"` |  |
| `config.showList.params.referenceSchemaName` | `<binding>` |  |
| `config.showList.request` | `"crt.LoadDefaultValueLookupListRequest"` |  |

## Приклад з реальної схеми


```json
{type:"crt.EditTypedValueCell",config:{items:"$DynamicLookupValuesList",showList:{request:"crt.LoadDefaultValueLookupListRequest",params:{referenceSchemaName:"$SelectedFormFieldsCollection.ReferenceSchemaName",itemsAttributeName:"DynamicLookupValuesList"}}},dataValueType:"$SelectedFormFieldsCollection.Type",valueAttribute:"SelectedFormFieldsCollection.DefaultValue"}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.EditTypedValueCell** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.EditTypedValueCell** (власні) | `config`, `dataValueType`, `valueAttribute` | — |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 6 згадок у конфігах. Мінімізовані імена класів не наводяться.*