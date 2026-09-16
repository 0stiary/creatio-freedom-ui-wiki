---
type: crt.DateTimePicker
selector: crt-datetimepicker
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.DateTimePicker

> Поле дати/часу.

Angular-селектор: `<crt-datetimepicker>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `autofocus` |  |  |  |
| `mode` | `"auto"` |  | `auto` |
| `multiYearSelector` | `true` |  |  |
| `pickerType` |  | `"date"`, `"datetime"` | `date` / `datetime` / `time` |
| `preventSameDateTimeSelection` | `false` |  |  |
| `readonly` | `false` | `false`, `true`, `<binding>` |  |
| `startView` | `"month"` |  |  |
| `timeInterval` | `1` |  | крок хвилин |
| `useSeconds` | `false` |  | показувати секунди |
| `useTwelveHourFormat` |  |  |  |
| `value` |  |  |  |
| `appearance` | `"legacy"` | `legacy` | (успадковано від базового класу) |
| `ariaLabel` | `""` |  | (успадковано від базового класу) |
| `control` |  | `<binding>` | (успадковано від базового класу) |
| `disabled` |  |  | (успадковано від базового класу) |
| `label` | `""` | `<binding>`, `"#ResourceString(DecisionDate_label)#"` | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"` | (успадковано від базового класу) |
| `placeholder` |  | `""` | (успадковано від базового класу) |
| `tooltip` |  | `""`, `"#ResourceString(DecisionDate_tooltip)#"` | (успадковано від базового класу) |

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
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `formControlConfig` |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `formControlConfig.relatesTo` | `"control"` |  |
| `layoutConfig.colSpan` | `1`, `2` |  |
| `layoutConfig.column` | `1`, `2` |  |
| `layoutConfig.row` | `1`, `5`, `2`, `3`, `6`, `7` |  |
| `layoutConfig.rowSpan` | `1` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:40,icon:e(3522),defaultPropertyValues:{label:"",placeholder:"",readonly:false,labelPosition:"auto",tooltip:""},defaultLocalizableStrings:{label:"Components.DateTimePicker.Caption"}},dataValueTypes:[P.r.Date,P.r.Time,P.r.DateTime],propertiesPanelComponentTypeName:"crt.InputPropertiesPanelComponent",viewElementGroupType:N.J.Inputs,typeCaption:"Components.DateTimePicker.Caption"}
```

## Приклад з реальної схеми


```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 5,
						"rowSpan": 1
					},
					"type": "crt.DateTimePicker",
					"label": "$Resources.Strings.PageParameters_UsrDateTimeParameter1_3u6zktc",
					"placeholder": "",
					"readonly": true,
					"labelPosition": "auto",
					"tooltip": "",
					"control": "$PageParameters_UsrDateTimeParameter1_3u6zktc",
					"pickerType": "date",
					"visible": true
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (8245.hash=cdf54a1857fc1318.js) + 733 згадок у конфігах. Мінімізовані імена класів не наводяться.*