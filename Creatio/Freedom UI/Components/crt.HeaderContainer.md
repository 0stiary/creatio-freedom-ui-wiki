---
type: crt.HeaderContainer
selector: crt-header
group: "Layout"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.HeaderContainer

Angular-селектор: `<crt-header>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ✅ рендериться — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `title` |  |  |  |  |
| `borderRadius` |  |  |  | (успадковано від базового класу) |
| `color` |  | `"primary"` | 2 | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` |  |  | (успадковано від базового класу) |
| `fitContent` | `true` | `true` | 2 | (успадковано від базового класу) |
| `items` | `[]` | `[]` | 2 | (успадковано від базового класу) |
| `padding` |  |  | 2 | (успадковано від базового класу) |
| `responsiveWidth` |  |  |  | (успадковано від базового класу) |
| `stretch` | `false` |  |  | (успадковано від базового класу) |
| `visiblePadding` | `true` |  |  | (успадковано від базового класу) |

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
| `padding.left` | 2 | `"large"` |  |
| `padding.right` | 2 | `"large"` |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_1.js.завантаження`

```json
{type:"crt.HeaderContainer",color:"primary",padding:{right:"large",left:"large"},fitContent:true,items:[]}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 8 згадок у конфігах. Мінімізовані імена класів не наводяться.*