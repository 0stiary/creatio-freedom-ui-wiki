---
type: crt.AccountCompactProfile
selector: crt-account-compact-profile
group: "Бізнес-компоненти"
usage_in_configs: 4
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.AccountCompactProfile

Angular-селектор: `<crt-account-compact-profile>`  
Група: **Бізнес-компоненти**  
Слоти вкладених елементів (`contentSlots`): `dialogItems`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **4** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `accountName` |  |  |  |  |
| `accountNameValidationInfo` |  |  |  |  |
| `alternativeName` |  |  |  |  |
| `city` |  |  |  |  |
| `country` |  |  |  |  |
| `timeZone` |  |  |  |  |
| `dialogTitle` |  |  |  | (успадковано від базового класу) |
| `photo` |  |  |  | (успадковано від базового класу) |
| `photoTitle` |  |  |  | (успадковано від базового класу) |
| `readonly` |  | `true`, `false` | 4 | (успадковано від базового класу) |
| `referenceColumn` |  | `<binding>` | 4 | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `imageClear` |  |  |
| `imageSelected` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 4 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:210,icon:r(69200),defaultPropertyValues:{readonly:false},defaultLocalizableStrings:{},requiredPackages:["CrtCustomer360App"]},designViewItemCommands:{create:"crt.AddAccountCompactProfileCommand"},propertiesPanelComponentTypeName:"crt.AccountCompactProfilePropertiesPanel",typeCaption:"AccountCompactProfile.Caption",viewElementGroupType:L.J.Components}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_0.js.завантаження`

```json
{layoutConfig:{},type:"crt.AccountCompactProfile",referenceColumn:"$Account",readonly:true}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (6316.hash=ba7a97bcc1acf044.js) + 12 згадок у конфігах. Мінімізовані імена класів не наводяться.*