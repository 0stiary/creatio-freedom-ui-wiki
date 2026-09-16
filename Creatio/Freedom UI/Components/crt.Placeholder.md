---
type: crt.Placeholder
selector: crt-placeholder
group: "Базові компоненти"
usage_in_configs: 11
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Placeholder

> Заглушка «немає даних» (у `DataGrid.placeholder`).

Angular-селектор: `<crt-placeholder>`  
Група: **Базові компоненти**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **11** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `image` |  | `{}`, `null` | 11 | `{type:"animation", name:"cat"\|"search"}` |
| `subhead` | `"Placeholder.Default.Subhead"` | `<binding>`, `null`, `""` | 11 |  |
| `title` | `"Placeholder.Default.Title"` | `<binding>`, `""` | 11 |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `loading` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `visible` | 8 | `<binding>` | `"$DataTable_NoItems"` |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `image.type` | 8 | `"animation"`, `"icon"` |  |
| `image.name` | 6 | `"search"`, `"cat"` |  |
| `image.height` | 2 | `null` |  |
| `image.icon` | 2 | `"data-table"`, `"list-widget"` |  |
| `image.padding` | 2 | `null` |  |
| `image.width` | 2 | `null` |  |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_1.js.завантаження`

```json
{type:"crt.Placeholder",image:{type:"animation",name:"search"},title:"#ResourceString(FilteredEmptySectionPlaceholderTitle)#",subhead:"#ResourceString(FilteredEmptySectionPlaceholderSubHead)#",visible:"$DataTable_NoFilteredItems"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2215.hash=c7626779519a0486.js) + 41 згадок у конфігах. Мінімізовані імена класів не наводяться.*