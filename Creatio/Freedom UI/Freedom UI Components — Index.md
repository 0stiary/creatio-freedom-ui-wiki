---
tags: [creatio, freedom-ui, moc]
generated: 2026-09-16
---
# Freedom UI — довідник view-елементів (crt.*)

Згенеровано автоматично з мінімізованого коду Shell **Creatio 8.3.4.2753** (папка `Z:\Creatio Freedom\Shell`, 63 lazy-чанки з 124 — компоненти з незавантажених чанків, напр. `crt.IFrame`, `crt.NextStepTile`, `crt.ApprovalTile`, `crt.InplaceProcessSchemaDesigner`, `crt.Angular7XDetail`, у довіднику відсутні) та з ~1 000 реальних конфігів схем (бандли збережених сторінок + пакети `WTW_*`/`CP_Main`).

Для кожного елемента: **inputs** (справжні `@Input` компонента, включно з успадкованими), **outputs**, **приховані властивості** (читаються препроцесорами, у документації не описані — напр. `visibilityStrategyMode`, `_designOptions`, `_filterOptions`), структура вкладених об'єктів, метадані дизайнера і приклад з реальної схеми.

- [[Common view-element properties]] — спільні властивості, синтаксис біндінгів, `visible`/`crtIf`, `layoutConfig`, слоти.
- [[Converters & Validators]] — усі зареєстровані `crt.*` конвертери та валідатори з сигнатурами.

## Layout

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.GridContainer]] | `crt-grid` | 798 | ✅ | CSS-grid контейнер; діти позиціонуються через `layoutConfig {column,row,colSpan,rowSpan}`. |
| [[crt.FlexContainer]] | `crt-flex` | 654 | ✅ | Flex-контейнер (базовий блок компонування). |
| [[crt.ExpansionPanel]] | `crt-expansion-panel` | 305 | ✅ | Розгортна панель (деталь). |
| [[crt.TabContainer]] | `crt-tab` | 169 | ❌ | Одна вкладка всередині `crt.TabPanel`. Має слоти `items` (вміст) і `tools` (елементи хедера/заголовка). |
| [[crt.TabPanel]] | `crt-tab-panel-container` | 28 | ❌ | Панель вкладок або toggle-панель. Препроцесор розбирає `crt.TabPanel` на `crt.TabPanelHeader` + `crt.ToggleContainer`; більшість «вхідних» властивостей з конфігу читає саме препроцесор, а не компонент. |
| [[crt.SidebarContainer]] | `crt-sidebar-container` | 4 | ❌ |  |
| [[crt.HeaderContainer]] | `crt-header` | 2 | ✅ |  |
| [[crt.TabPanelHeader]] | `crt-tab-panel-header` | 1 | ❌ |  |
| [[crt.TabPanelHeaderItem]] | `crt-tab-panel-header-item` | 1 | ❌ |  |
| [[crt.ToggleContainer]] | `crt-toggle-container` | 1 | ✅ | Внутрішній контейнер, у який препроцесор перетворює `crt.TabPanel`. Напряму у схемах майже не пишеться, але саме його inputs визначають поведінку вкладок. |
| [[crt.ToggleContainerItem]] | `crt-toggle-container-item` | 1 | ✅ | Елемент `crt.ToggleContainer` (тіло однієї вкладки). Створюється препроцесором з `crt.TabContainer`. |
| [[crt.Conversation]] | `crt-conversation` | 0 | ❌ |  |
| [[crt.ItemWrapper]] | `crt-item-wrapper` | 0 | ⚠️ |  |

## Базові компоненти

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.MenuItem]] | `crt-menu-item` | 899 | ❌ | Пункт меню (у `Button.menuItems`, `DataGrid.rowToolbarItems/bulkActions`, `ComboBox.listActions`…). |
| [[crt.Button]] | `crt-button` | 797 | ✅ | Кнопка; з `menuItems` + `clickMode: "menu"` стає меню. |
| [[crt.Label]] | `crt-label` | 215 | ❌ | Текстовий напис. **`classes` і `styles` ігнорує** — стилізуйте через `labelStyle`/`label*`-властивості або через клас батьківського контейнера. |
| [[crt.Link]] | `crt-link` | 30 | ❌ | Посилання (використовується і як cellView у гріді). |
| [[crt.ButtonToggleGroup]] | `crt-button-toggle-group` | 16 | ❌ | Група кнопок-перемикачів. З `for: "<TabPanelName>"` стає «зовнішнім хедером» toggle-панелі. |
| [[crt.Placeholder]] | `crt-placeholder` | 11 | ❌ | Заглушка «немає даних» (у `DataGrid.placeholder`). |
| [[crt.MenuLabel]] | `crt-menu-label` | 6 | ❌ |  |
| [[crt.ButtonToggleGroupItem]] | `crt-button-toggle-group-item` | 2 | ❌ |  |
| [[crt.Menu]] | `crt-menu` | 2 | ❌ |  |
| [[crt.SkipLinks]] | `crt-skip-links` | 2 | ❌ |  |
| [[crt.MenuDivider]] | `crt-menu-divider` | 1 | ❌ |  |
| [[crt.Badge]] | `crt-badge` | 0 | ❌ |  |
| [[crt.Chip]] | `crt-chip` | 0 | ❌ |  |
| [[crt.ChipList]] | `crt-chip-list` | 0 | ❌ |  |
| [[crt.DeprecatedLabel]] | `ts-label` | 0 | ✅ |  |
| [[crt.IconRadioButton]] | `crt-icon-radio-button` | 0 | ❌ |  |
| [[crt.LocalTime]] | `crt-local-time` | 0 | ❌ |  |
| [[crt.Timer]] | `crt-timer` | 0 | ❌ |  |

## Поля вводу

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.ComboBox]] | `crt-combobox` | 465 | ❌ | Поле-довідник (lookup) / список. |
| [[crt.ComboboxSearchTextAction]] | `crt-combobox-search-text-action` | 364 | ❌ | Дія у списку ComboBox (напр. «Створити <текст пошуку>»). |
| [[crt.Input]] | `crt-input` | 265 | ❌ | Текстове поле (однорядкове/багаторядкове). |
| [[crt.NumberInput]] | `crt-number-input` | 112 | ❌ | Числове поле. |
| [[crt.Checkbox]] | `crt-checkbox` | 97 | ❌ | Прапорець. |
| [[crt.DateTimePicker]] | `crt-datetimepicker` | 95 | ❌ | Поле дати/часу. |
| [[crt.RichTextEditor]] | `crt-rich-text-editor` | 18 | ❌ | HTML-редактор (CKEditor). |
| [[crt.ImageInput]] | `crt-image-input` | 16 | ❌ | Поле зображення (аватар). |
| [[crt.CommunicationOptions]] | `crt-communication-options` | 10 | ❌ | Засоби зв'язку контакта/контрагента (телефони, email, соцмережі). |
| [[crt.PhoneInput]] | `crt-phone-input` | 6 | ❌ |  |
| [[crt.WebInput]] | `crt-web-input` | 5 | ✅ |  |
| [[crt.MultiSelect]] | `crt-multi-select` | 3 | ❌ | Мультивибір записів зв'язку M:N. |
| [[crt.TagSelect]] | `crt-tag-select` | 2 | ⚠️ | Теги запису. |
| [[crt.ColorPicker]] | `crt-color-picker` | 1 | ❌ |  |
| [[crt.ComboboxAction]] | `crt-combobox-action` | 1 | ❌ |  |
| [[crt.DeprecatedInput]] | `ts-input` | 1 | ⚠️ |  |
| [[crt.EmailInput]] | `crt-email-input` | 1 | ✅ |  |
| [[crt.EncryptedInput]] | `crt-encrypted-input` | 1 | ✅ |  |
| [[crt.FileInput]] | `crt-file-input` | 1 | ⚠️ | Поле завантаження файлу в атрибут. |
| [[crt.PasswordInput]] | `crt-password-input` | 1 | ⚠️ |  |
| [[crt.Slider]] | `crt-slider` | 1 | ❌ |  |
| [[crt.FileDrop]] | `crt-file-drop` | 0 | ❌ |  |
| [[crt.RichTextLinkComponent]] | `crt-rich-text-link` | 0 | ❌ |  |
| [[crt.RichTextVideoComponent]] | `crt-rich-text-video` | 0 | ❌ |  |

## Списки і дані

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.DataGrid]] | `crt-data-grid` | 251 | ✅ | Реєстр (таблиця) над колекцією view-моделей. Найбільше прихованих властивостей: `_selectionOptions`, `_designOptions`, `placeholder`, `rowToolbarItems`, `bulkActions`, `features.*`. |
| [[crt.SummaryItem]] | `crt-summary-item` | 42 | ❌ | Один підсумок. |
| [[crt.Summaries]] | `crt-summaries` | 25 | ❌ | Панель підсумків над гридом. |
| [[crt.TemplateList]] | `crt-template-list` | 2 | ✅ | Список, що рендерить `template` для кожного елемента колекції view-моделей. Подій не має; перемальовується на `items.changed`. |
| [[crt.ArticlesList]] | `crt-articles-list` | 0 | ⚠️ |  |
| [[crt.ComponentList]] | `ts-component-list` | 0 | ✅ |  |
| [[crt.FilterableList]] | `ts-filterable-list` | 0 | ✅ |  |
| [[crt.Gallery]] | `crt-gallery` | 0 | ❌ |  |
| [[crt.List]] | `ts-list` | 0 | ✅ |  |
| [[crt.MultiList]] | `crt-multi-list` | 0 | ⚠️ |  |
| [[crt.ObjectExplorer]] | `crt-object-explorer` | 0 | ⚠️ |  |

## Комірки гріда

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.TableBooleanCell]] | `crt-data-table-boolean-cell` | 4 | ❌ |  |
| [[crt.TableTextCell]] | `crt-data-table-text-cell` | 4 | ❌ | Текстова комірка гріда — використовується як `cellView` для кастомного форматування. |
| [[crt.DataTableEditLookupCell]] | `crt-data-table-edit-lookup-cell` | 2 | ❌ |  |
| [[crt.EditTypedValueCell]] | `crt-edit-typed-value-cell` | 2 | ❌ |  |
| [[crt.TypedValueCell]] | `crt-typed-value-cell` | 2 | ❌ |  |
| [[crt.DataTableEditDateTimeCell]] | `crt-data-table-edit-date-time-cell` | 1 | ❌ |  |
| [[crt.DataTableEditEmailCell]] | `crt-data-table-edit-email-cell` | 1 | ❌ |  |
| [[crt.DataTableEditNumericCell]] | `crt-data-table-edit-numeric-cell` | 1 | ❌ |  |
| [[crt.DataTableEditPhoneCell]] | `crt-data-table-edit-phone-cell` | 1 | ❌ |  |
| [[crt.DataTableEditTextCell]] | `crt-data-table-edit-text-cell` | 1 | ❌ |  |
| [[crt.DataTableEditWebCell]] | `crt-data-table-edit-web-cell` | 1 | ❌ |  |
| [[crt.TableDcmStageEditingCell]] | `crt-data-table-dcm-editing-stage-cell` | 1 | ❌ |  |
| [[crt.TableColoredCell]] | `crt-data-table-colored-cell` | 0 | ❌ | Кольорова комірка (lookup зі кольором, посилання). |
| [[crt.TableDateTimeCell]] | `crt-data-table-date-time-cell` | 0 | ❌ |  |
| [[crt.TableDcmStageCell]] | `crt-data-table-dcm-stage-cell` | 0 | ❌ |  |
| [[crt.TableEmailCell]] | `crt-data-table-email-cell` | 0 | ❌ |  |
| [[crt.TableFileCell]] | `crt-data-table-file-cell` | 0 | ❌ |  |
| [[crt.TableFileSizeCell]] | `crt-data-table-file-size-cell` | 0 | ❌ |  |
| [[crt.TableNumericCell]] | `crt-data-table-numeric-cell` | 0 | ❌ |  |
| [[crt.TablePhoneCell]] | `crt-data-table-phone-cell` | 0 | ❌ |  |
| [[crt.TableRichTextEditorCell]] | `crt-data-table-rich-text-editor-cell` | 0 | ❌ |  |
| [[crt.TableSliderCell]] | `crt-data-table-slider-cell` | 0 | ❌ |  |

## Фільтри

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.SearchFilter]] | `crt-search-filter` | 313 | ❌ | Рядок пошуку по колонках гріда. |
| [[crt.QuickFilter]] | `crt-quick-filter` | 238 | ❌ | Швидкий фільтр (lookup / date-range / custom) над гридом. Уся «магія» — у прихованому `_filterOptions`. |
| [[crt.FolderTree]] | `crt-folder-tree` | 5 | ✅ | Дерево груп (папок) розділу. |
| [[crt.FolderTreeActions]] | `crt-folder-tree-actions` | 5 | ❌ |  |
| [[crt.EntityHierarchyFilter]] | `crt-entity-hierarchy-filter` | 2 | ❌ | Ієрархічний фільтр (дерево вузлів об'єкта). |
| [[crt.DesignerFiltersContainer]] | `crt-designer-filters-container` | 1 | ❌ |  |
| [[crt.LookupQuickFilterMenuItem]] | `crt-lookup-quick-filter-menu-item` | 1 | ❌ |  |
| [[crt.FiltersContainer]] | `crt-filters-container` | 0 | ❌ |  |

## Дашборди та віджети

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.IndicatorWidget]] | `crt-indicator-widget` | 118 | ❌ | Віджет-показник (аналітика). |
| [[crt.ChartWidget]] | `crt-chart-widget` | 48 | ❌ | Віджет-графік. |
| [[crt.ListWidget]] | `crt-list-widget` | 3 | ❌ |  |
| [[crt.Dashboards]] | `crt-dashboards` | 2 | ❌ | Вбудовані дашборди розділу. |
| [[crt.FullPipelineWidget]] | `crt-full-pipeline-widget` | 0 | ❌ |  |
| [[crt.FunnelWidget]] | `crt-funnel-widget` | 0 | ❌ |  |
| [[crt.GaugeWidget]] | `crt-gauge-widget` | 0 | ❌ |  |

## Бізнес-компоненти

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.AccountCompactProfile]] | `crt-account-compact-profile` | 4 | ❌ |  |
| [[crt.ContactCompactProfile]] | `crt-contact-compact-profile` | 4 | ❌ |  |
| [[crt.NextBestOffer]] | `crt-next-best-offer` | 4 | ❌ |  |
| [[crt.EntityStageProgressBar]] | `crt-entity-stage-progress-bar` | 3 | ❌ | Індикатор стадій (DCM). |
| [[crt.NextSteps]] | `crt-next-steps` | 2 | ❌ | Панель «Наступні кроки». |
| [[crt.ActionDashboard]] | `crt-action-dashboard-7x-dt` | 1 | ❌ |  |
| [[crt.AllowedResults]] | `crt-allowed-results` | 1 | ⚠️ |  |
| [[crt.Approval]] | `crt-approval` | 1 | ❌ |  |
| [[crt.ApprovalList]] | `crt-approval-list` | 1 | ❌ |  |
| [[crt.Calendar]] | `crt-calendar` | 1 | ❌ |  |
| [[crt.CampaignViewer]] | `crt-campaign-viewer-7x-dt` | 1 | ❌ |  |
| [[crt.AgentInbox]] | `crt-agent-inbox` | 0 | ❌ |  |
| [[crt.NextBestOfferItem]] | `crt-next-best-offer-item` | 0 | ❌ |  |
| [[crt.Playbook]] | `crt-playbook` | 0 | ⚠️ |  |
| [[crt.UserCompactProfile]] | `crt-user-compact-profile` | 0 | ❌ |  |

## Timeline / Feed / Файли

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.TimelineTile]] | `crt-timeline-tile` | 80 | ❌ | Плитка типу запису у Timeline (описова, не має слотів у конфігу — читає препроцесор). |
| [[crt.FileList]] | `crt-file-list` | 11 | ✅ | Список файлів (успадковує DataGrid). |
| [[crt.Timeline]] | `crt-timeline` | 6 | ❌ | Таймлайн запису (активності, email, дзвінки, фід). |
| [[crt.Feed]] | `crt-feed` | 4 | ❌ | Стрічка (коментарі) запису. |
| [[crt.FeedComposer]] | `crt-feed-composer` | 2 | ❌ |  |
| [[crt.BaseTimelineLabel]] | `ts-base-timeline-label` | 0 | ❌ |  |
| [[crt.FeedItem]] | `crt-feed-item` | 0 | ❌ |  |
| [[crt.FileGalleryItem]] | `crt-file-list-gallery-item` | 0 | ❌ |  |
| [[crt.FilePreview]] | `crt-file-preview` | 0 | ❌ |  |
| [[crt.TimelineEmailLabel]] | `crt-timeline-email-label` | 0 | ❌ |  |
| [[crt.TimelineLabel]] | `crt-timeline-label` | 0 | ❌ |  |
| [[crt.TimelineLookup]] | `crt-timeline-lookup` | 0 | ❌ |  |
| [[crt.TimelinePhoneLabel]] | `crt-timeline-phone-label` | 0 | ❌ |  |
| [[crt.TimelineWebLabel]] | `crt-timeline-web-label` | 0 | ❌ |  |

## Чати / Omnichannel / повідомлення

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.EmailComposer]] | `crt-email-composer` | 2 | ❌ |  |
| [[crt.MessageComposerSelector]] | `crt-message-composer-selector` | 2 | ❌ |  |
| [[crt.MessageEditor]] | `crt-message-editor` | 1 | ❌ |  |
| [[crt.MessageEditorBody]] | `crt-message-editor-body` | 1 | ❌ |  |
| [[crt.MessageEditorInput]] | `crt-message-editor-input` | 1 | ❌ |  |
| [[crt.AutoTranslateToggle]] | `crt-auto-translate-toggle` | 0 | ✅ |  |
| [[crt.BaseMessageComposer]] | `crt-base-message-composer` | 0 | ❌ |  |
| [[crt.BaseMessageComposerSkeleton]] | `crt-base-message-composer-skeleton` | 0 | ❌ |  |
| [[crt.CallConversation]] | `crt-call-conversation` | 0 | ❌ |  |
| [[crt.ChannelSelector]] | `crt-channel-selector` | 0 | ❌ |  |
| [[crt.Chat]] | `crt-chat` | 0 | ❌ |  |
| [[crt.ChatDisclaimer]] | `crt-chat-disclaimer` | 0 | ❌ |  |
| [[crt.ChatItem]] | `crt-chat-item` | 0 | ✅ |  |
| [[crt.ChatList]] | `crt-chat-list` | 0 | ❌ |  |
| [[crt.ChatTyping]] | `crt-chat-typing` | 0 | ❌ |  |
| [[crt.IncomingItem]] | `crt-incoming-item` | 0 | ❌ |  |
| [[crt.IncomingItems]] | `crt-incoming-item-list` | 0 | ❌ |  |
| [[crt.MessageEditorReply]] | `crt-message-editor-reply` | 0 | ❌ |  |
| [[crt.OperatorState]] | `crt-operator-state` | 0 | ⚠️ |  |
| [[crt.TranslateToggle]] | `crt-translate-toggle` | 0 | ✅ |  |

## Shell / службові

| Елемент | Селектор | Вживань | `classes` | Опис |
|---|---|---|---|---|
| [[crt.ModuleLoader]] | `crt-7x-module` | 36 | ❌ | Вбудовування legacy 7.x-модуля (`<crt-7x-module>`). |
| [[crt.AppBackground]] | `crt-app-background` | 2 | ⚠️ |  |
| [[crt.AppToolbar]] | `crt-app-toolbar` | 2 | ⚠️ |  |
| [[crt.NavigationPanel]] | `crt-navigation-panel` | 2 | ✅ |  |
| [[crt.RouterOutlet]] | `crt-router-outlet` | 2 | ❌ |  |
| [[crt.DesignTimeActionDashboard]] | `crt-action-dashboard-7x-dt` | 1 | ❌ |  |
| [[crt.DesignTimeCampaignViewer]] | `crt-campaign-viewer-7x-dt` | 1 | ❌ |  |
| [[crt.NavigationPanelItem]] | `crt-navigation-panel-item` | 0 | ⚠️ |  |
| [[crt.SchemaOutlet]] | `crt-schema-outlet` | 0 | ❌ |  |
