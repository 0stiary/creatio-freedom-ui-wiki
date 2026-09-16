---
type: crt.EntityStageProgressBar
selector: crt-entity-stage-progress-bar
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.EntityStageProgressBar

> Індикатор стадій (DCM).

Angular-селектор: `<crt-entity-stage-progress-bar>`  
Група: **Бізнес-компоненти**  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `allowedStages` | `null` |  |  |
| `askUserToChangeSchema` |  | `true` | питати про зміну схеми кейсу |
| `currentStage` |  |  |  |
| `entityName` |  | `"UsrPendingLines"`, `"UsrPIMRequest"` | об'єкт |
| `isAppropriateEntityStageSchema` |  |  |  |
| `recordId` |  |  |  |
| `saveOnChange` |  | `false`, `true` | зберігати запис при зміні стадії |
| `stageConnections` |  |  |  |
| `stageRunningProcessUId` |  |  |  |
| `stageSchemaFilterByValue` |  |  |  |
| `stages` |  |  |  |
| `value` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `changeToAppropriateEntityStageSchema` |  |  |
| `checkIsAnAppropriateProcessSchema` |  |  |
| `loadData` |  |  |
| `setAllowedStages` |  |  |
| `stageChanged` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{icon:l(99249),hint:"Components.ProgressBar.Hint",position:130,defaultPropertyValues:{saveOnChange:false,askUserToChangeSchema:true}},typeCaption:"Components.ProgressBar.Caption",propertiesPanelComponentTypeName:"crt.EntityStageProgressBarPropertiesPanel",viewElementGroupType:xt.J.Components}
```

## Приклад з реальної схеми


```json
{
					"type": "crt.EntityStageProgressBar",
					"saveOnChange": false,
					"askUserToChangeSchema": true,
					"entityName": "UsrPendingLines"
				}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.EntityStageProgressBar** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.EntityStageProgressBar** (власні) | `allowedStages`, `askUserToChangeSchema`, `currentStage`, `entityName`, `isAppropriateEntityStageSchema`, `recordId`, `saveOnChange`, `stageConnections`, `stageRunningProcessUId`, `stageSchemaFilterByValue`, `stages`, `value` | `changeToAppropriateEntityStageSchema`, `checkIsAnAppropriateProcessSchema`, `loadData`, `setAllowedStages`, `stageChanged` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

## Пов'язані

[[crt.DataGrid]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (9592.hash=4d3322d5f61331bb.js) + 10 згадок у конфігах. Мінімізовані імена класів не наводяться.*