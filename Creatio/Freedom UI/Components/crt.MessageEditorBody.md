---
type: crt.MessageEditorBody
selector: crt-message-editor-body
group: "Чати / Omnichannel / повідомлення"
usage_in_configs: 1
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.MessageEditorBody

Angular-селектор: `<crt-message-editor-body>`  
Група: **Чати / Omnichannel / повідомлення**  
Слоти вкладених елементів (`contentSlots`): `inputs`, `toolbarItems`  
Зустрічається в реальних конфігах: **1** раз(ів)  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем; *N* = скільки разів властивість зустрічається в реальних конфігах.

| Властивість | Default | Значення | N | Примітка |
|---|---|---|---|---|
| `chatInput` |  |  |  |  |
| `inputs` |  |  | 1 |  |
| `isFocused` |  |  |  |  |
| `toolbarItems` |  |  |  |  |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

У конфігурації сторінки подія задається об'єктом `{"request": "crt.XRequest", "params": {...}}` (виконується через HandlerChain) або зв'язується двосторонньо як атрибут (`selectedTabChange` ↔ `selectedTab`). Параметри можуть містити макрос `@event.detail` / `@event` (payload події) та `useRelativeContext: true` (контекст = view-модель елемента, а не сторінки).

| Подія | Спостережувані `request` у конфігах | Примітка |
|---|---|---|
| `sendMessage` |  |  |

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (N = частота; `[]` = елемент масиву).

| Шлях | N | Значення | Примітка |
|---|---|---|---|
| `inputs[].name` | 1 | `"MessageEditorInput_"+s.N` |  |
| `inputs[].type` | 1 | `"crt.MessageEditorInput"` |  |

## Приклад з реальної схеми

Джерело: `main.4ac964730f037ecc.js`

```json
{"type":"crt.MessageEditorBody","contentSlots":[{"name":"inputs","lazy":true,"input":true},{"name":"toolbarItems","lazy":true,"input":true}]}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (2656.hash=2360e964a8a68b73.js) + 2 згадок у конфігах. Мінімізовані імена класів не наводяться.*