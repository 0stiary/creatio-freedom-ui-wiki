---
type: crt.GridContainer
selector: crt-grid
group: "Layout"
usage_in_configs: 798
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.GridContainer

> CSS-grid контейнер; діти позиціонуються через `layoutConfig {column,row,colSpan,rowSpan}`.

Angular-селектор: `<crt-grid>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **798** раз(ів)  
`classes`: ✅ рендериться (на host-елемент) · `styles`: ✅ рендериться — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `alignItems` |  | `"stretch"` | 226 |  |
| `allowOverlap` |  |  |  | дозволити перекриття |
| `columns` |  | `string` · `"minmax(64px, 1fr)"` | 795 | масив треків, напр. `["minmax(32px, 1fr)", "minmax(32px, 1fr)"]` |
| `gap` |  | `8`, `"small"` | 798 | `{columnGap, rowGap}` |
| `justifyItems` |  |  |  |  |
| `rows` |  | `string` · `"minmax(max-content, 32px)"`, `"minmax(max-content, 24px)"`, `"minmax( 32px, 32px)"`, `"minmax(32px, max-content)"`, `"60px"`, `"64px"`, `"minmax(max-content, 0)"`, `"1fr"` | 795 | `"minmax(32px, max-content)"` (легасі `minmax(32px,32px)` автозамінюється) |
| `borderRadius` |  | `"none"`, `"medium"` | 313 | (успадковано від базового класу) |
| `color` |  | `"transparent"`, `"primary"` | 315 | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` | `600`, `616` | 4 | (успадковано від базового класу) |
| `fitContent` | `true` | `true`, `false` | 158 | (успадковано від базового класу) |
| `items` | `[]` | `[]` | 798 | (успадковано від базового класу) |
| `padding` |  |  | 316 | (успадковано від базового класу) |
| `responsiveWidth` |  |  |  | (успадковано від базового класу) |
| `stretch` | `false` | `true`, `false` | 9 | (успадковано від базового класу) |
| `visiblePadding` | `true` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `visible` | 309 | `true`, `false`, `<binding>` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` | 67 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `caption` | 3 |  |  |
| `iconPosition` | 3 |  |  |
| `sealed` | 2 | `true` |  |
| `selected` | 2 | `false` | службовий стан дизайнера (виділення елемента в Page Designer) |
| `dragging` | 2 | `false` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `gap.columnGap` | 789 | `"large"`, `"none"`, `"small"`, `"medium"`, `"extra-small"` |  |
| `gap.rowGap` | 785 | `0`, `"none"`, `null`, `"small"`, `"extra-small"` |  |
| `items[].type` | 3 | `"crt.FlexContainer"`, `"crt.GridContainer"` |  |
| `items[].alignItems` | 2 | `"center"` |  |
| `items[].direction` | 2 | `"row"` |  |
| `items[].gap` | 2 | `"small"`, `"none"` |  |
| `items[].items` | 2 |  |  |
| `items[].layoutConfig` | 2 |  |  |
| `items[].layoutConfig.colSpan` | 2 | `1` |  |
| `items[].layoutConfig.column` | 2 | `1` |  |
| `items[].layoutConfig.row` | 2 | `1` |  |
| `items[].layoutConfig.rowSpan` | 2 | `1` |  |
| `items[].name` | 2 | `"FlexContainer_"+c.N`, `"GridContainer_"+_.N` |  |
| `items[].borderRadius` | 1 | `"none"` |  |
| `items[].classes` | 1 | `<binding>` |  |
| `items[].color` | 1 | `"transparent"` |  |
| `items[].fitContent` | 1 | `true` |  |
| `items[].items[].alignItems` | 1 | `"stretch"` |  |
| `items[].items[].borderRadius` | 1 | `"none"` |  |
| `items[].items[].classes` | 1 |  |  |
| `items[].items[].color` | 1 | `"transparent"` |  |
| `items[].items[].direction` | 1 | `"row"` |  |
| `items[].items[].fitContent` | 1 | `true` |  |
| `items[].items[].gap` | 1 | `"extra-small"` |  |
| `items[].items[].items` | 1 |  |  |
| `items[].items[].items[].caption` | 1 | `<binding>` |  |
| `items[].items[].items[].classes` | 1 |  |  |
| `items[].items[].items[].clicked` | 1 |  |  |
| `items[].items[].items[].color` | 1 | `"default"` |  |
| `items[].items[].items[].disabled` | 1 | `<binding>` |  |
| `items[].items[].items[].iconPosition` | 1 | `"only-text"` |  |
| `items[].items[].items[].size` | 1 | `"medium"` |  |
| `items[].items[].items[].type` | 1 | `"crt.Button"` |  |
| `items[].items[].items[].visible` | 1 | `true` |  |
| `items[].items[].justifyContent` | 1 | `"center"` |  |
| `items[].items[].padding` | 1 |  |  |
| `items[].items[].padding.bottom` | 1 | `"none"` |  |
| `items[].items[].padding.left` | 1 | `"none"` |  |
| `items[].items[].padding.right` | 1 | `"none"` |  |
| `items[].items[].padding.top` | 1 | `"none"` |  |
| `items[].items[].type` | 1 | `"crt.FlexContainer"` |  |
| `items[].items[].visible` | 1 | `true` |  |
| `items[].items[].wrap` | 1 | `"nowrap"` |  |
| `items[].justifyContent` | 1 | `"space-between"` |  |
| `items[].padding` | 1 |  |  |
| `items[].padding.bottom` | 1 | `"none"` |  |
| `items[].padding.left` | 1 | `"none"` |  |
| `items[].padding.right` | 1 | `"none"` |  |
| `items[].padding.top` | 1 | `"none"` |  |
| `items[].visible` | 1 | `true` |  |
| `items[].wrap` | 1 | `"wrap"` |  |
| `layoutConfig.colSpan` | 54 | `1`, `8`, `2` |  |
| `layoutConfig.column` | 54 | `1`, `2` |  |
| `layoutConfig.row` | 54 | `1`, `2`, `6` |  |
| `layoutConfig.rowSpan` | 54 | `1`, `10` |  |
| `layoutConfig.basis` | 6 | `"fit-content"` |  |
| `padding.left` | 315 | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.right` | 315 | `"none"`, `"medium"`, `"large"`, `"small"` |  |
| `padding.bottom` | 314 | `"none"`, `"medium"`, `"small"`, `"large"` |  |
| `padding.top` | 313 | `"none"`, `"medium"`, `"small"`, `"large"` |  |
| `styles.display` | 2 | `"inline"` |  |

## Приклад з реальної схеми

Джерело: `UsrPage_t4y0i8y.js`

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