---
type: crt.ContactCompactProfile
selector: crt-contact-compact-profile
group: "Бізнес-компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ContactCompactProfile

Angular-селектор: `<crt-contact-compact-profile>`  
Група: **Бізнес-компоненти**  
Слоти вкладених елементів (`contentSlots`): `dialogItems`  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `birthDate` |  |  |  |
| `city` |  |  |  |
| `country` |  |  |  |
| `displayName` |  |  |  |
| `firstName` |  |  |  |
| `firstNameValidationInfo` |  |  |  |
| `lastName` |  |  |  |
| `middleName` |  |  |  |
| `timeZone` |  |  |  |
| `dialogTitle` |  |  | (успадковано від базового класу) |
| `photo` |  |  | (успадковано від базового класу) |
| `photoTitle` |  |  | (успадковано від базового класу) |
| `readonly` |  | `false`, `true` | (успадковано від базового класу) |
| `referenceColumn` |  | `<binding>` | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `firstNameChange` |  |  |
| `fullNameChange` |  |  |
| `lastNameChange` |  |  |
| `middleNameChange` |  |  |
| `imageClear` |  |  |
| `imageSelected` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:220,icon:r(40941),defaultPropertyValues:{readonly:false},defaultLocalizableStrings:{},requiredPackages:["CrtCustomer360App"]},designViewItemCommands:{create:"crt.AddContactCompactProfileCommand"},propertiesPanelComponentTypeName:"crt.ContactCompactProfilePropertiesPanel",typeCaption:"ContactCompactProfile.Caption",viewElementGroupType:L.J.Components}
```

## Приклад з реальної схеми


```json
{layoutConfig:{},type:"crt.ContactCompactProfile",referenceColumn:"$PrimaryContact",readonly:true}
```

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.ContactCompactProfile** → *BaseCompactProfile* → *BaseViewElement* → *BaseComponent*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.ContactCompactProfile** (власні) | `birthDate`, `city`, `country`, `displayName`, `firstName`, `firstNameValidationInfo`, `lastName`, `middleName`, `timeZone` | `firstNameChange`, `fullNameChange`, `lastNameChange`, `middleNameChange` |  |
| *BaseCompactProfile* | `dialogTitle`, `photo`, `photoTitle`, `readonly`, `referenceColumn` | `imageClear`, `imageSelected` | `photo, photoTitle, dialogTitle, referenceColumn, readonly`; події `imageSelected/imageClear` |
| *BaseViewElement* | `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` | — | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| *BaseComponent* | — | — | корінь: зберігає лише Angular `injector` |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (6316.hash=ba7a97bcc1acf044.js) + 12 згадок у конфігах. Мінімізовані імена класів не наводяться.*