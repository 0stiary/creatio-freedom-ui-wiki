---
type: crt.NavigationPanel
selector: crt-navigation-panel
group: "Shell / службові"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.NavigationPanel

Angular-селектор: `<crt-navigation-panel>`  
Група: **Shell / службові**  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `collapsedGroupTooltipPrefix` | `""` |  |  |
| `currentGroupCode` |  |  |  |
| `dataSource` |  |  |  |
| `emptyGroupsPlaceholderConfig` |  |  |  |
| `emptyItemsPlaceholderConfig` |  |  |  |
| `openItemAsLink` |  |  |  |
| `panelDisplayMode` |  |  |  |
| `selectedGroupAriaLabel` | `""` |  |  |
| `setupItemConfig` |  |  |  |
| `usePanelIconBackground` |  |  |  |

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

| Властивість | Значення | Що робить |
|---|---|---|
| `stretch` | `true` |  |
| `visibilityStrategyMode` | `"hide"` | спільна → [[Common view-element properties#visibilityStrategyMode]] |

## Приклад з реальної схеми


```json
{type:"crt.NavigationPanel",classes:["remove-outside-horizontal-padding"],stretch:true,visibilityStrategyMode:"hide"}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.NavigationPanel** → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.NavigationPanel** (власні) | `collapsedGroupTooltipPrefix`, `currentGroupCode`, `dataSource`, `emptyGroupsPlaceholderConfig`, `emptyItemsPlaceholderConfig`, `openItemAsLink`, `panelDisplayMode`, `selectedGroupAriaLabel`, `setupItemConfig`, `usePanelIconBackground` | `groupChanged`, `itemClicked`, `loadData`, `panelDisplayModeChanged`, `placeholderItemEvent`, `setupClicked` |  |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 6 згадок у конфігах. Мінімізовані імена класів не наводяться.*