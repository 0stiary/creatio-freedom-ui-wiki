---
type: crt.UserCompactProfile
selector: crt-user-compact-profile
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.UserCompactProfile

Angular-селектор: `<crt-user-compact-profile>`  
Група: **Бізнес-компоненти**  
Слоти вкладених елементів (`contentSlots`): `dialogItems`  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `firstName` |  |  |  |
| `firstNameValidationInfo` |  |  |  |
| `lastName` |  |  |  |
| `middleName` |  |  |  |
| `dialogTitle` |  |  | (успадковано від базового класу) |
| `photo` |  |  | (успадковано від базового класу) |
| `photoTitle` |  |  | (успадковано від базового класу) |
| `readonly` |  |  | (успадковано від базового класу) |
| `referenceColumn` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `imageClear` |  |  |
| `imageSelected` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:230,requiredFeatures:{ShowDesignerDemoItems:true},icon:r(40941),defaultPropertyValues:{readonly:false},defaultLocalizableStrings:{}},propertiesPanelComponentTypeName:"crt.UserCompactProfilePropertiesPanel",typeCaption:"UserCompactProfile.Caption",viewElementGroupType:L.J.Components,placeholderSize:{height:"80px"}}
```

## Приклад з реальної схеми


```json
{type:"crt.UserCompactProfile",contentSlots:["dialogItems"],reuseStrategy:U.B.Reuse}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.UserCompactProfile** → *BaseCompactProfile* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.UserCompactProfile** (власні) | `firstName`, `firstNameValidationInfo`, `lastName`, `middleName` | — |  |
| *BaseCompactProfile* | `dialogTitle`, `photo`, `photoTitle`, `readonly`, `referenceColumn` | `imageClear`, `imageSelected` | `photo, photoTitle, dialogTitle, referenceColumn, readonly`; події `imageSelected/imageClear` |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (6316.hash=ba7a97bcc1acf044.js) + 0 згадок у конфігах. Мінімізовані імена класів не наводяться.*