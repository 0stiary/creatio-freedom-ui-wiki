---
type: crt.NextSteps
selector: crt-next-steps
group: "Бізнес-компоненти"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.NextSteps

> Панель «Наступні кроки».

Angular-селектор: `<crt-next-steps>`  
Група: **Бізнес-компоненти**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `bindingColumns` |  | `[]` | 1 | колонки прив'язки нових активностей до майстер-запису |
| `canAdd` |  |  |  |  |
| `cardState` |  | `<binding>` | 2 |  |
| `dataLoading` | `false` |  |  |  |
| `galleryItemConfig` |  |  |  |  |
| `masterSchemaId` |  | `<binding>` | 2 |  |
| `masterSchemaName` |  | `"Case"` | 1 | об'єкт |
| `nextSteps` |  |  |  |  |
| `reloadNextSteps` |  |  |  |  |
| `tilesMap` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `reloadNextStepsChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 2 |  | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `layoutConfig.colSpan` | 1 | `2` |  |
| `layoutConfig.column` | 1 | `1` |  |
| `layoutConfig.row` | 1 | `1` |  |
| `layoutConfig.rowSpan` | 1 | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{designControlConfig:{allowDesignContent:true},propertiesPanelComponentTypeName:"crt.NextStepsPropertiesPanel",viewElementGroupType:Re.J.Components,typeCaption:"NextSteps.Caption"}
```

## Приклад з реальної схеми

Джерело: `Cases_FormPage.js`

```json
{
					"type": "crt.NextSteps",
					"masterSchemaId": "$Id",
					"cardState": "$CardState",
					"layoutConfig": {
						"colSpan": 2,
						"column": 1,
						"row": 1,
						"rowSpan": 1
					},
					"masterSchemaName": "Case",
					"bindingColumns": []
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7907.hash=e671ec9673e17f6d.js) + 9 згадок у конфігах. Мінімізовані імена класів не наводяться.*