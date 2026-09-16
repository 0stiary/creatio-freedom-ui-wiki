---
type: crt.ButtonToggleGroupItem
selector: crt-button-toggle-group-item
group: "Базові компоненти"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ButtonToggleGroupItem

Angular-селектор: `<crt-button-toggle-group-item>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `ariaLabel` |  |  |  | (успадковано від базового класу) |
| `backgroundColor` |  |  |  | (успадковано від базового класу) |
| `badge` |  |  |  | (успадковано від базового класу) |
| `badgeConfig` |  |  | 1 | (успадковано від базового класу) |
| `color` | `"default"` |  |  | (успадковано від базового класу) |
| `contentAlign` |  |  | 2 | (успадковано від базового класу) |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `displayMenuIcon` | `false` | `true` | 1 | (успадковано від базового класу) |
| `displayValue` |  |  | 1 | (успадковано від базового класу) |
| `icon` |  |  | 1 | (успадковано від базового класу) |
| `iconPosition` |  |  | 1 | (успадковано від базового класу) |
| `iconSize` |  |  | 2 | (успадковано від базового класу) |
| `menuButtonsMode` | `false` | `true` | 2 | (успадковано від базового класу) |
| `menuItems` |  |  | 1 | (успадковано від базового класу) |
| `pressed` | `false` | `null` | 1 | (успадковано від базового класу) |
| `size` |  |  | 2 | (успадковано від базового класу) |
| `tooltipNotificationsPostfix` |  |  |  | (успадковано від базового класу) |
| `tooltipTitle` |  |  |  | (успадковано від базового класу) |
| `value` |  |  | 1 | (успадковано від базового класу) |
| `visible` | `true` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `toggleItemClicked` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `clickMode` | 1 | `"menu"` |  |

## Приклад з реальної схеми

Джерело: `4223.hash=3d5a69794a1b3d08.js`

```json
{type:"crt.ButtonToggleGroupItem",size:s,iconSize:c,contentAlign:d,menuButtonsMode:true,displayValue:m,value:l,icon:f,iconPosition:v,pressed:null,clickMode:"menu",displayMenuIcon:true,shape:"default",menuItems:r?.map(C=>({...C,type:"crt.MenuItem",caption:C.displayValue,selected:l===C.value,handleItemClick:()=>{i.handleToggleItemClickQueue([C])}}))}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 18 згадок у конфігах. Мінімізовані імена класів не наводяться.*