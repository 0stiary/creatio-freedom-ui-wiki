---
type: crt.LookupQuickFilterMenuItem
selector: crt-lookup-quick-filter-menu-item
group: "Фільтри"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.LookupQuickFilterMenuItem

Angular-селектор: `<crt-lookup-quick-filter-menu-item>`  
Група: **Фільтри**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `checkedState` |  |  |  |
| `checkedStateChange` |  |  |  |
| `displayValue` |  |  |  |
| `value` |  |  |  |

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `dataItemMarker` |  | маркер для автотестів (`ts-data-item-marker`) |

## Приклад з реальної схеми


```json
{type:"crt.LookupQuickFilterMenuItem",checkedStateChange:T=>this._checkLookupFilterItemHandler(T),dataItemMarker:M.displayValue,...M}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.LookupQuickFilterMenuItem** → *(базовий клас не розв'язано — його модуль відсутній у збережених чанках Shell; за архітектурою це BaseViewElement)*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.LookupQuickFilterMenuItem** (власні) | `checkedState`, `checkedStateChange`, `displayValue`, `value` | — |  |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (3681.hash=5b6e27ea9c707070.js) + 2 згадок у конфігах. Мінімізовані імена класів не наводяться.*