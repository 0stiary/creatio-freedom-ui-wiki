---
type: crt.ButtonToggleGroupItem
selector: crt-button-toggle-group-item
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ButtonToggleGroupItem

Angular-селектор: `<crt-button-toggle-group-item>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `ariaLabel` |  |  | (успадковано від базового класу) |
| `backgroundColor` |  |  | (успадковано від базового класу) |
| `badge` |  |  | (успадковано від базового класу) |
| `badgeConfig` |  |  | (успадковано від базового класу) |
| `color` | `"default"` |  | (успадковано від базового класу) |
| `contentAlign` |  |  | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `displayMenuIcon` | `false` | `true` | (успадковано від базового класу) |
| `displayValue` |  |  | (успадковано від базового класу) |
| `icon` |  |  | (успадковано від базового класу) |
| `iconPosition` |  |  | (успадковано від базового класу) |
| `iconSize` |  |  | (успадковано від базового класу) |
| `menuButtonsMode` | `false` | `true` | (успадковано від базового класу) |
| `menuItems` |  |  | (успадковано від базового класу) |
| `pressed` | `false` | `null` | (успадковано від базового класу) |
| `size` |  |  | (успадковано від базового класу) |
| `tooltipNotificationsPostfix` |  |  | (успадковано від базового класу) |
| `tooltipTitle` |  |  | (успадковано від базового класу) |
| `value` |  |  | (успадковано від базового класу) |
| `visible` | `true` |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `toggleItemClicked` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `clickMode` | `"menu"` |  |

## Приклад з реальної схеми


```json
{type:"crt.ButtonToggleGroupItem",size:s,iconSize:c,contentAlign:d,menuButtonsMode:true,displayValue:m,value:l,icon:f,iconPosition:v,pressed:null,clickMode:"menu",displayMenuIcon:true,shape:"default",menuItems:r?.map(C=>({...C,type:"crt.MenuItem",caption:C.displayValue,selected:l===C.value,handleItemClick:()=>{i.handleToggleItemClickQueue([C])}}))}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ButtonToggleGroupItem** → *BaseToggleGroupItem* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ButtonToggleGroupItem** (власні) | — | — |  |
| *BaseToggleGroupItem* | `ariaLabel`, `backgroundColor`, `badge`, `badgeConfig`, `color`, `contentAlign`, `disabled`, `displayMenuIcon`, `displayValue`, `icon`, `iconPosition`, `iconSize`, `menuButtonsMode`, `menuItems`, `pressed`, `size`, `tooltipNotificationsPostfix`, `tooltipTitle`, `value`, `visible` | `toggleItemClicked` | `value, displayValue, icon, iconPosition, size, menuItems, pressed, backgroundColor, color, badge, tooltipTitle`; подія `toggleItemClicked` |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 18 згадок у конфігах. Мінімізовані імена класів не наводяться.*