---
type: crt.Playbook
selector: crt-playbook
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Playbook

Angular-селектор: `<crt-playbook>`  
Група: **Бізнес-компоненти**  
reuseStrategy: `Reuse`  
`classes`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `items` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:280,icon:t(19702),hint:"Playbook.Hint"},typeCaption:"Playbook.Caption",propertiesPanelComponentTypeName:"crt.PlaybookPropertiesPanel",viewElementGroupType:O.J.Components}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*