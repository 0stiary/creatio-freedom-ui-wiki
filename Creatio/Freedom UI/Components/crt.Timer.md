---
type: crt.Timer
selector: crt-timer
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Timer

Angular-селектор: `<crt-timer>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `adjustToUserTimezone` |  |  |  |
| `control` |  |  |  |
| `negativeTextColor` |  |  |  |
| `negativeTextValue` |  |  |  |
| `positiveTextColor` |  |  |  |
| `positiveTextValue` |  |  |  |
| `showNegativeCountDownValue` |  |  |  |
| `timerType` |  |  |  |
| `headingLevel` |  |  | (успадковано від базового класу) |
| `labelBackgroundColor` |  |  | (успадковано від базового класу) |
| `labelElementType` |  |  | (успадковано від базового класу) |
| `labelTextAlign` |  |  | (успадковано від базового класу) |
| `caption` |  |  | (успадковано від базового класу) |
| `labelColor` |  |  | (успадковано від базового класу) |
| `labelEllipsis` |  |  | (успадковано від базового класу) |
| `labelFontFamily` |  |  | (успадковано від базового класу) |
| `labelFontSize` |  |  | (успадковано від базового класу) |
| `labelHeight` |  |  | (успадковано від базового класу) |
| `labelLetterSpacing` |  |  | (успадковано від базового класу) |
| `labelLineHeight` |  |  | (успадковано від базового класу) |
| `labelMargin` |  |  | (успадковано від базового класу) |
| `labelStyle` | `{}` |  | (успадковано від базового класу) |
| `labelTextTransform` |  |  | (успадковано від базового класу) |
| `labelThickness` |  |  | (успадковано від базового класу) |
| `labelType` |  | `button` | (успадковано від базового класу) |
| `required` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:270,icon:t(60306),defaultPropertyValues:{caption:"Timer",labelType:"body",labelThickness:"normal",labelEllipsis:false,labelColor:"#0B8500",labelBackgroundColor:"transparent",labelTextAlign:"start",timerType:r.a.FromDate,showNegativeCountDownValue:true,negativeTextColor:"#D2310D",positiveTextColor:"#0B8500",positiveTextValue:"",negativeTextValue:""},defaultLocalizableStrings:{caption:"DataValueType.TimerCaption",label:"DataValueType.TimerCaption"}},propertiesPanelComponentTypeName:"crt.TimerPropertiesPanel",viewElementGroupType:_.J.Components,typeCaption:"DataValueType.TimerCaption",dataValueTypes:[i.r.Date,i.r.Time,i.r.DateTime],placeholderSize:{height:"20px"}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*