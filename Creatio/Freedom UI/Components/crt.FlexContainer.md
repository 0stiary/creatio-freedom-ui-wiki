---
type: crt.FlexContainer
selector: crt-flex
group: "Layout"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FlexContainer

> Flex-контейнер (базовий блок компонування).

Angular-селектор: `<crt-flex>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на host-елемент) · `styles`: ✅ рендериться — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `alignItems` |  | `"center"`, `"stretch"`, `"flex-start"`, `"flex-end"` | `stretch` / `center` / `flex-start` |
| `direction` |  | `column` · `"row"`, `"column"` | `row` / `column` |
| `gap` |  | `"none"`, `"small"`, `"large"`, `"medium"`, `"extra-small"`, `8`, `"0px"` | `none` / `extra-small` / `small` / `medium` / `large` |
| `justifyContent` |  | `"start"`, `"space-between"`, `"end"`, `"center"` | `start` / `end` / `center` / `space-between` |
| `role` |  | `"banner"`, `"main"` |  |
| `wrap` |  | `"nowrap"`, `"wrap"` | `wrap` / `nowrap` |
| `borderRadius` |  | `"none"`, `"medium"` | `none`/`small`/`medium`/`large` |
| `color` |  | `"transparent"`, `"primary"` | `transparent` / `primary` / `primary-contrast-500`… |
| `elementResponsiveWidth` | `0` |  | (успадковано від базового класу) |
| `fitContent` | `true` | `true`, `false` | висота за вмістом |
| `items` | `[]` | `[]` | слот |
| `padding` |  | `"none"` | `{top,right,bottom,left}` |
| `responsiveWidth` |  |  | (успадковано від базового класу) |
| `stretch` | `false` | `true`, `false` | розтягнути на висоту батька |
| `visiblePadding` | `true` |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `innerScroll` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true`, `<binding>`, `false` | спільна → [[Common view-element properties#visible]] |
| `selected` | `true` | службовий стан дизайнера (виділення елемента в Page Designer) |
| `bodyBackgroundColor` | `"primary-contrast-100"` |  |
| `visibilityStrategyMode` | `"hide"` | спільна → [[Common view-element properties#visibilityStrategyMode]] |
| `ariaLive` | `"polite"` |  |
| `ariaLabel` | `"Main content"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `items[].type` | `"crt.Label"`, `"crt.FlexContainer"`, `"crt.Button"` |  |
| `items[].caption` | `<binding>`, `""` |  |
| `items[].classes` |  |  |
| `items[].color` | `"transparent"`, `"default"` |  |
| `items[].labelColor` | `"#0D2E4E"` |  |
| `items[].labelType` | `"headline-1"`, `"headline-3"` |  |
| `items[].name` | `"HeaderLabel"`, `"Label_"+_.N` |  |
| `items[].visible` | `true` |  |
| `items[].alignItems` | `"stretch"` |  |
| `items[].borderRadius` | `"none"` |  |
| `items[].clicked` |  |  |
| `items[].clicked.params` |  |  |
| `items[].clicked.params.nodeId` | `<binding>` |  |
| `items[].clicked.request` | `"usr.ToggleSelectionGroupRequest"` |  |
| `items[].defaultLocalizableStrings` |  |  |
| `items[].defaultLocalizableStrings.caption` |  |  |
| `items[].direction` | `"row"` |  |
| `items[].disabled` | `<binding>` |  |
| `items[].fitContent` | `true` |  |
| `items[].gap` | `"extra-small"` |  |
| `items[].iconPosition` | `"only-text"` |  |
| `items[].items` |  |  |
| `items[].items[].caption` | `<binding>` |  |
| `items[].items[].classes` |  |  |
| `items[].items[].clicked` |  |  |
| `items[].items[].clicked.params` |  |  |
| `items[].items[].clicked.request` | `"usr.ToggleSelectionGroupRequest"` |  |
| `items[].items[].color` | `"default"` |  |
| `items[].items[].disabled` | `<binding>` |  |
| `items[].items[].iconPosition` | `"only-text"` |  |
| `items[].items[].size` | `"medium"` |  |
| `items[].items[].type` | `"crt.Button"` |  |
| `items[].items[].visible` | `true` |  |
| `items[].justifyContent` | `"center"` |  |
| `items[].labelBackgroundColor` | `"transparent"` |  |
| `items[].labelEllipsis` | `false` |  |
| `items[].labelTextAlign` | `"start"` |  |
| `items[].labelThickness` | `"default"` |  |
| `items[].padding` |  |  |
| `items[].padding.bottom` | `"none"` |  |
| `items[].padding.left` | `"none"` |  |
| `items[].padding.right` | `"none"` |  |
| `items[].padding.top` | `"none"` |  |
| `items[].size` | `"medium"` |  |
| `items[].wrap` | `"nowrap"` |  |
| `layoutConfig.colSpan` | `1`, `2`, `8`, `4` |  |
| `layoutConfig.column` | `1`, `2`, `3`, `4` |  |
| `layoutConfig.row` | `1`, `2`, `3`, `5` |  |
| `layoutConfig.rowSpan` | `1`, `5`, `11`, `84`, `6` |  |
| `layoutConfig.width` | `420` |  |
| `padding.left` | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.right` | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.bottom` | `"none"`, `"small"`, `"medium"`, `"large"` |  |
| `padding.top` | `"none"`, `"medium"`, `"large"`, `"small"`, `null`, `"12px"` |  |
| `styles.border` | `"none"` |  |
| `styles.height` | `"600px"` |  |

## Приклад з реальної схеми


```json
{
					"layoutConfig": {
						"column": 2,
						"colSpan": 1,
						"row": 1,
						"rowSpan": 1
					},
					"type": "crt.FlexContainer",
					"direction": "column",
					"wrap": "nowrap",
					"items": [],
					"fitContent": true,
					"visible": true,
					"padding": {
						"top": "none",
						"right": "none",
						"bottom": "none",
						"left": "none"
					},
					"color": "transparent",
					"borderRadius": "none",
					"alignItems": "stretch",
					"justifyContent": "start",
					"gap": "small"
				}
```

## Нотатки

`layoutConfig` дитини Flex: `{width, minWidth, maxWidth, basis, grow, shrink}`.

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.FlexContainer** → *BaseLayoutContainer* → *BaseContainer* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.FlexContainer** (власні) | `alignItems`, `direction`, `gap`, `justifyContent`, `role`, `wrap` | `innerScroll` |  |
| *BaseLayoutContainer* | — | — | розкладка дітей: читає `layoutConfig` слот-елементів і перетворює на стилі (`getItemLayout`, `applySlotElementStyles`) |
| *BaseContainer* | `borderRadius`, `color`, `elementResponsiveWidth`, `fitContent`, `items`, `padding`, `responsiveWidth`, `stretch`, `visiblePadding` | — | контейнер: `items, padding, visiblePadding, borderRadius, color, stretch, fitContent, responsiveWidth, elementResponsiveWidth`; класи padding/color/borderRadius, реакція на resize |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

## Пов'язані

[[crt.GridContainer]], [[crt.ExpansionPanel]], [[crt.TemplateList]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 4223 згадок у конфігах. Мінімізовані імена класів не наводяться.*