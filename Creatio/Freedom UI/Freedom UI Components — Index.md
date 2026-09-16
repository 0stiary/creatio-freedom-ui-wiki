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

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.GridContainer]] | `crt-grid` | ✅ | CSS-grid контейнер; діти позиціонуються через `layoutConfig {column,row,colSpan,rowSpan}`. |
| [[crt.FlexContainer]] | `crt-flex` | ✅ | Flex-контейнер (базовий блок компонування). |
| [[crt.ExpansionPanel]] | `crt-expansion-panel` | ✅ | Розгортна панель (деталь). |
| [[crt.TabContainer]] | `crt-tab` | ❌ | Одна вкладка всередині `crt.TabPanel`. Має слоти `items` (вміст) і `tools` (елементи хедера/заголовка). |
| [[crt.TabPanel]] | `crt-tab-panel-container` | ❌ | Панель вкладок або toggle-панель. Препроцесор розбирає `crt.TabPanel` на `crt.TabPanelHeader` + `crt.ToggleContainer`; більшість «вхідних» властивостей з конфігу читає саме препроцесор, а не компонент. |
| [[crt.SidebarContainer]] | `crt-sidebar-container` | ❌ |  |
| [[crt.HeaderContainer]] | `crt-header` | ✅ |  |
| [[crt.TabPanelHeader]] | `crt-tab-panel-header` | ❌ |  |
| [[crt.TabPanelHeaderItem]] | `crt-tab-panel-header-item` | ❌ |  |
| [[crt.ToggleContainer]] | `crt-toggle-container` | ✅ | Внутрішній контейнер, у який препроцесор перетворює `crt.TabPanel`. Напряму у схемах майже не пишеться, але саме його inputs визначають поведінку вкладок. |
| [[crt.ToggleContainerItem]] | `crt-toggle-container-item` | ✅ | Елемент `crt.ToggleContainer` (тіло однієї вкладки). Створюється препроцесором з `crt.TabContainer`. |
| [[crt.Conversation]] | `crt-conversation` | ❌ |  |
| [[crt.ItemWrapper]] | `crt-item-wrapper` | ⚠️ |  |

## Базові компоненти

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.MenuItem]] | `crt-menu-item` | ❌ | Пункт меню (у `Button.menuItems`, `DataGrid.rowToolbarItems/bulkActions`, `ComboBox.listActions`…). |
| [[crt.Button]] | `crt-button` | ✅ | Кнопка; з `menuItems` + `clickMode: "menu"` стає меню. |
| [[crt.Label]] | `crt-label` | ❌ | Текстовий напис. **`classes` і `styles` ігнорує** — стилізуйте через `labelStyle`/`label*`-властивості або через клас батьківського контейнера. |
| [[crt.Link]] | `crt-link` | ❌ | Посилання (використовується і як cellView у гріді). |
| [[crt.ButtonToggleGroup]] | `crt-button-toggle-group` | ❌ | Група кнопок-перемикачів. З `for: "<TabPanelName>"` стає «зовнішнім хедером» toggle-панелі. |
| [[crt.Placeholder]] | `crt-placeholder` | ❌ | Заглушка «немає даних» (у `DataGrid.placeholder`). |
| [[crt.MenuLabel]] | `crt-menu-label` | ❌ |  |
| [[crt.ButtonToggleGroupItem]] | `crt-button-toggle-group-item` | ❌ |  |
| [[crt.Menu]] | `crt-menu` | ❌ |  |
| [[crt.SkipLinks]] | `crt-skip-links` | ❌ |  |
| [[crt.MenuDivider]] | `crt-menu-divider` | ❌ |  |
| [[crt.Badge]] | `crt-badge` | ❌ |  |
| [[crt.Chip]] | `crt-chip` | ❌ |  |
| [[crt.ChipList]] | `crt-chip-list` | ❌ |  |
| [[crt.DeprecatedLabel]] | `ts-label` | ✅ |  |
| [[crt.IconRadioButton]] | `crt-icon-radio-button` | ❌ |  |
| [[crt.LocalTime]] | `crt-local-time` | ❌ |  |
| [[crt.Timer]] | `crt-timer` | ❌ |  |

## Поля вводу

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.ComboBox]] | `crt-combobox` | ❌ | Поле-довідник (lookup) / список. |
| [[crt.ComboboxSearchTextAction]] | `crt-combobox-search-text-action` | ❌ | Дія у списку ComboBox (напр. «Створити <текст пошуку>»). |
| [[crt.Input]] | `crt-input` | ❌ | Текстове поле (однорядкове/багаторядкове). |
| [[crt.NumberInput]] | `crt-number-input` | ❌ | Числове поле. |
| [[crt.Checkbox]] | `crt-checkbox` | ❌ | Прапорець. |
| [[crt.DateTimePicker]] | `crt-datetimepicker` | ❌ | Поле дати/часу. |
| [[crt.RichTextEditor]] | `crt-rich-text-editor` | ❌ | HTML-редактор (CKEditor). |
| [[crt.ImageInput]] | `crt-image-input` | ❌ | Поле зображення (аватар). |
| [[crt.CommunicationOptions]] | `crt-communication-options` | ❌ | Засоби зв'язку контакта/контрагента (телефони, email, соцмережі). |
| [[crt.PhoneInput]] | `crt-phone-input` | ❌ |  |
| [[crt.WebInput]] | `crt-web-input` | ✅ |  |
| [[crt.MultiSelect]] | `crt-multi-select` | ❌ | Мультивибір записів зв'язку M:N. |
| [[crt.TagSelect]] | `crt-tag-select` | ⚠️ | Теги запису. |
| [[crt.ColorPicker]] | `crt-color-picker` | ❌ |  |
| [[crt.ComboboxAction]] | `crt-combobox-action` | ❌ |  |
| [[crt.DeprecatedInput]] | `ts-input` | ⚠️ |  |
| [[crt.EmailInput]] | `crt-email-input` | ✅ |  |
| [[crt.EncryptedInput]] | `crt-encrypted-input` | ✅ |  |
| [[crt.FileInput]] | `crt-file-input` | ⚠️ | Поле завантаження файлу в атрибут. |
| [[crt.PasswordInput]] | `crt-password-input` | ⚠️ |  |
| [[crt.Slider]] | `crt-slider` | ❌ |  |
| [[crt.FileDrop]] | `crt-file-drop` | ❌ |  |
| [[crt.RichTextLinkComponent]] | `crt-rich-text-link` | ❌ |  |
| [[crt.RichTextVideoComponent]] | `crt-rich-text-video` | ❌ |  |

## Списки і дані

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.DataGrid]] | `crt-data-grid` | ✅ | Реєстр (таблиця) над колекцією view-моделей. Найбільше прихованих властивостей: `_selectionOptions`, `_designOptions`, `placeholder`, `rowToolbarItems`, `bulkActions`, `features.*`. |
| [[crt.SummaryItem]] | `crt-summary-item` | ❌ | Один підсумок. |
| [[crt.Summaries]] | `crt-summaries` | ❌ | Панель підсумків над гридом. |
| [[crt.TemplateList]] | `crt-template-list` | ✅ | Список, що рендерить `template` для кожного елемента колекції view-моделей. Подій не має; перемальовується на `items.changed`. |
| [[crt.ArticlesList]] | `crt-articles-list` | ⚠️ |  |
| [[crt.ComponentList]] | `ts-component-list` | ✅ |  |
| [[crt.FilterableList]] | `ts-filterable-list` | ✅ |  |
| [[crt.Gallery]] | `crt-gallery` | ❌ |  |
| [[crt.List]] | `ts-list` | ✅ |  |
| [[crt.MultiList]] | `crt-multi-list` | ⚠️ |  |
| [[crt.ObjectExplorer]] | `crt-object-explorer` | ⚠️ |  |

## Комірки гріда

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.TableBooleanCell]] | `crt-data-table-boolean-cell` | ❌ |  |
| [[crt.TableTextCell]] | `crt-data-table-text-cell` | ❌ | Текстова комірка гріда — використовується як `cellView` для кастомного форматування. |
| [[crt.DataTableEditLookupCell]] | `crt-data-table-edit-lookup-cell` | ❌ |  |
| [[crt.EditTypedValueCell]] | `crt-edit-typed-value-cell` | ❌ |  |
| [[crt.TypedValueCell]] | `crt-typed-value-cell` | ❌ |  |
| [[crt.DataTableEditDateTimeCell]] | `crt-data-table-edit-date-time-cell` | ❌ |  |
| [[crt.DataTableEditEmailCell]] | `crt-data-table-edit-email-cell` | ❌ |  |
| [[crt.DataTableEditNumericCell]] | `crt-data-table-edit-numeric-cell` | ❌ |  |
| [[crt.DataTableEditPhoneCell]] | `crt-data-table-edit-phone-cell` | ❌ |  |
| [[crt.DataTableEditTextCell]] | `crt-data-table-edit-text-cell` | ❌ |  |
| [[crt.DataTableEditWebCell]] | `crt-data-table-edit-web-cell` | ❌ |  |
| [[crt.TableDcmStageEditingCell]] | `crt-data-table-dcm-editing-stage-cell` | ❌ |  |
| [[crt.TableColoredCell]] | `crt-data-table-colored-cell` | ❌ | Кольорова комірка (lookup зі кольором, посилання). |
| [[crt.TableDateTimeCell]] | `crt-data-table-date-time-cell` | ❌ |  |
| [[crt.TableDcmStageCell]] | `crt-data-table-dcm-stage-cell` | ❌ |  |
| [[crt.TableEmailCell]] | `crt-data-table-email-cell` | ❌ |  |
| [[crt.TableFileCell]] | `crt-data-table-file-cell` | ❌ |  |
| [[crt.TableFileSizeCell]] | `crt-data-table-file-size-cell` | ❌ |  |
| [[crt.TableNumericCell]] | `crt-data-table-numeric-cell` | ❌ |  |
| [[crt.TablePhoneCell]] | `crt-data-table-phone-cell` | ❌ |  |
| [[crt.TableRichTextEditorCell]] | `crt-data-table-rich-text-editor-cell` | ❌ |  |
| [[crt.TableSliderCell]] | `crt-data-table-slider-cell` | ❌ |  |

## Фільтри

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.SearchFilter]] | `crt-search-filter` | ❌ | Рядок пошуку по колонках гріда. |
| [[crt.QuickFilter]] | `crt-quick-filter` | ❌ | Швидкий фільтр (lookup / date-range / custom) над гридом. Уся «магія» — у прихованому `_filterOptions`. |
| [[crt.FolderTree]] | `crt-folder-tree` | ✅ | Дерево груп (папок) розділу. |
| [[crt.FolderTreeActions]] | `crt-folder-tree-actions` | ❌ |  |
| [[crt.EntityHierarchyFilter]] | `crt-entity-hierarchy-filter` | ❌ | Ієрархічний фільтр (дерево вузлів об'єкта). |
| [[crt.DesignerFiltersContainer]] | `crt-designer-filters-container` | ❌ |  |
| [[crt.LookupQuickFilterMenuItem]] | `crt-lookup-quick-filter-menu-item` | ❌ |  |
| [[crt.FiltersContainer]] | `crt-filters-container` | ❌ |  |

## Дашборди та віджети

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.IndicatorWidget]] | `crt-indicator-widget` | ❌ | Віджет-показник (аналітика). |
| [[crt.ChartWidget]] | `crt-chart-widget` | ❌ | Віджет-графік. |
| [[crt.ListWidget]] | `crt-list-widget` | ❌ |  |
| [[crt.Dashboards]] | `crt-dashboards` | ❌ | Вбудовані дашборди розділу. |
| [[crt.FullPipelineWidget]] | `crt-full-pipeline-widget` | ❌ |  |
| [[crt.FunnelWidget]] | `crt-funnel-widget` | ❌ |  |
| [[crt.GaugeWidget]] | `crt-gauge-widget` | ❌ |  |

## Бізнес-компоненти

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.AccountCompactProfile]] | `crt-account-compact-profile` | ❌ |  |
| [[crt.ContactCompactProfile]] | `crt-contact-compact-profile` | ❌ |  |
| [[crt.NextBestOffer]] | `crt-next-best-offer` | ❌ |  |
| [[crt.EntityStageProgressBar]] | `crt-entity-stage-progress-bar` | ❌ | Індикатор стадій (DCM). |
| [[crt.NextSteps]] | `crt-next-steps` | ❌ | Панель «Наступні кроки». |
| [[crt.ActionDashboard]] | `crt-action-dashboard-7x-dt` | ❌ |  |
| [[crt.AllowedResults]] | `crt-allowed-results` | ⚠️ |  |
| [[crt.Approval]] | `crt-approval` | ❌ |  |
| [[crt.ApprovalList]] | `crt-approval-list` | ❌ |  |
| [[crt.Calendar]] | `crt-calendar` | ❌ |  |
| [[crt.CampaignViewer]] | `crt-campaign-viewer-7x-dt` | ❌ |  |
| [[crt.AgentInbox]] | `crt-agent-inbox` | ❌ |  |
| [[crt.NextBestOfferItem]] | `crt-next-best-offer-item` | ❌ |  |
| [[crt.Playbook]] | `crt-playbook` | ⚠️ |  |
| [[crt.UserCompactProfile]] | `crt-user-compact-profile` | ❌ |  |

## Timeline / Feed / Файли

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.TimelineTile]] | `crt-timeline-tile` | ❌ | Плитка типу запису у Timeline (описова, не має слотів у конфігу — читає препроцесор). |
| [[crt.FileList]] | `crt-file-list` | ✅ | Список файлів (успадковує DataGrid). |
| [[crt.Timeline]] | `crt-timeline` | ❌ | Таймлайн запису (активності, email, дзвінки, фід). |
| [[crt.Feed]] | `crt-feed` | ❌ | Стрічка (коментарі) запису. |
| [[crt.FeedComposer]] | `crt-feed-composer` | ❌ |  |
| [[crt.BaseTimelineLabel]] | `ts-base-timeline-label` | ❌ |  |
| [[crt.FeedItem]] | `crt-feed-item` | ❌ |  |
| [[crt.FileGalleryItem]] | `crt-file-list-gallery-item` | ❌ |  |
| [[crt.FilePreview]] | `crt-file-preview` | ❌ |  |
| [[crt.TimelineEmailLabel]] | `crt-timeline-email-label` | ❌ |  |
| [[crt.TimelineLabel]] | `crt-timeline-label` | ❌ |  |
| [[crt.TimelineLookup]] | `crt-timeline-lookup` | ❌ |  |
| [[crt.TimelinePhoneLabel]] | `crt-timeline-phone-label` | ❌ |  |
| [[crt.TimelineWebLabel]] | `crt-timeline-web-label` | ❌ |  |

## Чати / Omnichannel / повідомлення

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.EmailComposer]] | `crt-email-composer` | ❌ |  |
| [[crt.MessageComposerSelector]] | `crt-message-composer-selector` | ❌ |  |
| [[crt.MessageEditor]] | `crt-message-editor` | ❌ |  |
| [[crt.MessageEditorBody]] | `crt-message-editor-body` | ❌ |  |
| [[crt.MessageEditorInput]] | `crt-message-editor-input` | ❌ |  |
| [[crt.AutoTranslateToggle]] | `crt-auto-translate-toggle` | ✅ |  |
| [[crt.BaseMessageComposer]] | `crt-base-message-composer` | ❌ |  |
| [[crt.BaseMessageComposerSkeleton]] | `crt-base-message-composer-skeleton` | ❌ |  |
| [[crt.CallConversation]] | `crt-call-conversation` | ❌ |  |
| [[crt.ChannelSelector]] | `crt-channel-selector` | ❌ |  |
| [[crt.Chat]] | `crt-chat` | ❌ |  |
| [[crt.ChatDisclaimer]] | `crt-chat-disclaimer` | ❌ |  |
| [[crt.ChatItem]] | `crt-chat-item` | ✅ |  |
| [[crt.ChatList]] | `crt-chat-list` | ❌ |  |
| [[crt.ChatTyping]] | `crt-chat-typing` | ❌ |  |
| [[crt.IncomingItem]] | `crt-incoming-item` | ❌ |  |
| [[crt.IncomingItems]] | `crt-incoming-item-list` | ❌ |  |
| [[crt.MessageEditorReply]] | `crt-message-editor-reply` | ❌ |  |
| [[crt.OperatorState]] | `crt-operator-state` | ⚠️ |  |
| [[crt.TranslateToggle]] | `crt-translate-toggle` | ✅ |  |

## Shell / службові

| Елемент | Селектор | `classes` | Опис |
|---|---|---|---|
| [[crt.ModuleLoader]] | `crt-7x-module` | ❌ | Вбудовування legacy 7.x-модуля (`<crt-7x-module>`). |
| [[crt.AppBackground]] | `crt-app-background` | ⚠️ |  |
| [[crt.AppToolbar]] | `crt-app-toolbar` | ⚠️ |  |
| [[crt.NavigationPanel]] | `crt-navigation-panel` | ✅ |  |
| [[crt.RouterOutlet]] | `crt-router-outlet` | ❌ |  |
| [[crt.DesignTimeActionDashboard]] | `crt-action-dashboard-7x-dt` | ❌ |  |
| [[crt.DesignTimeCampaignViewer]] | `crt-campaign-viewer-7x-dt` | ❌ |  |
| [[crt.NavigationPanelItem]] | `crt-navigation-panel-item` | ⚠️ |  |
| [[crt.SchemaOutlet]] | `crt-schema-outlet` | ❌ |  |
