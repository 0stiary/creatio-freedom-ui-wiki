---
type: crt.NavigationPanel
selector: crt-navigation-panel
group: "Shell / службові"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.NavigationPanel

Angular-селектор: `<crt-navigation-panel>`  
Група: **Shell / службові**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `collapsedGroupTooltipPrefix` | `""` |  |  |  |
| `currentGroupCode` |  |  |  |  |
| `dataSource` |  |  |  |  |
| `emptyGroupsPlaceholderConfig` |  |  |  |  |
| `emptyItemsPlaceholderConfig` |  |  |  |  |
| `openItemAsLink` |  |  |  |  |
| `panelDisplayMode` |  |  |  |  |
| `selectedGroupAriaLabel` | `""` |  |  |  |
| `setupItemConfig` |  |  |  |  |
| `usePanelIconBackground` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `groupChanged` |  |  |
| `itemClicked` |  |  |
| `loadData` |  |  |
| `panelDisplayModeChanged` |  |  |
| `placeholderItemEvent` |  |  |
| `setupClicked` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `stretch` | 2 | `true` |  |
| `visibilityStrategyMode` | 2 | `"hide"` | спільна → [[Common view-element properties#visibilityStrategyMode]] |

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_0.js.завантаження`

```json
{type:"crt.NavigationPanel",classes:["remove-outside-horizontal-padding"],stretch:true,visibilityStrategyMode:"hide"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 6 згадок у конфігах. Мінімізовані імена класів не наводяться.*