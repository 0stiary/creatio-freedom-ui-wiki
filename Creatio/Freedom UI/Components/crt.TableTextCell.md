---
type: crt.TableTextCell
selector: crt-data-table-text-cell
group: "Комірки гріда"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TableTextCell

> Текстова комірка гріда — використовується як `cellView` для кастомного форматування.

Angular-селектор: `<crt-data-table-text-cell>`  
Група: **Комірки гріда**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `column` |  |  | (успадковано від базового класу) |
| `record` |  |  | (успадковано від базового класу) |
| `value` |  |  | `"$Items.PDS_X \| usr.Converter"` |

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `name` |  | спільна → [[Common view-element properties#name]] |
| `disabled` | `true` | `true` для нередагованої |
| `control` |  | `"Items.PDS_X"` (без `$`) |

## Приклад з реальної схеми


```json
{
                            "name": cellViewName,
                            "type": "crt.TableTextCell",
                            "disabled": true,
                            "control": `${itemsAttributeName}.${columnName}`,
                            "value": `$${itemsAttributeName}.${columnName} | ${converterName}`
                        }
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 16 згадок у конфігах. Мінімізовані імена класів не наводяться.*