---
type: crt.TableColoredCell
selector: crt-data-table-colored-cell
group: "Комірки гріда"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TableColoredCell

> Кольорова комірка (lookup зі кольором, посилання).

Angular-селектор: `<crt-data-table-colored-cell>`  
Група: **Комірки гріда**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `caption` |  |  |  |
| `disableLink` |  |  |  |
| `displayValue` |  |  |  |
| `href` |  |  |  |
| `mode` |  |  |  |
| `target` |  |  |  |
| `column` |  |  | (успадковано від базового класу) |
| `record` |  |  | (успадковано від базового класу) |
| `value` |  |  | (успадковано від базового класу) |

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `clicked` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.TableColoredCell** → *BaseTableCell*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.TableColoredCell** (власні) | `caption`, `disableLink`, `displayValue`, `href`, `mode`, `target` | `clicked` |  |
| *BaseTableCell* | `column`, `record`, `value` | — | комірка гріда: `value, record, column`; `getTitle()` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*