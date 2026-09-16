---
type: crt.SkipLinks
selector: crt-skip-links
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.SkipLinks

Angular-селектор: `<crt-skip-links>`  
Група: **Базові компоненти**  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `links` | `[]` |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `links[].elementSelectors` |  |  |
| `links[].label` | `<binding>` |  |

## Приклад з реальної схеми


```json
{type:"crt.SkipLinks",links:[{label:"#ResourceString(SkipLinkToNavigation_caption)#",elementSelectors:["#LeftNavigationPanel","crt-navigation-panel-button button"]},{label:"#ResourceString(SkipLinkToMainContent_caption)#",elementSelectors:["#RouterOutlet"]},]}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (887.hash=700fed5564cae876.js) + 2 згадок у конфігах. Мінімізовані імена класів не наводяться.*