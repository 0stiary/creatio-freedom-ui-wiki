---
type: crt.FlexContainer
selector: crt-flex
group: "Layout"
usage_in_configs: 654
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.FlexContainer

> Flex-контейнер (базовий блок компонування).

Angular-селектор: `<crt-flex>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **654** раз(ів)  
`classes`: ✅ рендериться (на host-елемент) · `styles`: ✅ рендериться — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `alignItems` |  | `"center"`, `"stretch"`, `"flex-start"`, `"flex-end"` | 536 | `stretch` / `center` / `flex-start` |
| `direction` |  | `column` · `"row"`, `"column"` | 652 | `row` / `column` |
| `gap` |  | `"none"`, `"small"`, `"large"`, `"medium"`, `"extra-small"`, `8`, `"0px"` | 494 | `none` / `extra-small` / `small` / `medium` / `large` |
| `justifyContent` |  | `"start"`, `"space-between"`, `"end"`, `"center"` | 203 | `start` / `end` / `center` / `space-between` |
| `role` |  | `"banner"`, `"main"` | 4 |  |
| `wrap` |  | `"nowrap"`, `"wrap"` | 213 | `wrap` / `nowrap` |
| `borderRadius` |  | `"none"`, `"medium"` | 181 | `none`/`small`/`medium`/`large` |
| `color` |  | `"transparent"`, `"primary"` | 182 | `transparent` / `primary` / `primary-contrast-500`… |
| `elementResponsiveWidth` | `0` |  |  | (успадковано від базового класу) |
| `fitContent` | `true` | `true`, `false` | 236 | висота за вмістом |
| `items` | `[]` | `[]` | 654 | слот |
| `padding` |  | `"none"` | 194 | `{top,right,bottom,left}` |
| `responsiveWidth` |  |  |  | (успадковано від базового класу) |
| `stretch` | `false` | `true`, `false` | 44 | розтягнути на висоту батька |
| `visiblePadding` | `true` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `innerScroll` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 383 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 177 | `true`, `<binding>`, `false` | спільна → [[Common view-element properties#visible]] |
| `selected` | 4 | `true` | службовий стан дизайнера (виділення елемента в Page Designer) |
| `bodyBackgroundColor` | 2 | `"primary-contrast-100"` |  |
| `visibilityStrategyMode` | 2 | `"hide"` | спільна → [[Common view-element properties#visibilityStrategyMode]] |
| `ariaLive` | 2 | `"polite"` |  |
| `ariaLabel` | 2 | `"Main content"` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `items[].type` | 4 | `"crt.Label"`, `"crt.FlexContainer"`, `"crt.Button"` |  |
| `items[].caption` | 3 | `<binding>`, `""` |  |
| `items[].classes` | 2 |  |  |
| `items[].color` | 2 | `"transparent"`, `"default"` |  |
| `items[].labelColor` | 2 | `"#0D2E4E"` |  |
| `items[].labelType` | 2 | `"headline-1"`, `"headline-3"` |  |
| `items[].name` | 2 | `"HeaderLabel"`, `"Label_"+_.N` |  |
| `items[].visible` | 2 | `true` |  |
| `items[].alignItems` | 1 | `"stretch"` |  |
| `items[].borderRadius` | 1 | `"none"` |  |
| `items[].clicked` | 1 |  |  |
| `items[].clicked.params` | 1 |  |  |
| `items[].clicked.params.nodeId` | 1 | `<binding>` |  |
| `items[].clicked.request` | 1 | `"usr.ToggleSelectionGroupRequest"` |  |
| `items[].defaultLocalizableStrings` | 1 |  |  |
| `items[].defaultLocalizableStrings.caption` | 1 |  |  |
| `items[].direction` | 1 | `"row"` |  |
| `items[].disabled` | 1 | `<binding>` |  |
| `items[].fitContent` | 1 | `true` |  |
| `items[].gap` | 1 | `"extra-small"` |  |
| `items[].iconPosition` | 1 | `"only-text"` |  |
| `items[].items` | 1 |  |  |
| `items[].items[].caption` | 1 | `<binding>` |  |
| `items[].items[].classes` | 1 |  |  |
| `items[].items[].clicked` | 1 |  |  |
| `items[].items[].clicked.params` | 1 |  |  |
| `items[].items[].clicked.request` | 1 | `"usr.ToggleSelectionGroupRequest"` |  |
| `items[].items[].color` | 1 | `"default"` |  |
| `items[].items[].disabled` | 1 | `<binding>` |  |
| `items[].items[].iconPosition` | 1 | `"only-text"` |  |
| `items[].items[].size` | 1 | `"medium"` |  |
| `items[].items[].type` | 1 | `"crt.Button"` |  |
| `items[].items[].visible` | 1 | `true` |  |
| `items[].justifyContent` | 1 | `"center"` |  |
| `items[].labelBackgroundColor` | 1 | `"transparent"` |  |
| `items[].labelEllipsis` | 1 | `false` |  |
| `items[].labelTextAlign` | 1 | `"start"` |  |
| `items[].labelThickness` | 1 | `"default"` |  |
| `items[].padding` | 1 |  |  |
| `items[].padding.bottom` | 1 | `"none"` |  |
| `items[].padding.left` | 1 | `"none"` |  |
| `items[].padding.right` | 1 | `"none"` |  |
| `items[].padding.top` | 1 | `"none"` |  |
| `items[].size` | 1 | `"medium"` |  |
| `items[].wrap` | 1 | `"nowrap"` |  |
| `layoutConfig.colSpan` | 378 | `1`, `2`, `8`, `4` |  |
| `layoutConfig.column` | 378 | `1`, `2`, `3`, `4` |  |
| `layoutConfig.row` | 378 | `1`, `2`, `3`, `5` |  |
| `layoutConfig.rowSpan` | 378 | `1`, `5`, `11`, `84`, `6` |  |
| `layoutConfig.width` | 1 | `420` |  |
| `padding.left` | 192 | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.right` | 192 | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.bottom` | 190 | `"none"`, `"small"`, `"medium"`, `"large"` |  |
| `padding.top` | 190 | `"none"`, `"medium"`, `"large"`, `"small"`, `null`, `"12px"` |  |
| `styles.border` | 3 | `"none"` |  |
| `styles.height` | 2 | `"600px"` |  |

## Приклад з реальної схеми

Джерело: `UsrInvoice_FormPage.js`

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

## Пов'язані

[[crt.GridContainer]], [[crt.ExpansionPanel]], [[crt.TemplateList]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 4223 згадок у конфігах. Мінімізовані імена класів не наводяться.*