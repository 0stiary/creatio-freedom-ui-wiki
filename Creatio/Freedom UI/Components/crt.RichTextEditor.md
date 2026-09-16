---
type: crt.RichTextEditor
selector: crt-rich-text-editor
group: "Поля вводу"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.RichTextEditor

> HTML-редактор (CKEditor).

Angular-селектор: `<crt-rich-text-editor>`  
Група: **Поля вводу**  
Слоти вкладених елементів (`contentSlots`): `selectionActions`  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `true`, `false` | спільна → [[Common view-element properties#visible]] |
| `label` | `<binding>` |  |
| `labelPosition` | `"hidden"`, `"auto"`, `"above"` |  |
| `control` | `<binding>` | атрибут |
| `filesStorage` |  |  |
| `readonly` | `false`, `true`, `null` |  |
| `placeholder` | `""`, `null`, `"#ResourceString(Notes_placeholder)#"` |  |
| `tooltip` | `""`, `null` |  |
| `toolbarDisplayMode` | `null` | режим тулбару |
| `needHandleSave` | `true` |  |
| `multiline` | `null`, `true`, `false` | багаторядковий |
| `layoutConfig` |  | спільна → [[Common view-element properties#layoutConfig]] |
| `alwaysShowToolbar` | `false` |  |
| `caption` | `<binding>` |  |
| `formControlConfig` |  | конфіг Angular FormControl, який генерує препроцесор для полів (валідатори/required) |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `filesStorage.entitySchemaName` | `"SysFile"`, `"ActivityFile"`, `"UsrInvoiceFile"` |  |
| `filesStorage.masterRecordColumnValue` | `<binding>`, `null` |  |
| `filesStorage.recordColumnName` | `"RecordId"`, `"Activity"`, `"UsrInvoice"` |  |
| `filesStorage.recordEntitySchemaName` | `"Activity"`, `null` |  |
| `formControlConfig.relatesTo` | `"control"` |  |
| `layoutConfig.colSpan` | `1`, `2` |  |
| `layoutConfig.column` | `1` |  |
| `layoutConfig.row` | `1`, `3` |  |
| `layoutConfig.rowSpan` | `9`, `1`, `2` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{groupType:I.h.Inputs,position:41,icon:e(14560),defaultPropertyValues:{label:"",control:"",labelPosition:"auto",placeholder:"",tooltip:"",needHandleSave:true,filesStorage:{masterRecordColumnValue:"$Id",entitySchemaName:"SysFile",recordColumnName:"RecordId",recordEntitySchemaName:""}},defaultLocalizableStrings:{caption:"Components.RichTextEditor.Caption",label:"Components.RichTextEditor.Caption"}},dataValueTypes:[v.r.RICH_TEXT],propertiesPanelComponentTypeName:"crt.RichTextPropertiesPanel",viewElementGroupType:P.J.Inputs,typeCaption:"Components.RichTextEditor.Caption"}
```

## Приклад з реальної схеми


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

## Успадкування

Ланцюжок класів від компонента до кореня (Angular `extends`). Inputs/outputs успадковуються по всьому ланцюжку; імена абстрактних баз — описові, дані за їхніми властивостями (у коді вони мінімізовані), деталі — [[Inheritance tree]].

**crt.RichTextEditor** → *(базовий клас не розв'язано — його модуль відсутній у збережених чанках Shell; за архітектурою це BaseViewElement)*

| Рівень | Оголошує inputs | Оголошує outputs | Роль |
|---|---|---|---|
| **crt.RichTextEditor** (власні) | — | — |  |

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (7463.hash=eedaefd9f4ee5aca.js) + 190 згадок у конфігах. Мінімізовані імена класів не наводяться.*