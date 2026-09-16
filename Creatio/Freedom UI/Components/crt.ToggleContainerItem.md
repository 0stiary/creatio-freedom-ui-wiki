---
type: crt.ToggleContainerItem
selector: crt-toggle-container-item
group: "Layout"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ToggleContainerItem

> Елемент `crt.ToggleContainer` (тіло однієї вкладки). Створюється препроцесором з `crt.TabContainer`.

Angular-селектор: `<crt-toggle-container-item>`  
Група: **Layout**  
Слоти вкладених елементів (`contentSlots`): `items`, `tools`  
reuseStrategy: `Reuse`  
`classes`: ✅ рендериться (на внутрішній елемент) · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `allowToggleClose` | `true` |  | чи показувати кнопку закриття / дозволяти закриття |
| `backgroundColor` |  |  | = `TabPanel.bodyBackgroundColor` |
| `isToggleTabHeaderVisible` |  |  | показувати `tools` як заголовок |
| `borderRadius` |  |  | (успадковано від базового класу) |
| `color` |  |  | (успадковано від базового класу) |
| `elementResponsiveWidth` | `0` |  | (успадковано від базового класу) |
| `fitContent` | `true` |  | (успадковано від базового класу) |
| `items` | `[]` |  | (успадковано від базового класу) |
| `padding` |  |  | (успадковано від базового класу) |
| `responsiveWidth` |  |  | (успадковано від базового класу) |
| `stretch` | `false` |  | (успадковано від базового класу) |
| `visiblePadding` | `true` |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `closeContainer` |  | емітиться при закритті → батько робить `selectedTabChange(null)` |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Приклад з реальної схеми


```json
{...St,type:"crt.ToggleContainerItem",backgroundColor:N.bodyBackgroundColor,isToggleTabHeaderVisible:St.isToggleTabHeaderVisible??false,allowToggleClose:rt}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ToggleContainerItem** → *BaseContainer* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ToggleContainerItem** (власні) | `allowToggleClose`, `backgroundColor`, `isToggleTabHeaderVisible` | `closeContainer` |  |
| *BaseContainer* | `borderRadius`, `color`, `elementResponsiveWidth`, `fitContent`, `items`, `padding`, `responsiveWidth`, `stretch`, `visiblePadding` | — | контейнер: `items, padding, visiblePadding, borderRadius, color, stretch, fitContent, responsiveWidth, elementResponsiveWidth`; класи padding/color/borderRadius, реакція на resize |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

## Пов'язані

[[crt.ToggleContainer]], [[crt.TabPanel]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 3 згадок у конфігах. Мінімізовані імена класів не наводяться.*