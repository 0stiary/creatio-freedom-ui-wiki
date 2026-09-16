---
type: crt.EntityHierarchyFilter
selector: crt-entity-hierarchy-filter
group: "Фільтри"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.EntityHierarchyFilter

> Ієрархічний фільтр (дерево вузлів об'єкта).

Angular-селектор: `<crt-entity-hierarchy-filter>`  
Група: **Фільтри**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `displayMode` |  | `"manualDisplayMode"` |  |
| `expandedItems` |  |  |  |
| `nodes` |  |  |  |
| `searchResultNodes` |  |  |  |
| `selectedNodeId` |  |  |  |
| `selectedTabIndex` | `1` |  |  |
| `specificationEntityName` |  |  |  |
| `specificationFiltersConfiguration` |  |  |  |
| `specificationReferenceColumnName` |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `expandedItemsChange` |  |  |
| `loadNext` |  |  |
| `loadSearchNext` |  |  |
| `loadSpecificationFilters` |  |  |
| `nodeClick` |  |  |
| `specificationFilterChange` |  |  |
| `tabIndexChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `_filterOptions` |  | **прихована**: expose-атрибут фільтра для гріда |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `schemaName` | `"Case"` | **прихована**: об'єкт дерева |
| `nodesConfig` |  | **прихована**: конфіг вузлів |
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `_filterOptions.expose` |  |  |
| `_filterOptions.from` |  |  |
| `_filterOptions.expose[].attribute` | `"EntityHierarchyFilter_i03k17b_Filters"` |  |
| `_filterOptions.expose[].converters` |  |  |
| `_filterOptions.expose[].converters[].converter` | `"crt.ToHierarchyFiltersConverter"` |  |
| `layoutConfig.height` | `507` |  |
| `nodesConfig[].children` | `[]` |  |
| `nodesConfig[].columnName` | `"Category"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:290,icon:c(27778),hint:"Components.EntityHierarchyFilter.Hint"},typeCaption:"Components.EntityHierarchyFilter.Caption",viewElementGroupType:mt.J.Components,propertiesPanelComponentTypeName:"crt.EntityHierarchyFilterPropertiesPanel",designViewItemCommands:{create:"crt.CreateEntityHierarchyFilterComponentCommand",update:"crt.ChangeFilterViewItemCommand",delete:"crt.RemoveFilterViewItemCommand"}}
```

## Приклад з реальної схеми


```json
{
					"type": "crt.EntityHierarchyFilter",
					"_filterOptions": {
						"from": "EntityHierarchyFilter_i03k17b_SelectedNode",
						"expose": [
							{
								"attribute": "EntityHierarchyFilter_i03k17b_Filters",
								"converters": [
									{
										"converter": "crt.ToHierarchyFiltersConverter"
									}
								]
							}
						]
					},
					"displayMode": "manualDisplayMode",
					"visible": true,
					"schemaName": "Case",
					"nodesConfig": [
						{
							"columnName": "Category",
							"children": []
						}
					],
					"layoutConfig": {
						"height": 507
					}
				}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.EntityHierarchyFilter** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.EntityHierarchyFilter** (власні) | `displayMode`, `expandedItems`, `nodes`, `searchResultNodes`, `selectedNodeId`, `selectedTabIndex`, `specificationEntityName`, `specificationFiltersConfiguration`, `specificationReferenceColumnName` | `expandedItemsChange`, `loadNext`, `loadSearchNext`, `loadSpecificationFilters`, `nodeClick`, `specificationFilterChange`, `tabIndexChange` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (3692.hash=0d34c9d0ea062d58.js) + 12 згадок у конфігах. Мінімізовані імена класів не наводяться.*