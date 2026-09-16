---
type: crt.Link
selector: crt-link
group: "Базові компоненти"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Link

> Посилання (використовується і як cellView у гріді).

Angular-селектор: `<crt-link>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `ariaLabel` |  |  |  |
| `caption` |  | `<binding>` |  |
| `href` |  | `<binding>`, `"https://oauth.net/2/"` | URL або біндінг з `crt.ToRecordLinkAsync` |
| `linkType` |  | `"body"`, `"caption"` |  |
| `mode` |  | `native` · `"preventDefault"`, `"native"` | `native` |
| `payload` |  |  |  |
| `target` |  | `"_blank"`, `"_self"` | `_blank` |
| `title` |  |  |  |
| `underlining` |  | `"hover"`, `"never"` | `hover`/`always`/`none` |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `clicked` | `"crt.OpenPageRequest"`, `"crt.OpenUserCardRequest"`, `"crt.UpdateRecordRequest"` |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | Значення | Що робить |
|---|---|---|
| `visible` | `true` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `column` |  |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `clicked.params` |  |  |
| `clicked.request` | `"crt.OpenPageRequest"`, `"crt.OpenUserCardRequest"`, `"crt.UpdateRecordRequest"` |  |
| `clicked.params.modelInitConfigs` |  |  |
| `clicked.params.schemaName` | `"UsrTransactions_ListPage"` |  |
| `clicked.params.entityName` |  |  |
| `clicked.params.modelInitConfigs[].OracleInvoiceNo` | `<binding>` |  |
| `clicked.params.recordId` |  |  |
| `clicked.params.systemUserId` | `<binding>` |  |
| `clicked.params.itemsAttributeName` |  |  |

## Приклад з реальної схеми


```json
{
									"caption": "$GridDetail_2ydt4vb.GridDetail_2ydt4vbDS_UsrOracleInvoiceNo",
									"type": "crt.Link",
									"href": "$GridDetail_2ydt4vb.GridDetail_2ydt4vbDS_Id | crt.ToRecordLinkAsync : 'GridDetail_2ydt4vbDS_Id'",
									"underlining": "hover",
									"mode": "preventDefault",
									"clicked": {
										"request": "crt.OpenPageRequest",
										"params": {
											"schemaName": "UsrTransactions_ListPage",
											"modelInitConfigs": [
												{
													"OracleInvoiceNo": "$GridDetail_2ydt4vb.GridDetail_2ydt4vbDS_UsrOracleInvoiceNo"
												}
											]
										}
									}
								}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 148 згадок у конфігах. Мінімізовані імена класів не наводяться.*