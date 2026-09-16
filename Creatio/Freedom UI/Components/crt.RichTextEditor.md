---
type: crt.RichTextEditor
selector: crt-rich-text-editor
group: "Поля вводу"
usage_in_configs: 18
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.RichTextEditor

> HTML-редактор (CKEditor).

Angular-селектор: `<crt-rich-text-editor>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `selectionActions`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **18** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `visible` | 18 | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `label` | 18 | `<binding>` |  |
| `labelPosition` | 18 | `"hidden"`, `"auto"`, `"above"` |  |
| `control` | 18 | `<binding>` | атрибут |
| `filesStorage` | 18 |  |  |
| `readonly` | 18 | `false`, `true`, `null` |  |
| `placeholder` | 18 | `""`, `null`, `"#ResourceString(Notes_placeholder)#"` |  |
| `tooltip` | 18 | `""`, `null` |  |
| `toolbarDisplayMode` | 17 | `null` | режим тулбару |
| `needHandleSave` | 13 | `true` |  |
| `multiline` | 5 | `null`, `true`, `false` | багаторядковий |
| `layoutConfig` | 5 |  | спільна → [[Common view-element properties#layoutConfig]] |
| `alwaysShowToolbar` | 3 | `false` |  |
| `caption` | 2 | `<binding>` |  |
| `formControlConfig` | 1 |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `filesStorage.entitySchemaName` | 18 | `"SysFile"`, `"ActivityFile"`, `"UsrInvoiceFile"` |  |
| `filesStorage.masterRecordColumnValue` | 18 | `<binding>`, `null` |  |
| `filesStorage.recordColumnName` | 18 | `"RecordId"`, `"Activity"`, `"UsrInvoice"` |  |
| `filesStorage.recordEntitySchemaName` | 4 | `"Activity"`, `null` |  |
| `formControlConfig.relatesTo` | 1 | `"control"` |  |
| `layoutConfig.colSpan` | 5 | `1`, `2` |  |
| `layoutConfig.column` | 5 | `1` |  |
| `layoutConfig.row` | 5 | `1`, `3` |  |
| `layoutConfig.rowSpan` | 5 | `9`, `1`, `2` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{groupType:I.h.Inputs,position:41,icon:e(14560),defaultPropertyValues:{label:"",control:"",labelPosition:"auto",placeholder:"",tooltip:"",needHandleSave:true,filesStorage:{masterRecordColumnValue:"$Id",entitySchemaName:"SysFile",recordColumnName:"RecordId",recordEntitySchemaName:""}},defaultLocalizableStrings:{caption:"Components.RichTextEditor.Caption",label:"Components.RichTextEditor.Caption"}},dataValueTypes:[v.r.RICH_TEXT],propertiesPanelComponentTypeName:"crt.RichTextPropertiesPanel",viewElementGroupType:P.J.Inputs,typeCaption:"Components.RichTextEditor.Caption"}
```

## Приклад з реальної схеми

Джерело: `UsrInvoice_FormPage.js`

```json
{
					"layoutConfig": {
						"column": 1,
						"colSpan": 1,
						"row": 1,
						"rowSpan": 9
					},
					"type": "crt.RichTextEditor",
					"label": "#ResourceString(RichTextEditor_g6ltfwc_label)#",
					"control": "$PDS_UsrNotes_3zluz3f",
					"labelPosition": "hidden",
					"placeholder": "",
					"tooltip": "",
					"needHandleSave": true,
					"filesStorage": {
						"masterRecordColumnValue": "$Id",
						"entitySchemaName": "UsrInvoiceFile",
						"recordColumnName": "UsrInvoice"
					},
					"caption": "#ResourceString(RichTextEditor_g6ltfwc_caption)#",
					"visible": true,
					"readonly": false,
					"toolbarDisplayMode": null,
					"alwaysShowToolbar": false
				}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7463.hash=eedaefd9f4ee5aca.js) + 190 згадок у конфігах. Мінімізовані імена класів не наводяться.*