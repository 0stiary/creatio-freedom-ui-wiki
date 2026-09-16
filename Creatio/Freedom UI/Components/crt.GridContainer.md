---
type: crt.GridContainer
selector: crt-grid
group: "Layout"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.GridContainer

> CSS-grid контейнер; діти позиціонуються через `layoutConfig {column,row,colSpan,rowSpan}`.

Angular-селектор: `<crt-grid>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на host-елемент) · `styles`: ✅ рендериться — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `alignItems` |  | `"stretch"` |  |
| `allowOverlap` |  |  | дозволити перекриття |
| `columns` |  | `string` · `"minmax(64px, 1fr)"` | масив треків, напр. `["minmax(32px, 1fr)", "minmax(32px, 1fr)"]` |
| `gap` |  | `8`, `"small"` | `{columnGap, rowGap}` |
| `justifyItems` |  |  |  |
| `rows` |  | `string` · `"minmax(max-content, 32px)"`, `"minmax(max-content, 24px)"`, `"minmax( 32px, 32px)"`, `"minmax(32px, max-content)"`, `"60px"`, `"64px"`, `"minmax(max-content, 0)"`, `"1fr"` | `"minmax(32px, max-content)"` (легасі `minmax(32px,32px)` автозамінюється) |
| `borderRadius` |  | `"none"`, `"medium"` | (успадковано від базового класу) |
| `color` |  | `"transparent"`, `"primary"` | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` | `600`, `616` | (успадковано від базового класу) |
| `fitContent` | `true` | `true`, `false` | (успадковано від базового класу) |
| `items` | `[]` | `[]` | (успадковано від базового класу) |
| `padding` |  |  | (успадковано від базового класу) |
| `responsiveWidth` |  |  | (успадковано від базового класу) |
| `stretch` | `false` | `true`, `false` | (успадковано від базового класу) |
| `visiblePadding` | `true` |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `true`, `false`, `<binding>` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `caption` |  |  |
| `iconPosition` |  |  |
| `sealed` | `true` |  |
| `selected` | `false` | службовий стан дизайнера (виділення елемента в Page Designer) |
| `dragging` | `false` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `gap.columnGap` | `"large"`, `"none"`, `"small"`, `"medium"`, `"extra-small"` |  |
| `gap.rowGap` | `0`, `"none"`, `null`, `"small"`, `"extra-small"` |  |
| `items[].type` | `"crt.FlexContainer"`, `"crt.GridContainer"` |  |
| `items[].alignItems` | `"center"` |  |
| `items[].direction` | `"row"` |  |
| `items[].gap` | `"small"`, `"none"` |  |
| `items[].items` |  |  |
| `items[].layoutConfig` |  |  |
| `items[].layoutConfig.colSpan` | `1` |  |
| `items[].layoutConfig.column` | `1` |  |
| `items[].layoutConfig.row` | `1` |  |
| `items[].layoutConfig.rowSpan` | `1` |  |
| `items[].name` | `"FlexContainer_"+c.N`, `"GridContainer_"+_.N` |  |
| `items[].borderRadius` | `"none"` |  |
| `items[].classes` | `<binding>` |  |
| `items[].color` | `"transparent"` |  |
| `items[].fitContent` | `true` |  |
| `items[].items[].alignItems` | `"stretch"` |  |
| `items[].items[].borderRadius` | `"none"` |  |
| `items[].items[].classes` |  |  |
| `items[].items[].color` | `"transparent"` |  |
| `items[].items[].direction` | `"row"` |  |
| `items[].items[].fitContent` | `true` |  |
| `items[].items[].gap` | `"extra-small"` |  |
| `items[].items[].items` |  |  |
| `items[].items[].items[].caption` | `<binding>` |  |
| `items[].items[].items[].classes` |  |  |
| `items[].items[].items[].clicked` |  |  |
| `items[].items[].items[].color` | `"default"` |  |
| `items[].items[].items[].disabled` | `<binding>` |  |
| `items[].items[].items[].iconPosition` | `"only-text"` |  |
| `items[].items[].items[].size` | `"medium"` |  |
| `items[].items[].items[].type` | `"crt.Button"` |  |
| `items[].items[].items[].visible` | `true` |  |
| `items[].items[].justifyContent` | `"center"` |  |
| `items[].items[].padding` |  |  |
| `items[].items[].padding.bottom` | `"none"` |  |
| `items[].items[].padding.left` | `"none"` |  |
| `items[].items[].padding.right` | `"none"` |  |
| `items[].items[].padding.top` | `"none"` |  |
| `items[].items[].type` | `"crt.FlexContainer"` |  |
| `items[].items[].visible` | `true` |  |
| `items[].items[].wrap` | `"nowrap"` |  |
| `items[].justifyContent` | `"space-between"` |  |
| `items[].padding` |  |  |
| `items[].padding.bottom` | `"none"` |  |
| `items[].padding.left` | `"none"` |  |
| `items[].padding.right` | `"none"` |  |
| `items[].padding.top` | `"none"` |  |
| `items[].visible` | `true` |  |
| `items[].wrap` | `"wrap"` |  |
| `layoutConfig.colSpan` | `1`, `8`, `2` |  |
| `layoutConfig.column` | `1`, `2` |  |
| `layoutConfig.row` | `1`, `2`, `6` |  |
| `layoutConfig.rowSpan` | `1`, `10` |  |
| `layoutConfig.basis` | `"fit-content"` |  |
| `padding.left` | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.right` | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.bottom` | `"none"`, `"medium"`, `"small"`, `"large"` |  |
| `padding.top` | `"none"`, `"medium"`, `"small"`, `"large"` |  |
| `styles.display` | `"inline"` |  |

## Приклад з реальної схеми


```json
{
					"layoutConfig": {
						"column": 1,
						"row": 1,
						"colSpan": 1,
						"rowSpan": 1
					},
					"type": "crt.GridContainer",
					"columns": [
						"minmax(32px, 1fr)",
						"minmax(32px, 1fr)",
						"minmax(32px, 1fr)",
						"minmax(32px, 1fr)"
					],
					"rows": "minmax(max-content, 32px)",
					"gap": {
						"columnGap": "large",
						"rowGap": "none"
					},
					"items": [],
					"fitContent": true,
					"visible": true,
					"color": "transparent",
					"borderRadius": "none",
					"padding": {
						"top": "none",
						"right": "none",
						"bottom": "none",
						"left": "none"
					},
					"alignItems": "stretch"
				}
```

## Пов'язані

[[crt.FlexContainer]], [[crt.ExpansionPanel]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 5511 згадок у конфігах. Мінімізовані імена класів не наводяться.*