---
type: crt.ToggleContainer
selector: crt-toggle-container
group: "Layout"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ToggleContainer

> Внутрішній контейнер, у який препроцесор перетворює `crt.TabPanel`. Напряму у схемах майже не пишеться, але саме його inputs визначають поведінку вкладок.

Angular-селектор: `<crt-toggle-container>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `items` | `[]` |  |  |
| `preserveContent` | `true` |  | default `true` — неактивні елементи ховаються (`.hide`), а не знищуються; `false` — знищуються при перемиканні |
| `selectedTab` | `null` |  | `{value: name}`; якщо `null` — жодна не вибрана (toggle закрито) |
| `selectedTabIndex` | `0` |  | -1 = нічого не вибрано; при рендері автоматично 0 |
| `slidingAnimation` | `false` |  | анімація ковзання між вкладками (250 мс) |
| `borderRadius` |  |  | (успадковано від базового класу) |
| `color` |  |  | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` |  | (успадковано від базового класу) |
| `fitContent` | `true` |  | (успадковано від базового класу) |
| `padding` |  |  | (успадковано від базового класу) |
| `responsiveWidth` |  |  | (успадковано від базового класу) |
| `stretch` | `false` |  | (успадковано від базового класу) |
| `visiblePadding` | `true` |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `selectedTabChange` |  |  |
| `selectedTabIndexChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visibilityStrategyMode` |  | спільна → [[Common view-element properties#visibilityStrategyMode]] |

## Приклад з реальної схеми


```json
{type:"crt.ToggleContainer",preserveContent:N.preserveContent??true,slidingAnimation:N.slidingAnimation??false,items:N.items?.map(St=>({...St,type:"crt.ToggleContainerItem",backgroundColor:N.bodyBackgroundColor,isToggleTabHeaderVisible:St.isToggleTabHeaderVisible??false,allowToggleClose:rt})),visibilityStrategyMode:N.visibilityStrategyMode}
```

## Нотатки

Керування видимістю відбувається через `_changeItemVisibility` (клас `hide`) або `_destroyRenderedItem`. Закриття панелі (`ToggleContainerItem.closeContainer`) емітить `selectedTabChange(null)`.

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ToggleContainer** → *BaseContainer* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ToggleContainer** (власні) | `items`, `preserveContent`, `selectedTab`, `selectedTabIndex`, `slidingAnimation` | `selectedTabChange`, `selectedTabIndexChange` |  |
| *BaseContainer* | `borderRadius`, `color`, `elementResponsiveWidth`, `fitContent`, `padding`, `responsiveWidth`, `stretch`, `visiblePadding` | — | контейнер: `items, padding, visiblePadding, borderRadius, color, stretch, fitContent, responsiveWidth, elementResponsiveWidth`; класи padding/color/borderRadius, реакція на resize |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

## Пов'язані

[[crt.TabPanel]], [[crt.ToggleContainerItem]], [[crt.ButtonToggleGroup]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 4 згадок у конфігах. Мінімізовані імена класів не наводяться.*