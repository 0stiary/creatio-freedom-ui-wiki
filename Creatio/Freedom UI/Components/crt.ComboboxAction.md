---
type: crt.ComboboxAction
selector: crt-combobox-action
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ComboboxAction

Angular-селектор: `<crt-combobox-action>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `details` |  |  |  |
| `iconPosition` |  |  |  |
| `title` |  |  |  |
| `caption` |  | `"ComboBox.OpenSection"` | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `handleItemClick` |  |  | (успадковано від базового класу) |
| `icon` |  | `"combobox-go-to-source"` | (успадковано від базового класу) |
| `iconColor` |  |  | (успадковано від базового класу) |
| `items` |  |  | (успадковано від базового класу) |
| `visible` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `clicked` | `"crt.OpenLookupSourceRequest"` |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `code` |  |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `clicked.params` | `{}` |  |
| `clicked.request` | `"crt.OpenLookupSourceRequest"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{viewElementGroupType:s.J.Components}
```

## Приклад з реальної схеми


```json
{code:D.U.GoToRecordList,type:"crt.ComboboxAction",icon:"combobox-go-to-source",caption:"ComboBox.OpenSection",clicked:{request:"crt.OpenLookupSourceRequest",params:{}}}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ComboboxAction** → [[crt.MenuItem]] → *BaseMenuItem* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ComboboxAction** (власні) | `details`, `iconPosition`, `title` | — |  |
| *BaseMenuItem* | `caption`, `disabled`, `handleItemClick`, `icon`, `iconColor`, `items`, `visible` | `clicked` | `caption, icon, iconColor, visible, disabled, items, handleItemClick`; подія `clicked` |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

Нащадки (компоненти, що наслідують цей): [[crt.ComboboxSearchTextAction]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 4 згадок у конфігах. Мінімізовані імена класів не наводяться.*