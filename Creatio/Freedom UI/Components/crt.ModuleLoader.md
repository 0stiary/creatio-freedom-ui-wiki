---
type: crt.ModuleLoader
selector: crt-7x-module
group: "Shell / службові"
tags: [creatio, freedom-ui, view-element]
generated: 2026-09-16
---
# crt.ModuleLoader

> Вбудовування legacy 7.x-модуля (`<crt-7x-module>`).

Angular-селектор: `<crt-7x-module>`  
Група: **Shell / службові**  
reuseStrategy: `Reuse`  
`classes`: ❌ приймається, але **не застосовується** до DOM · `styles`: ❌ приймається, але **не застосовується** до DOM — див. [[Common view-element properties#Хто реально рендерить classes і styles]]

Див. також [[Common view-element properties|спільні властивості всіх елементів]] (`name`, `visible`, `visibilityStrategyMode`, `layoutConfig`, `classes`, `styles`, `bindTo`, `_designOptions`).

## Вхідні параметри (inputs)

Джерело: декоратор `@Input()` Freedom UI у класі компонента та його базових класах. Колонка *Значення* = можливі значення, знайдені в коді компонента та в реальних конфігах схем.

| Властивість | Default | Значення | Примітка |
|---|---|---|---|
| `doNotRender` |  | `true` | не рендерити одразу |
| `instanceConfig` |  |  | конфіг, що передається у модуль |
| `module` |  | `"BaseSchemaModuleV2"`, `"CtiPanelLazyLoaderModule"`, `"OauthSettingsModule"`, `"CtiPanelModule"`, `"EmailModule"`, `"OmniChatModule"`, `"AngularAdapterModule"` | ім'я 7.x модуля/схеми |

Базові inputs (приймаються всіма елементами, але `classes`/`styles` рендеряться не всюди — див. рядок вище): `classes`, `id`, `loading`, `name`, `shape`, `styles`, `tabIndex` — [[Common view-element properties]].

## Вихідні події (outputs)

Подій (`@Output`) у компонента немає.

## Приховані / фреймворкові властивості

Властивості, які **не є inputs компонента**, але зустрічаються в реальних конфігах: їх читають препроцесори метаданих (`crtOnMetaDataInit` / `crtOnModelInit`), компілятор view (`crtIf`, `layoutConfig`) або дизайнер. Без них конфіг теж валідний, але поведінка буде «за замовчуванням».

У реальних конфігах додаткових властивостей не знайдено.

## Структура вкладених об'єктів

Шляхи всередині складних властивостей, як їх реально заповнюють (`[]` = елемент масиву).

| Шлях | Значення | Примітка |
|---|---|---|
| `instanceConfig.isSchemaConfigInitialized` | `true` |  |
| `instanceConfig.schemaName` | `"ReminderNotificationsSchema"`, `"ESNNotificationSchema"`, `"VisaNotificationsSchema"`, `"AnniversaryNotificationsSchema"`, `"SystemNotificationsSchema"`, `"ProcessDashboardSchema"` |  |
| `instanceConfig.useHistoryState` | `false` |  |

## Приклад з реальної схеми


```json
{type:"crt.ModuleLoader",module:"BaseSchemaModuleV2",instanceConfig:{useHistoryState:false,isSchemaConfigInitialized:true,schemaName:"AnniversaryNotificationsSchema"}}
```

---
*Згенеровано з коду Shell Creatio 8.3.4.2753 (4223.hash=3d5a69794a1b3d08.js) + 64 згадок у конфігах. Мінімізовані імена класів не наводяться.*