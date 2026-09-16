---
type: crt.LookupQuickFilterMenuItem
selector: crt-lookup-quick-filter-menu-item
group: "Фільтри"
usage_in_configs: 1
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.LookupQuickFilterMenuItem

Angular-селектор: `<crt-lookup-quick-filter-menu-item>`  
Група: **Фільтри**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **1** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `checkedState` |  |  |  |  |
| `checkedStateChange` |  |  | 1 |  |
| `displayValue` |  |  |  |  |
| `value` |  |  |  |  |

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `dataItemMarker` | 1 |  | маркер для автотестів (`ts-data-item-marker`) |

## Приклад з реальної схеми

Джерело: `3681.hash=5b6e27ea9c707070.js`

```json
{type:"crt.LookupQuickFilterMenuItem",checkedStateChange:T=>this._checkLookupFilterItemHandler(T),dataItemMarker:M.displayValue,...M}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (3681.hash=5b6e27ea9c707070.js) + 2 згадок у конфігах. Мінімізовані імена класів не наводяться.*