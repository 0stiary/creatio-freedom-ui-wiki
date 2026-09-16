---
type: crt.TableBooleanCell
selector: crt-data-table-boolean-cell
group: "Комірки гріда"
usage_in_configs: 4
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TableBooleanCell

Angular-селектор: `<crt-data-table-boolean-cell>`  
Група: **Комірки гріда**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **4** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `control` |  | `<binding>` | 3 |  |
| `readiness` | `false` | `<binding>` | 2 |  |
| `readonly` | `true` | `<binding>`, `false` | 4 |  |
| `column` |  |  |  | (успадковано від базового класу) |
| `record` |  |  |  | (успадковано від базового класу) |
| `value` |  |  |  | (успадковано від базового класу) |

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `tooltip` | 2 | `<binding>` |  |
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_18.js.завантаження`

```json
{type:"crt.TableBooleanCell",control:"$SelectedFormFieldsCollection.Hidden",readonly:"$SelectedFormFieldsCollection.ReadOnly",tooltip:"$SelectedFormFieldsCollection.Tooltip",readiness:"$SelectedFormFieldsCollection.Readiness"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 12 згадок у конфігах. Мінімізовані імена класів не наводяться.*