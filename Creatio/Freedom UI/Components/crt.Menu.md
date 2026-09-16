---
type: crt.Menu
selector: crt-menu
group: "Базові компоненти"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Menu

Angular-селектор: `<crt-menu>`  
Група: **Базові компоненти**  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `context` |  |  |  |  |
| `items` |  |  | 2 |  |
| `menuItems` |  |  |  |  |
| `panelClass` |  |  | 2 |  |
| `stopOverlayClickPropagation` | `false` |  |  |  |
| `useGlassmorphism` |  |  | 2 |  |
| `xPosition` | `"after"` |  |  |  |
| `yPosition` | `"below"` |  |  |  |

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `name` | 2 |  | спільна → [[Common view-element properties#name]] |
| `id` | 1 |  | спільна → [[Common view-element properties#id]] |
| `visible` | 1 | `true` | спільна → [[Common view-element properties#visible]] |

## Приклад з реальної схеми

Джерело: `4223.hash=3d5a69794a1b3d08.js`

```json
{id:this._getNestedMenuId(at),name:at.name,type:"crt.Menu",items:at.items,panelClass:this._panelClass,useGlassmorphism:this._useGlassmorphism,visible:true}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 10 згадок у конфігах. Мінімізовані імена класів не наводяться.*