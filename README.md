# Creatio Freedom UI Wiki

Obsidian-vault з довідником по клієнтській розробці в **Creatio 8.x (Freedom UI)**. Основна частина — згенерований з коду платформи довідник усіх view-елементів `crt.*`: inputs/outputs, приховані властивості, вкладені структури, успадкування, приклади з реальних схем. Друга частина — робочі нотатки по SDK (`@creatio-devkit/common`) з перевіреними сніпетами.

Мова нотаток — українська (SDK-нотатки частково англійською). Ідентифікатори, властивості й приклади коду — як у Creatio.

## Зміст репозиторію

```
Creatio/
├── Freedom UI/                          # довідник view-елементів (161 компонент)
│   ├── README.md                        # як користуватись довідником, легенда, обмеження
│   ├── Freedom UI Components — Index.md # точка входу: усі компоненти по групах
│   ├── Common view-element properties.md
│   ├── Inheritance tree.md
│   ├── Converters & Validators.md
│   └── Components/crt.*.md              # по сторінці на компонент
└── Js/Sdk (8 UI)/                       # нотатки по SDK з прикладами
    ├── Grid/Row toolbar actions.md
    ├── HandlerChainService/Global request listeners.md
    ├── HttpService/Service.md
    ├── crt.OpenSelectionWindowRequest/…
    └── sdk.Model/sdk.Model - Filters Guide.md
```

### Freedom UI — довідник компонентів

Починати з [Freedom UI Components — Index](Creatio/Freedom%20UI/Freedom%20UI%20Components%20%E2%80%94%20Index.md) або з [README довідника](Creatio/Freedom%20UI/README.md).

| Сторінка | Що там |
|---|---|
| [Common view-element properties](Creatio/Freedom%20UI/Common%20view-element%20properties.md) | Формат `viewConfigDiff`, базові inputs, `visible` / `visibilityStrategyMode`, `layoutConfig`, слоти, синтаксис біндінгів і конвертерів, події → запити, хто реально рендерить `classes` / `styles`, фічі-перемикачі |
| [Inheritance tree](Creatio/Freedom%20UI/Inheritance%20tree.md) | Дерево успадкування компонентів; іменовані абстрактні бази (`BaseViewElement`, `BaseContainer`, `BaseFormControl`, …) і що вони дають нащадкам |
| [Converters & Validators](Creatio/Freedom%20UI/Converters%20%26%20Validators.md) | Усі зареєстровані `crt.*` конвертери та валідатори з сигнатурами |
| `Components/crt.*.md` | Для кожного компонента: селектор, слоти, inputs (зі значеннями та дефолтами), outputs, приховані властивості, вкладені структури, метадані Page Designer, приклад з реальної схеми, нотатки, ланцюжок успадкування |

Приклади сторінок: [crt.DataGrid](Creatio/Freedom%20UI/Components/crt.DataGrid.md), [crt.TabPanel](Creatio/Freedom%20UI/Components/crt.TabPanel.md), [crt.QuickFilter](Creatio/Freedom%20UI/Components/crt.QuickFilter.md), [crt.ComboBox](Creatio/Freedom%20UI/Components/crt.ComboBox.md), [crt.TemplateList](Creatio/Freedom%20UI/Components/crt.TemplateList.md).

Чим довідник відрізняється від офіційної документації:

- покриває **всі** зареєстровані елементи, включно зі службовими (`crt.ToggleContainer`, `crt.TabPanelHeaderItem`, комірки гріда);
- показує **приховані властивості**, які читають препроцесори, а не компонент (`visibilityStrategyMode`, `preserveContent`, `_designOptions`, `_filterOptions`, `_selectionOptions`, `for`, …);
- для `classes` / `styles` вказує, чи компонент їх взагалі застосовує до DOM;
- показує, від якого базового класу успадковано кожен input.

### SDK-нотатки

Короткі перевірені рецепти: дії в тулбарі рядка гріда, глобальні слухачі запитів через `HandlerChainService`, виклик веб-сервісів через `HttpClientService`, фільтри у `crt.OpenSelectionWindowRequest`, побудова фільтрів для `sdk.Model`.

## Як користуватись

**В Obsidian (рекомендовано):** клонуйте репозиторій і відкрийте папку як vault (*Open folder as vault*). Працюють `[[wiki-лінки]]`, граф зв'язків, пошук по frontmatter (`type`, `selector`, `group`, `tags`).

**На GitHub:** сторінки читаються як звичайний Markdown; `[[wiki-лінки]]` всередині нотаток не клікабельні — переходьте через дерево файлів або посилання в цьому README.

Корисні запити для пошуку по vault:

- сторінка компонента — файл `Components/crt.<Назва>.md`;
- знайти, де рендериться `classes` — frontmatter/шапка сторінки або таблиця в *Common view-element properties*;
- знайти всі елементи з певним input (напр. `selectionState`) — повнотекстовий пошук по `Components/`.

## Джерела й версія

- Довідник компонентів згенеровано з мінімізованого коду Shell **Creatio 8.3.4.2753** (Angular 18) та з ~1 000 реальних конфігів сторінок (OOTB-бандли + кастомні пакети проєкту). Кожен факт у таблицях або є в коді компонента, або зустрівся в реальній схемі.
- Ручні описи додано лише для ключових компонентів; сторінки без нотаток містять тільки автоматично витягнуті дані.
- Обмеження: доступні були 63 зі 124 lazy-чанків Shell — компоненти з незавантажених чанків (`crt.IFrame`, `crt.NextStepTile`, `crt.ApprovalTile`, …) відсутні, для 28 компонентів не розв'язано базовий клас. Детально — у [README довідника](Creatio/Freedom%20UI/README.md#обмеження).
- Інша версія Creatio може мати інший набір inputs; версію, з якої зібрано дані, вказано у футері кожної сторінки.

## Регенерація

Довідник збирається скриптами (Python), які зберігаються окремо від vault разом із вихідними даними. Процес і вимоги до вхідних даних описано в [README довідника](Creatio/Freedom%20UI/README.md#як-перегенерувати). Ручні описи живуть у `wiki_notes.py` і переживають перегенерацію; правки безпосередньо в згенерованих `.md` — ні. SDK-нотатки пишуться вручну.

## Внесок

- Помилка у згенерованій сторінці → issue з назвою компонента і властивістю; правка вноситься в генератор/нотатки, а не в `.md`.
- Новий рецепт для SDK → окрема нотатка в `Creatio/Js/Sdk (8 UI)/<Тема>/`, у стилі наявних (передумови → приклад → пояснення).
- Не додавайте у vault реальні дані інстансів, облікові записи та локальні шляхи.
