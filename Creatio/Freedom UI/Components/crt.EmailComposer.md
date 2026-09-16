---
type: crt.EmailComposer
selector: crt-email-composer
group: "Чати / Omnichannel / повідомлення"
usage_in_configs: 2
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.EmailComposer

Angular-селектор: `<crt-email-composer>`  
Група: **Чати / Omnichannel / повідомлення**  
Слоти вкладених елементів (`contentSlots`): `channelsPanel`, `selectionActions`  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **2** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `bcc` |  |  |  |  |
| `bindingColumns` |  |  |  |  |
| `body` |  |  |  |  |
| `cc` |  |  |  |  |
| `composerEvent` |  |  |  |  |
| `defaultSenderRequest` |  | `"crt.DefaultSenderComposerRequest"` | 2 |  |
| `emailId` |  |  |  |  |
| `entitySchemaName` |  | `"Account"` | 2 |  |
| `expandOnLoad` |  |  |  |  |
| `from` | `""` |  |  |  |
| `headerExpanded` | `false` |  |  |  |
| `headerLabelsWidth` |  |  |  |  |
| `height` |  |  |  |  |
| `isReplyExpanded` | `false` |  |  |  |
| `recipientsMailboxes` |  |  |  |  |
| `recordId` |  | `<binding>` | 2 |  |
| `sendersMailboxes` |  |  |  |  |
| `skeletonLoading` |  |  |  |  |
| `subject` |  |  |  |  |
| `to` |  |  |  |  |
| `visibleBcc` | `false` |  |  |  |
| `visibleCc` | `false` |  |  |  |
| `disableSelectionOptions` |  |  |  | (успадковано від базового класу) |
| `selection` |  |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `bccChange` |  |  |
| `bodyChange` |  |  |
| `ccChange` |  |  |
| `emailComposerCleared` |  |  |
| `emailComposerSaved` |  |  |
| `fromChange` |  |  |
| `headerExpandedChange` |  |  |
| `refreshRecipients` |  |  |
| `subjectChange` |  |  |
| `toChange` |  |  |
| `visibleBccChange` |  |  |
| `visibleCcChange` |  |  |
| `composerEventChange` |  |  |
| `selectionChange` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `sortedByColumn` | 2 | `"CreatedOn"` |  |
| `data` | 2 |  |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `data.caption` | 2 | `"Email"` |  |
| `data.icon` | 2 | `"email-composer-icon"` |  |
| `data.schemaType` | 2 | `"Email"` |  |
| `data.sortedByColumn` | 2 | `"CreatedOn"` |  |
| `data.typeName` | 2 | `"crt.EmailComposer"` |  |
| `data.uId` | 2 | `"75aadc65-a834-42d0-b880-fac9bdee4c86"` |  |

## Метадані дизайнера (Page Designer)

Що Page Designer підставляє за замовчуванням при додаванні елемента (`defaultPropertyValues`), які властивості є колекціями (`collectionPropertyNames`) і яка панель властивостей використовується.

```js
{propertiesPanelComponentTypeName:"crt.EmailComposerPropertiesPanel",viewElementGroupType:g.J.CustomElements,typeCaption:"MessageComposer.Email.Caption"}
```

## Приклад з реальної схеми

Джерело: `_bundle_8x_schema_1.js.завантаження`

```json
{type:"crt.EmailComposer",classes:["view-element"],sortedByColumn:"CreatedOn",data:{uId:"75aadc65-a834-42d0-b880-fac9bdee4c86",schemaType:"Email",caption:"Email",sortedByColumn:"CreatedOn",typeName:"crt.EmailComposer",icon:"email-composer-icon"},recordId:"$Id",defaultSenderRequest:"crt.DefaultSenderComposerRequest",entitySchemaName:"Account"}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (3789.hash=c07acffd1a475b43.js) + 12 згадок у конфігах. Мінімізовані імена класів не наводяться.*