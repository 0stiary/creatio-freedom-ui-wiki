---
tags: [creatio, freedom-ui, reference]
generated: 2026-09-16
---
# Дерево успадкування view-елементів Freedom UI

Побудовано з ланцюжків `class X extends Y` у коді Shell Creatio 8.3.4.2753. Зареєстровані компоненти — посиланнями, абстрактні бази — **жирним** з описовими іменами (у коді вони мінімізовані; ім'я дано за набором inputs/методів). Дочірній клас отримує всі inputs/outputs предків.

## Абстрактні базові класи

| Назва | Що дає нащадкам |
|---|---|
| **BaseComponent** | корінь: зберігає лише Angular `injector` |
| **BaseViewElement** | спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()` |
| **BaseContainer** | контейнер: `items, padding, visiblePadding, borderRadius, color, stretch, fitContent, responsiveWidth, elementResponsiveWidth`; класи padding/color/borderRadius, реакція на resize |
| **BaseLayoutContainer** | розкладка дітей: читає `layoutConfig` слот-елементів і перетворює на стилі (`getItemLayout`, `applySlotElementStyles`) |
| **BaseTabContainer** | контейнер вкладки зі слотом `tools` |
| **BaseExpansionPanel** | `expanded, title, togglePosition, toggleType, labelColor, tooltip, description, fullWidthHeader, titleWidth, tools, disableOverflow`; події `opened/closed/expandedChange` |
| **BaseFormControl** | поле форми: `label, ariaLabel, appearance, placeholder, disabled, tooltip, control, labelPosition`; події `keyUp, keyDown, blurred, focused`; зв'язок з FormControl (`_initControl`, required, disabled state) |
| **BaseInputControl** | `id, value, readonly, autofocus, autocomplete` (+ `ngDoCheck`) |
| **BaseCheckbox** | `value, inversed, readonly, disabled, ariaLabel, indeterminate, multilineLabel`; `valueChange` |
| **BaseSlider** | `control, value, minValue, maxValue, step, hideLabels, hideThumb, color, height, paddingLineMode` |
| **BaseImageInput** | `value, alt, placeholderMode, colorId, maxFileSize, size, positioning, borderRadius, custom*`; події `imageSelected/imageClear` |
| **BaseButton** | `caption, icon, size, iconSize, iconPosition, color, displayType, clickMode, menuItems, disabled, autofocus, title, textTransform, type, disableRipple, useGlassmorphism`; події `clicked, focused, blurred`; класи розміру/іконки |
| **BaseMenuItem** | `caption, icon, iconColor, visible, disabled, items, handleItemClick`; подія `clicked` |
| **BaseToggleGroup** | `items, value`; `valueChange` |
| **BaseButtonToggleGroup** | `menuButtonsMode, size, iconSize, allowUntoggle, badgeConfig, direction, gap, fitContent, contentAlign, disabled, toggleViewMode`; керує pressed-станом елементів |
| **BaseToggleGroupItem** | `value, displayValue, icon, iconPosition, size, menuItems, pressed, backgroundColor, color, badge, tooltipTitle`; подія `toggleItemClicked` |
| **BaseLabel** | `caption, required, labelType, labelMargin, labelFontSize, labelFontFamily, labelHeight, labelLineHeight, labelLetterSpacing, labelThickness, labelEllipsis, labelTextTransform, labelColor, labelStyle` |
| **BaseTableCell** | комірка гріда: `value, record, column`; `getTitle()` |
| **BaseTextTableCell** | проміжна база текстової комірки |
| **DataGridInputsMixin** | усі inputs/outputs DataGrid без реалізації (`columns, items, features, selectionState, activeRow, sorting, rowToolbarItems, bulkActions…`) — база для віджета-списку |
| **BaseWidget** | віджет дашборда: `sectionBindingColumnRecordId, toolbarMenuItems, listConfig, userProfileData, listData, searchValue, pagingConfig, sortingConfig`; події `drillDown, paginationChange, columnsChange, resetToDefault, getProfileColumns, sortingChange, searchFilterChange, fullScreenStateChanged` |
| **BaseDataItemsCollection** | `items, itemConfig`; перетворює колекцію view-моделей у data items |
| **BaseGalleryItem** | `record, isSelected, tileSizeClasses`; зображення запису, кліки по caption |
| **BaseRecordImage** | джерело зображення запису (`getRecordImage`, `getDefaultImage`, `hasImage`) |
| **BaseFileGalleryItem** | плитка файлу: розмір, меню дій, чекбокс вибору |
| **BaseCompactProfile** | `photo, photoTitle, dialogTitle, referenceColumn, readonly`; події `imageSelected/imageClear` |
| **BaseComposer** | композер повідомлень: `selection, disableSelectionOptions`; події `composerEventChange, selectionChange`; фокус/клік по полю вводу |

## Дерево

- **BaseComponent** — корінь: зберігає лише Angular `injector`
  - **BaseViewElement** — спільний предок усіх view-елементів: inputs `name, id, tabIndex, styles, shape, classes, loading`; `getClasses()/setClasses()`, `setValuesFromConfig()`, `detectChanges()`, `isRtl()`, `focus()`
    - **BaseButton** — `caption, icon, size, iconSize, iconPosition, color, displayType, clickMode, menuItems, disabled, autofocus, title, textTransform, type, disableRipple, useGlassmorphism`; події `clicked, focused, blurred`; класи розміру/іконки
      - [[crt.Button]]
    - **BaseCompactProfile** — `photo, photoTitle, dialogTitle, referenceColumn, readonly`; події `imageSelected/imageClear`
      - [[crt.AccountCompactProfile]]
      - [[crt.ContactCompactProfile]]
      - [[crt.UserCompactProfile]]
    - **BaseComposer** — композер повідомлень: `selection, disableSelectionOptions`; події `composerEventChange, selectionChange`; фокус/клік по полю вводу
      - [[crt.EmailComposer]]
      - [[crt.FeedComposer]]
    - **BaseContainer** — контейнер: `items, padding, visiblePadding, borderRadius, color, stretch, fitContent, responsiveWidth, elementResponsiveWidth`; класи padding/color/borderRadius, реакція на resize
      - **BaseExpansionPanel** — `expanded, title, togglePosition, toggleType, labelColor, tooltip, description, fullWidthHeader, titleWidth, tools, disableOverflow`; події `opened/closed/expandedChange`
        - [[crt.ExpansionPanel]]
      - **BaseLayoutContainer** — розкладка дітей: читає `layoutConfig` слот-елементів і перетворює на стилі (`getItemLayout`, `applySlotElementStyles`)
        - [[crt.FlexContainer]]
        - [[crt.GridContainer]]
      - **BaseTabContainer** — контейнер вкладки зі слотом `tools`
        - [[crt.TabContainer]]
      - [[crt.Chat]]
      - [[crt.ChatDisclaimer]]
      - [[crt.ChatList]]
      - [[crt.Conversation]]
      - [[crt.HeaderContainer]]
      - [[crt.ToggleContainer]]
      - [[crt.ToggleContainerItem]]
    - **BaseDataItemsCollection** — `items, itemConfig`; перетворює колекцію view-моделей у data items
      - [[crt.Gallery]]
    - **BaseFormControl** — поле форми: `label, ariaLabel, appearance, placeholder, disabled, tooltip, control, labelPosition`; події `keyUp, keyDown, blurred, focused`; зв'язок з FormControl (`_initControl`, required, disabled state)
      - **BaseCheckbox** — `value, inversed, readonly, disabled, ariaLabel, indeterminate, multilineLabel`; `valueChange`
        - [[crt.Checkbox]]
      - **BaseInputControl** — `id, value, readonly, autofocus, autocomplete` (+ `ngDoCheck`)
        - [[crt.EncryptedInput]]
        - [[crt.Input]]
          - **BaseImageInput** — `value, alt, placeholderMode, colorId, maxFileSize, size, positioning, borderRadius, custom*`; події `imageSelected/imageClear`
            - [[crt.ImageInput]]
          - [[crt.EmailInput]]
          - [[crt.FileInput]]
          - [[crt.PasswordInput]]
          - [[crt.PhoneInput]]
          - [[crt.WebInput]]
        - [[crt.NumberInput]]
      - [[crt.ColorPicker]]
      - [[crt.ComboBox]]
      - [[crt.DateTimePicker]]
    - **BaseGalleryItem** — `record, isSelected, tileSizeClasses`; зображення запису, кліки по caption
      - **BaseRecordImage** — джерело зображення запису (`getRecordImage`, `getDefaultImage`, `hasImage`)
        - **BaseFileGalleryItem** — плитка файлу: розмір, меню дій, чекбокс вибору
          - [[crt.FileGalleryItem]]
      - [[crt.NextBestOfferItem]]
    - **BaseLabel** — `caption, required, labelType, labelMargin, labelFontSize, labelFontFamily, labelHeight, labelLineHeight, labelLetterSpacing, labelThickness, labelEllipsis, labelTextTransform, labelColor, labelStyle`
      - [[crt.Label]]
        - [[crt.LocalTime]]
        - [[crt.Timer]]
    - **BaseMenuItem** — `caption, icon, iconColor, visible, disabled, items, handleItemClick`; подія `clicked`
      - [[crt.MenuItem]]
        - [[crt.ComboboxAction]]
          - [[crt.ComboboxSearchTextAction]]
    - **BaseSlider** — `control, value, minValue, maxValue, step, hideLabels, hideThumb, color, height, paddingLineMode`
      - [[crt.Slider]]
    - **BaseToggleGroup** — `items, value`; `valueChange`
      - **BaseButtonToggleGroup** — `menuButtonsMode, size, iconSize, allowUntoggle, badgeConfig, direction, gap, fitContent, contentAlign, disabled, toggleViewMode`; керує pressed-станом елементів
        - [[crt.ButtonToggleGroup]]
    - **BaseToggleGroupItem** — `value, displayValue, icon, iconPosition, size, menuItems, pressed, backgroundColor, color, badge, tooltipTitle`; подія `toggleItemClicked`
      - [[crt.ButtonToggleGroupItem]]
    - **BaseWidget** — віджет дашборда: `sectionBindingColumnRecordId, toolbarMenuItems, listConfig, userProfileData, listData, searchValue, pagingConfig, sortingConfig`; події `drillDown, paginationChange, columnsChange, resetToDefault, getProfileColumns, sortingChange, searchFilterChange, fullScreenStateChanged`
      - [[crt.ChartWidget]]
      - [[crt.FunnelWidget]]
      - [[crt.IndicatorWidget]]
        - [[crt.GaugeWidget]]
    - [[crt.ActionDashboard]]
    - [[crt.AgentInbox]]
    - [[crt.AllowedResults]]
    - [[crt.AppBackground]]
    - [[crt.AppToolbar]]
    - [[crt.Approval]]
    - [[crt.ArticlesList]]
    - [[crt.BaseMessageComposerSkeleton]]
    - [[crt.Calendar]]
    - [[crt.CallConversation]]
    - [[crt.CampaignViewer]]
    - [[crt.ChannelSelector]]
    - [[crt.ChipList]]
    - [[crt.CommunicationOptions]]
    - [[crt.ComponentList]]
    - [[crt.Dashboards]]
    - [[crt.DataGrid]]
      - [[crt.ApprovalList]]
      - [[crt.FileList]]
    - [[crt.DeprecatedInput]]
    - [[crt.DeprecatedLabel]]
    - [[crt.EditTypedValueCell]]
    - [[crt.EntityHierarchyFilter]]
    - [[crt.EntityStageProgressBar]]
    - [[crt.Feed]]
    - [[crt.FileDrop]]
    - [[crt.FilterableList]]
    - [[crt.FiltersContainer]]
    - [[crt.FolderTree]]
    - [[crt.FolderTreeActions]]
    - [[crt.FullPipelineWidget]]
    - [[crt.IncomingItem]]
    - [[crt.IncomingItems]]
    - [[crt.Link]]
    - [[crt.List]]
    - [[crt.MessageComposerSelector]]
    - [[crt.MessageEditor]]
    - [[crt.MessageEditorBody]]
    - [[crt.MessageEditorInput]]
    - [[crt.MessageEditorReply]]
    - [[crt.ModuleLoader]]
    - [[crt.MultiSelect]]
    - [[crt.NavigationPanel]]
    - [[crt.NavigationPanelItem]]
    - [[crt.NextBestOffer]]
    - [[crt.NextSteps]]
    - [[crt.ObjectExplorer]]
    - [[crt.OperatorState]]
    - [[crt.Playbook]]
    - [[crt.QuickFilter]]
    - [[crt.RouterOutlet]]
    - [[crt.SchemaOutlet]]
    - [[crt.SearchFilter]]
    - [[crt.SidebarContainer]]
    - [[crt.SkipLinks]]
    - [[crt.Summaries]]
    - [[crt.SummaryItem]]
    - [[crt.TabPanel]]
    - [[crt.TabPanelHeader]]
    - [[crt.TabPanelHeaderItem]]
    - [[crt.TagSelect]]
    - [[crt.TemplateList]]
    - [[crt.Timeline]]
    - [[crt.TimelineLookup]]
    - [[crt.TranslateToggle]]
      - [[crt.AutoTranslateToggle]]
    - [[crt.TypedValueCell]]
- **BaseTableCell** — комірка гріда: `value, record, column`; `getTitle()`
  - **BaseTextTableCell** — проміжна база текстової комірки
    - [[crt.TableTextCell]]
  - [[crt.TableBooleanCell]]
  - [[crt.TableColoredCell]]
  - [[crt.TableDateTimeCell]]
  - [[crt.TableDcmStageCell]]
  - [[crt.TableDcmStageEditingCell]]
  - [[crt.TableEmailCell]]
  - [[crt.TableFileSizeCell]]
  - [[crt.TableNumericCell]]
  - [[crt.TablePhoneCell]]
  - [[crt.TableRichTextEditorCell]]
  - [[crt.TableSliderCell]]
- **DataGridInputsMixin** — усі inputs/outputs DataGrid без реалізації (`columns, items, features, selectionState, activeRow, sorting, rowToolbarItems, bulkActions…`) — база для віджета-списку
  - [[crt.ListWidget]]
- [[crt.BaseTimelineLabel]]
  - [[crt.TimelineEmailLabel]]
  - [[crt.TimelineLabel]]
  - [[crt.TimelinePhoneLabel]]
  - [[crt.TimelineWebLabel]]

## Ланцюжок не розв'язано

Для цих компонентів базовий клас лежить у чанку/модулі, якого немає серед збережених файлів Shell (або імпорт не вдалося зіставити), тому предки невідомі. Фактично всі вони теж наслідують *BaseViewElement*.

[[crt.Badge]], [[crt.BaseMessageComposer]], [[crt.ChatItem]], [[crt.ChatTyping]], [[crt.Chip]], [[crt.DataTableEditDateTimeCell]], [[crt.DataTableEditEmailCell]], [[crt.DataTableEditLookupCell]], [[crt.DataTableEditNumericCell]], [[crt.DataTableEditPhoneCell]], [[crt.DataTableEditTextCell]], [[crt.DataTableEditWebCell]], [[crt.DesignerFiltersContainer]], [[crt.FeedItem]], [[crt.FilePreview]], [[crt.IconRadioButton]], [[crt.ItemWrapper]], [[crt.LookupQuickFilterMenuItem]], [[crt.Menu]], [[crt.MenuDivider]], [[crt.MenuLabel]], [[crt.MultiList]], [[crt.Placeholder]], [[crt.RichTextEditor]], [[crt.RichTextLinkComponent]], [[crt.RichTextVideoComponent]], [[crt.TableFileCell]], [[crt.TimelineTile]]

## Компоненти, від яких наслідують інші компоненти

- [[crt.BaseTimelineLabel]] ← [[crt.TimelineEmailLabel]], [[crt.TimelineLabel]], [[crt.TimelinePhoneLabel]], [[crt.TimelineWebLabel]]
- [[crt.ComboboxAction]] ← [[crt.ComboboxSearchTextAction]]
- [[crt.DataGrid]] ← [[crt.ApprovalList]], [[crt.FileList]]
- [[crt.IndicatorWidget]] ← [[crt.GaugeWidget]]
- [[crt.Input]] ← [[crt.EmailInput]], [[crt.FileInput]], [[crt.ImageInput]], [[crt.PasswordInput]], [[crt.PhoneInput]], [[crt.WebInput]]
- [[crt.Label]] ← [[crt.LocalTime]], [[crt.Timer]]
- [[crt.MenuItem]] ← [[crt.ComboboxAction]], [[crt.ComboboxSearchTextAction]]
- [[crt.TranslateToggle]] ← [[crt.AutoTranslateToggle]]