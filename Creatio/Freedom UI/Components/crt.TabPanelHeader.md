---
type: crt.TabPanelHeader
selector: crt-tab-panel-header
group: "Layout"
usage_in_configs: 1
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.TabPanelHeader

Angular-селектор: `<crt-tab-panel-header>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `tabs`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **1** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `selectedTabIndex` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `tabs` | 1 |  |  |

## Приклад з реальної схеми

Джерело: `4223.hash=3d5a69794a1b3d08.js`

```json
{type:"crt.TabPanelHeader",tabs:N.items?.map(rt=>({...Object.fromEntries(K.filter(St=>typeof rt[St]<"u").map(St=>[St,rt[St]])),type:"crt.TabPanelHeaderItem",name:rt.name,titleColor:N.tabTitleColor,selectedTitleColor:N.selectedTabTitleColor,styleType:N.styleType}))}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 1 згадок у конфігах. Мінімізовані імена класів не наводяться.*