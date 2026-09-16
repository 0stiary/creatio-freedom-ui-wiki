---
type: crt.Input
selector: crt-input
group: "Поля вводу"
usage_in_configs: 265
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Input

> Текстове поле (однорядкове/багаторядкове).

Angular-селектор: `<crt-input>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `tools`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **265** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `displayTools` |  |  |  |  |
| `inputType` | `"text"` |  |  | `text` / `password` / … |
| `mask` |  |  |  | маска вводу (imask) |
| `multiline` | `false` | `false`, `true` | 246 | textarea |
| `autocomplete` | `"none"` |  |  | (успадковано від базового класу) |
| `autofocus` | `false` |  |  | (успадковано від базового класу) |
| `readonly` | `false` | `false`, `true` | 212 | тільки читання (не плутати з `disabled`) |
| `value` |  |  |  | (успадковано від базового класу) |
| `appearance` | `"legacy"` | `legacy`, `outline` |  | (успадковано від базового класу) |
| `ariaLabel` | `""` |  |  | (успадковано від базового класу) |
| `control` |  | `<binding>` | 265 | `"$PDS_Column"` |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `label` | `""` | `<binding>` | 265 | (успадковано від базового класу) |
| `labelPosition` |  | `"auto"`, `"above"`, `"hidden"`, `"left"` | 265 | `auto` / `above` / `left` |
| `placeholder` |  | `""`, `<binding>`, `"#ResourceString(JobTitle_placeholder)#"`, `"#ResourceString(Dear_placeholder)#"` | 235 | (успадковано від базового класу) |
| `tooltip` |  | `""`, `<binding>` | 222 | (успадковано від базового класу) |

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

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `layoutConfig` | 187 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `visible` | 103 | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `formControlConfig.relatesTo` | 1 | `"control"` |  |
| `layoutConfig.colSpan` | 183 | `1`, `2` |  |
| `layoutConfig.column` | 183 | `1`, `2`, `3`, `4` |  |
| `layoutConfig.row` | 183 | `1`, `2`, `5`, `3`, `6`, `4` |  |
| `layoutConfig.rowSpan` | 183 | `1`, `3`, `4`, `2` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:20,icon:t(26969),defaultPropertyValues:{label:"",control:"",placeholder:"",tooltip:"",readonly:false,multiline:false,labelPosition:"auto"},defaultLocalizableStrings:{label:"Components.Input.Caption"}},dataValueTypes:dt,propertiesPanelComponentTypeName:"crt.TextInputPropertiesPanelComponent",viewElementGroupType:p.J.Inputs,typeCaption:"Components.Input.Caption",placeholderSize:{height:"32px"}}
```

## Приклад з реальної схеми

Джерело: `UsrPendingLines_FormPage.js`

```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 14,
						"rowSpan": 1
					},
					"type": "crt.Input",
					"label": "$Resources.Strings.PageParameters_UsrTextParameter1_82nf2sa",
					"control": "$PageParameters_UsrTextParameter1_82nf2sa",
					"placeholder": "",
					"tooltip": "",
					"readonly": true,
					"multiline": false,
					"labelPosition": "auto",
					"visible": true
				}
```

## Нотатки

Препроцесор `_modifyInputType` автоматично міняє тип на `crt.EmailInput`/`crt.PhoneInput`/`crt.WebInput` за `dataValueType` колонки (EMAIL_TEXT/PHONE_TEXT/WEB_TEXT).

## Пов'язані

[[crt.NumberInput]], [[crt.EmailInput]], [[crt.PhoneInput]], [[crt.WebInput]], [[crt.EncryptedInput]], [[crt.PasswordInput]], [[crt.ImageInput]], [[crt.FileInput]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 2001 згадок у конфігах. Мінімізовані імена класів не наводяться.*