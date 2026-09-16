---
type: crt.NextBestOffer
selector: crt-next-best-offer
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.NextBestOffer

Angular-селектор: `<crt-next-best-offer>`  
Група: **Бізнес-компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `alignCenter` | `false` |  |  |
| `hideScrollButtons` | `true` |  |  |
| `itemConfig` |  |  |  |
| `items` |  | `<binding>` |  |
| `loop` | `false` |  |  |
| `selectable` | `false` |  |  |
| `selectedItem` |  |  |  |
| `viewMode` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `selectedItemChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `specificPageRecordId` | `"NextBestOfferDS_Product"` |  |
| `useSpecificPage` | `true` |  |
| `specificPage` | `"Products_FormPage"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `itemConfig.templateValuesMapping` |  |  |
| `itemConfig.templateValuesMapping.caption` | `"NextBestOfferDS_Name"` |  |
| `itemConfig.templateValuesMapping.description` | `"NextBestOfferDS_ShortDescription"` |  |
| `itemConfig.templateValuesMapping.id` | `"NextBestOfferDS_Id"` |  |
| `itemConfig.templateValuesMapping.image` | `"NextBestOfferDS_ProductPicture"` |  |
| `itemConfig.templateValuesMapping.infoLabel` | `"NextBestOfferDS_Type"` |  |
| `itemConfig.templateValuesMapping.numberTag` | `"NextBestOfferDS_Score"` |  |
| `layoutConfig.colSpan` | `1` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `1` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{requiredFeatures:{ShowNextBestOfferComponent:true},icon:o(61919)},designViewItemCommands:{copy:"crt.CopyBaseImageListItemCommand"},typeCaption:"Components.NextBestOffer.Caption",propertiesPanelComponentTypeName:"crt.NextBestOfferPropertiesPanel",viewElementGroupType:F.J.Components,placeholderSize:{height:"60px"}}
```

## Приклад з реальної схеми


```json
{layoutConfig:{column:1,row:1,colSpan:1,rowSpan:1},type:"crt.NextBestOffer",visible:true,itemConfig:{templateValuesMapping:{caption:"NextBestOfferDS_Name",description:"NextBestOfferDS_ShortDescription",image:"NextBestOfferDS_ProductPicture",id:"NextBestOfferDS_Id",numberTag:"NextBestOfferDS_Score",infoLabel:"NextBestOfferDS_Type"}},items:"$NextBestOffer",specificPageRecordId:"NextBestOfferDS_Product",useSpecificPage:true,specificPage:"Products_FormPage"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (1851.hash=21f7ed8e55170b5b.js) + 28 згадок у конфігах. Мінімізовані імена класів не наводяться.*