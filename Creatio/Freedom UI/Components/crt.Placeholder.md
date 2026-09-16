---
type: crt.Placeholder
selector: crt-placeholder
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Placeholder

> Заглушка «немає даних» (у `DataGrid.placeholder`).

Angular-селектор: `<crt-placeholder>`  
Група: **Базові компоненти**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `image` |  | `{}`, `null` | `{type:"animation", name:"cat"\|"search"}` |
| `subhead` | `"Placeholder.Default.Subhead"` | `<binding>`, `null`, `""` |  |
| `title` | `"Placeholder.Default.Title"` | `<binding>`, `""` |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `loading` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `<binding>` | `"$DataTable_NoItems"` |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `image.type` | `"animation"`, `"icon"` |  |
| `image.name` | `"search"`, `"cat"` |  |
| `image.height` | `null` |  |
| `image.icon` | `"data-table"`, `"list-widget"` |  |
| `image.padding` | `null` |  |
| `image.width` | `null` |  |

## Приклад з реальної схеми


```json
{type:"crt.Placeholder",image:{type:"animation",name:"search"},title:"#ResourceString(FilteredEmptySectionPlaceholderTitle)#",subhead:"#ResourceString(FilteredEmptySectionPlaceholderSubHead)#",visible:"$DataTable_NoFilteredItems"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2215.hash=c7626779519a0486.js) + 41 згадок у конфігах. Мінімізовані імена класів не наводяться.*