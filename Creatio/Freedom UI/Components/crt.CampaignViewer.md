---
type: crt.CampaignViewer
selector: crt-campaign-viewer-7x-dt
group: "Бізнес-компоненти"
usage_in_configs: 1
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.CampaignViewer

Angular-селектор: `<crt-campaign-viewer-7x-dt>`  
Група: **Бізнес-компоненти**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **1** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `campaignId` |  |  |  |  |
| `fitContent` | `true` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `selector` | 1 | `"crt-campaign-viewer-7x"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{requiredFeatures:{EnableCampaignViewerDesignerItem:true},position:1,hint:"Components.CampaignViewer.Hint",icon:e(82385),defaultPropertyValues:{fitContent:true},defaultLocalizableStrings:{title:"Components.CampaignViewer.Caption"}},clientSchemaDeps:["CampaignViewerComponent"],typeCaption:"Components.CampaignViewer.Caption",viewElementGroupType:I.J.Components}
```

## Приклад з реальної схеми

Джерело: `2544.hash=abd05a3b2042cbcb.js`

```json
{type:"crt.CampaignViewer",selector:"crt-campaign-viewer-7x",reuseStrategy:L.B.Reuse}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2544.hash=abd05a3b2042cbcb.js) + 1 згадок у конфігах. Мінімізовані імена класів не наводяться.*