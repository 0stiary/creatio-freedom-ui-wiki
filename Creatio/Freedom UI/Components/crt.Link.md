---
type: crt.Link
selector: crt-link
group: "Базові компоненти"
usage_in_configs: 30
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.Link

> Посилання (використовується і як cellView у гріді).

Angular-селектор: `<crt-link>`  
Група: **Базові компоненти**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **30** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `ariaLabel` |  |  |  |  |
| `caption` |  | `<binding>` | 30 |  |
| `href` |  | `<binding>`, `"https://oauth.net/2/"` | 27 | URL або біндінг з `crt.ToRecordLinkAsync` |
| `linkType` |  | `"body"`, `"caption"` | 13 |  |
| `mode` |  | `native` · `"preventDefault"`, `"native"` | 17 | `native` |
| `payload` |  |  |  |  |
| `target` |  | `"_blank"`, `"_self"` | 20 | `_blank` |
| `title` |  |  |  |  |
| `underlining` |  | `"hover"`, `"never"` | 17 | `hover`/`always`/`none` |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `clicked` | `"crt.OpenPageRequest"`, `"crt.OpenUserCardRequest"`, `"crt.UpdateRecordRequest"` |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `visible` | 13 | `true` | спільна → [[Common view-element properties#visible]] |
| `layoutConfig` | 1 | `{}` | спільна → [[Common view-element properties#layoutConfig]] |
| `column` | 1 |  |  |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `clicked.params` | 9 |  |  |
| `clicked.request` | 9 | `"crt.OpenPageRequest"`, `"crt.OpenUserCardRequest"`, `"crt.UpdateRecordRequest"` |  |
| `clicked.params.modelInitConfigs` | 5 |  |  |
| `clicked.params.schemaName` | 5 | `"UsrTransactions_ListPage"` |  |
| `clicked.params.entityName` | 2 |  |  |
| `clicked.params.modelInitConfigs[].OracleInvoiceNo` | 2 | `<binding>` |  |
| `clicked.params.recordId` | 2 |  |  |
| `clicked.params.systemUserId` | 2 | `<binding>` |  |
| `clicked.params.itemsAttributeName` | 1 |  |  |

## Приклад з реальної схеми

Джерело: `Accounts_FormPage.js`

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