---
type: crt.Label
selector: crt-label
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Label

> Текстовий напис. **`classes` і `styles` ігнорує** — стилізуйте через `labelStyle`/`label*`-властивості або через клас батьківського контейнера.

Angular-селектор: `<crt-label>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `headingLevel` |  | `"label"`, `"h1"` | `h1`..`h6` / `label` (семантика) |
| `labelBackgroundColor` |  | `"transparent"` |  |
| `labelElementType` |  |  |  |
| `labelTextAlign` |  | `"start"`, `"center"`, `"end"` |  |
| `caption` |  | `<binding>`, `"#ResourceString(FeedsTab_caption)#"`, `"#ResourceString(CtiTab_caption)#"`, `"#ResourceString(EmailsTab_caption)#"`, `"#ResourceString(ChatsTab_caption)#"`, `"#ResourceString(ReminderTab_caption)#"`, `""` | текст / `#ResourceString(...)#` / `#MacrosTemplateString(...)#` / біндінг |
| `labelColor` |  | `"auto"`, `"#0D2E4E"`, `"#757575"`, `"var(--crt-palette-foreground-500)"`, `"#181818"`, `"#FFFFFF"`, `"var(--crt-palette-label-500)"` | `auto` або hex |
| `labelEllipsis` |  | `false` | (успадковано від базового класу) |
| `labelFontFamily` |  |  | (успадковано від базового класу) |
| `labelFontSize` |  |  | (успадковано від базового класу) |
| `labelHeight` |  |  | (успадковано від базового класу) |
| `labelLetterSpacing` |  | `"0.3px"` | (успадковано від базового класу) |
| `labelLineHeight` |  | `"1.8em"` | (успадковано від базового класу) |
| `labelMargin` |  | `"8px 24px 10px 40px"`, `"6px 16px 11px 16px"`, `"8px 16px"` | (успадковано від базового класу) |
| `labelStyle` | `{}` |  | об'єкт inline-стилів для самого тексту (`[ngStyle]`), напр. `{"color": "#c00", "font-style": "italic"}` — заміна `styles`, який Label не рендерить |
| `labelTextTransform` |  |  | (успадковано від базового класу) |
| `labelThickness` |  | `"default"`, `"normal"`, `"semibold"`, `"light"` | `default` / `bold`… |
| `labelType` |  | `button` · `"body"`, `"headline-3"`, `"headline-2"`, `"button-small"`, `"body-large"`, `"headline-1"`, `"caption"`, `"large-2"` | `headline-1..3` / `body` / `caption` / `caption-large` / `button`… |
| `required` |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `true`, `<binding>` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `selected` | `true` | службовий стан дизайнера (виділення елемента в Page Designer) |
| `defaultLocalizableStrings` |  | службове поле дизайнера — ключі локалізації, які підставляються при вставці елемента |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `defaultLocalizableStrings.caption` |  |  |
| `layoutConfig.colSpan` | `1`, `7`, `12`, `4` |  |
| `layoutConfig.column` | `1`, `3`, `2` |  |
| `layoutConfig.row` | `1`, `2`, `3`, `4` |  |
| `layoutConfig.rowSpan` | `1`, `2` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{toolbarConfig:{position:40,icon:t(3099),defaultPropertyValues:{caption:"",labelType:"headline-1",labelThickness:"default",labelEllipsis:false,labelColor:_.F.Auto,labelBackgroundColor:"transparent",labelTextAlign:"start",headingLevel:"label"},defaultLocalizableStrings:{caption:"Components.Label.Caption"}},designViewItemCommands:{update:"crt.LabelChangeViewItemCommand"},propertiesPanelComponentTypeName:"crt.LabelPropertiesPanel",viewElementGroupType:g.J.Components,typeCaption:"Components.Label.Caption",placeholderSize:{height:"20px"}}
```

## Приклад з реальної схеми


```json
{type:"crt.Label",caption:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_RecordsCount | usr.FilterNodeCountCaptionConverter",labelType:"caption-large",labelThickness:"default",labelEllipsis:false,labelColor:"auto",labelBackgroundColor:"transparent",labelTextAlign:"center",headingLevel:"label",visible:"$UsrCaseFilterNodes.UsrCaseFilterNodeDS_RecordsCount | crt.IsEqual : 0 | crt.InvertBooleanValue"}
```

## Пов'язані

[[crt.Timer]], [[crt.Link]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 1798 згадок у конфігах. Мінімізовані імена класів не наводяться.*