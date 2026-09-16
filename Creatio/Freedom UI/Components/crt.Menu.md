---
type: crt.Menu
selector: crt-menu
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Menu

Angular-селектор: `<crt-menu>`  
Група: **Базові компоненти**  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `context` |  |  |  |
| `items` |  |  |  |
| `menuItems` |  |  |  |
| `panelClass` |  |  |  |
| `stopOverlayClickPropagation` | `false` |  |  |
| `useGlassmorphism` |  |  |  |
| `xPosition` | `"after"` |  |  |
| `yPosition` | `"below"` |  |  |

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `name` |  | спільна → [[Common view-element properties#name]] |
| `id` |  | спільна → [[Common view-element properties#id]] |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |

## Приклад з реальної схеми


```json
{id:this._getNestedMenuId(at),name:at.name,type:"crt.Menu",items:at.items,panelClass:this._panelClass,useGlassmorphism:this._useGlassmorphism,visible:true}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 10 згадок у конфігах. Мінімізовані імена класів не наводяться.*