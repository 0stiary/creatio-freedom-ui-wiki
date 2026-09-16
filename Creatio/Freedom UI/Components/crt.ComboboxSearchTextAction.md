---
type: crt.ComboboxSearchTextAction
selector: crt-combobox-search-text-action
group: "Поля вводу"
usage_in_configs: 364
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ComboboxSearchTextAction

> Дія у списку ComboBox (напр. «Створити <текст пошуку>»).

Angular-селектор: `<crt-combobox-search-text-action>`  
Група: **Поля вводу**  
reuseStrategy: `Reuse`  
Зустрічається в реальних конфігах: **364** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `details` | `{}` |  |  |  |
| `iconPosition` |  |  |  | (успадковано від базового класу) |
| `title` |  |  |  | (успадковано від базового класу) |
| `caption` |  | `<binding>`, `"ComboBox.AddNewRecord"` | 364 | (успадковано від базового класу) |
| `disabled` |  |  |  | (успадковано від базового класу) |
| `handleItemClick` |  |  |  | (успадковано від базового класу) |
| `icon` |  | `"combobox-add-new"` | 364 | `combobox-add-new` |
| `iconColor` |  |  |  | (успадковано від базового класу) |
| `items` |  |  |  | (успадковано від базового класу) |
| `visible` |  |  |  | (успадковано від базового класу) |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `clicked` | `"crt.CreateRecordFromLookupRequest"` | `{request: "crt.CreateRecordFromLookupRequest", params: {}}` |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

| Властивість | N | Значення | Що робить |
|---|---|---|---|
| `code` | 364 | `"addRecord"` | `addRecord` |

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `clicked.params` | 364 | `{}` |  |
| `clicked.request` | 364 | `"crt.CreateRecordFromLookupRequest"` |  |

## Приклад з реальної схеми

Джерело: `Accounts_FormPage.js`

```json
{
					"code": "addRecord",
					"type": "crt.ComboboxSearchTextAction",
					"icon": "combobox-add-new",
					"caption": "#ResourceString(addRecord_m7g6uv2_caption)#",
					"clicked": {
						"request": "crt.CreateRecordFromLookupRequest",
						"params": {}
					}
				}
```

## Пов'язані

[[crt.ComboBox]]

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 1456 згадок у конфігах. Мінімізовані імена класів не наводяться.*