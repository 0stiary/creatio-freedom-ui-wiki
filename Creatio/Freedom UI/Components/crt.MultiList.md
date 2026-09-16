---
type: crt.MultiList
selector: crt-multi-list
group: "Списки і дані"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.MultiList

Angular-селектор: `<crt-multi-list>`  
Група: **Списки і дані**  
Слоти вкладених елементів (`contentSlots`): `items`  
`classes`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) · `styles`: ⚠️ ймовірно (спільний модуль, перевірте в DOM) — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `currentPage` |  |  |  |
| `isCombinedMode` |  |  |  |
| `isSearchDisabled` |  |  |  |
| `itemsList` | `[]` |  |  |
| `searchFilter` |  |  |  |
| `selectedItemId` |  |  |  |
| `showNoDataBlankState` | `true` |  |  |

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `currentPageChange` |  |  |
| `itemClicked` |  |  |
| `itemFocused` |  |  |
| `loadData` |  |  |
| `searchFilterChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.MultiList** → *(базовий клас не розв'язано — його модуль відсутній у збережених чанках Shell; за архітектурою це BaseViewElement)*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.MultiList** (власні) | `currentPage`, `isCombinedMode`, `isSearchDisabled`, `itemsList`, `searchFilter`, `selectedItemId`, `showNoDataBlankState` | `currentPageChange`, `itemClicked`, `itemFocused`, `loadData`, `searchFilterChange` |  |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*