---
type: crt.Summaries
selector: crt-summaries
group: "Списки і дані"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Summaries

> Панель підсумків над гридом.

Angular-селектор: `<crt-summaries>`  
Група: **Списки і дані**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `actions` |  |  |  |
| `disabled` |  | `true` |  |
| `expanded` |  | `false`, `<binding>` |  |
| `items` |  | `[]` | масив `crt.SummaryItem` |
| `readonly` |  |  |  |
| `title` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `expandedChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `_designOptions` |  | **прихована**: `{modelName: "PDS"}` — джерело даних для агрегацій |
| `visible` | `false`, `true` | спільна → [[Common view-element properties#visible]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_designOptions.modelName` | `"GridDetail_1pq50ekDS"`, `"GridDetail_12go2z3DS"`, `"GridDetail_2ydt4vbDS"`, `"PDS"`, `"DataGrid_x3umv3rDS"`, `"DataGrid_xm741rqDS"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{typeCaption:"Components.Summaries.Caption",viewElementGroupType:Jt.J.Components,toolbarConfig:{position:190,icon:r(93616),defaultPropertyValues:{items:[]}},designControlConfig:{allowDesignContent:true},designViewItemCommands:{copy:"crt.CopySummariesCommand"},propertiesPanelComponentTypeName:"crt.SummariesPropertiesPanel",collectionPropertyNames:["items"]}
```

## Приклад з реальної схеми


```json
{
					"type": "crt.Summaries",
					"items": [],
					"visible": false,
					"disabled": true,
					"_designOptions": {
						"modelName": "GridDetail_1pq50ekDS"
					},
					"expanded": false
				}
```

## Пов'язані

[[crt.SummaryItem]], [[crt.DataGrid]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (6553.hash=41ee3da0cd19f881.js) + 112 згадок у конфігах. Мінімізовані імена класів не наводяться.*