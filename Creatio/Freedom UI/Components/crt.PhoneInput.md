---
type: crt.PhoneInput
selector: crt-phone-input
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.PhoneInput

Angular-селектор: `<crt-phone-input>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `tools`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `alwaysShowFlags` | `false` |  |  |
| `countrySelectionConfig` |  |  |  |
| `displayAsPhone` | `true` | `false` |  |
| `isGridMode` |  |  |  |
| `isViewCellMode` |  |  |  |
| `phoneAsLink` | `false` | `true` |  |
| `displayTools` |  |  | (успадковано від базового класу) |
| `inputType` | `"text"` |  | (успадковано від базового класу) |
| `mask` |  |  | (успадковано від базового класу) |
| `multiline` | `false` |  | (успадковано від базового класу) |
| `autocomplete` | `"none"` |  | (успадковано від базового класу) |
| `autofocus` | `false` |  | (успадковано від базового класу) |
| `readonly` | `false` |  | (успадковано від базового класу) |
| `value` |  |  | (успадковано від базового класу) |
| `appearance` | `"legacy"` | `legacy`, `outline` | (успадковано від базового класу) |
| `ariaLabel` | `""` |  | (успадковано від базового класу) |
| `control` |  | `<binding>` | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `label` | `""` | `<binding>`, `"Mobile phone"`, `"Primary phone"` | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"` | (успадковано від базового класу) |
| `placeholder` |  | `""` | (успадковано від базового класу) |
| `tooltip` |  | `""` | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `blurred` |  |  |
| `focused` |  |  |
| `keyDown` |  |  |
| `keyUp` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `needHandleSave` | `false` |  |
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `formControlConfig` |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |
| `displayPhoneMask` | `false` |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `formControlConfig.relatesTo` | `"control"` |  |
| `layoutConfig.colSpan` | `1` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `2` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{groupType:K.h.Inputs,position:42,icon:e(12076),defaultPropertyValues:{label:"",control:"",labelPosition:"auto",placeholder:"",tooltip:"",needHandleSave:false},defaultLocalizableStrings:{caption:"DataValueType.PhoneTextCaption",label:"DataValueType.PhoneTextCaption"}},dataValueTypes:[p.r.PHONE_TEXT],propertiesPanelComponentTypeName:"crt.PhoneTextPropertiesPanel",viewElementGroupType:C.J.Inputs,typeCaption:"DataValueType.PhoneTextShortenedCaption"}
```

## Приклад з реальної схеми


```json
{
					"type": "crt.PhoneInput",
					"label": "$Resources.Strings.PDS_MobilePhone_vg6n0ok",
					"control": "$PDS_MobilePhone_vg6n0ok",
					"labelPosition": "auto",
					"placeholder": "",
					"tooltip": "",
					"needHandleSave": false,
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 2,
						"rowSpan": 1
					}
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (5034.hash=3867441b4932aa64.js) + 46 згадок у конфігах. Мінімізовані імена класів не наводяться.*