{
  "Version": "8.3.4.2753",
  "UId": "6783fcb0-748b-441e-a02f-0e0adde4fd93",
  "ManagerName": "ClientUnitSchemaManager",
  "Name": "SqlConsoleModule",
  "Caption": "SqlConsoleModule",
  "ExtendParent": false,
  "DenyExtending": false,
  "Description": "",
  "Less": "#sqlconsole-module-panel {\r
\n\t#sqlconsole-module-panel-buttons-container {\r
\n\t\tmargin-bottom: 16px;\r
\n\t\tspan {\r
\n\t\t\tmargin-right: 9px;\r
\n\t\t}\r
\n\t\t\r
\n\t\t#sqlconsole-module-panel-rowsaffected-container {\r
\n\t\t\tdisplay: inline-block;\r
\n\t\t\ttext-transform: uppercase;\r
\n\t\t\tfont-size: 1.5em;\r
\n\t\t\tcolor: black;\r
\n\t\t\tpadding-top: 0.3em;\r
\n\t\t\tpadding-left: 0.6em;\r
\n\t\t}\r
\n\t}\r
\n\t\r
\n\t.grid-layout-row {\r
\n\t\tpadding-bottom: 4px;\r
\n\t}\r
\n\t\r
\n\t.t-label {\r
\n\t\tcolor: #999999;\r
\n\t\ttext-overflow: ellipsis;\r
\n\t}\r
\n\r
\n\tlabel[id^=\"sqlconsole-module-panel\"] {\r
\n\t\tmin-height: 40px;\r
\n\t}\r
\n}\r
\n\r
\n#sqlconsole-module-panel-item-query-result-container {\r
\n\toverflow: overlay;\r
\n\theight: 550px;\r
\n\tmargin-top: 10px;\r
\n}\r
\n\r
\n#sqlconsole-module-panel-item-settings-section-panel-background-color-label {\r
\n\tpadding-bottom: 16px;\r
\n}\r
\n\r
\n#sqlconsole-module-panel-item-settings-section-panel-background-color-label {\r
\n\tpadding-bottom: 16px;\r
\n}\r
\n\r
\n#sqlconsole-module-panel-item-settings-section-panel-background-color-label {\r
\n\tfont-family: \"Consolas\", serif;\r
\n}\r
\n\r
\n#IsInlineModeCheckBox-wrapEl {\r
\n\tmargin-top: 5px;\r
\n}\r
\n\r
\n.grid-layout-column {\r
\n\tpadding-right: 10px;\r
\n}\r
\n\r
\n#editor { \r
\n\theight: 200px;\r
\n}\r
\n\r
\n.dataTables_wrapper {\r
\n\tmargin-top: 5px;\r
\n}",
  "Js": "/*global ace*/\r
\ndefine(\"SqlConsoleModule\", [\"SqlConsoleModuleResources\", \"JQueryDataTables\", \"AceCodeEditor\", \"SecurityUtilities\", \"css!JQueryDataTables\"],\r
\n    function (resources) {\r
\n\r
\n\t\t/**\r
\n\t\t * Метод очистки результатов запроса\r
\n\t\t */\r
\n\r
\n\t\tvar clearQueryResult = function() {\r
\n\t\t\tvar i = 0;\r
\n\t\t\twhile ($(\"#query-result-table\" + i).length != 0) {\r
\n\t\t\t\t$(\"#query-result-table\" + i).DataTable().destroy();\r
\n\t\t\t\t$(\"#query-result-table\" + i).remove();\r
\n\t\t\t\ti++;\r
\n\t\t\t}\r
\n\t\t\t$(\"#query-result-text\").remove();\r
\n\t\t}\r
\n\r
\n        /**\r
\n         * Выполняет вызов метода сервиса\r
\n         * @param methodName Название метода\r
\n         * @param data\r
\n         * @param callback Функция-callback\r
\n         */\r
\n        var callServiceMethod = function (methodName, data, callback) {\r
\n            Terrasoft.AjaxProvider.request({\r
\n                url: Terrasoft.workspaceBaseUrl + \"/rest/SqlConsoleService/\" + methodName,\r
\n                headers: {\r
\n                    \"Accept\": \"application/json\",\r
\n                    \"Content-Type\": \"application/json\"\r
\n                },\r
\n                method: \"POST\",\r
\n                jsonData: data || {},\r
\n                callback: function (request, success, response) {\r
\n                    var responseObject = {};\r
\n                    if (success) {\r
\n                        var obj = Terrasoft.decode(response.responseText);\r
\n                        responseObject = obj[methodName + \"Result\"];\r
\n                        callback.call(this, responseObject);\r
\n                    } else {\r
\n                        clearQueryResult();\r
\n                        switch (Terrasoft.SysValue.CURRENT_USER_CULTURE.value) {\r
\n\t\t\t\t    \tcase \"a5420246-0a8e-e111-84a3-00155d054c03\":\r
\n\t\t\t\t    \t\tthis.Terrasoft.utils.showInformation(\"An error occurred while querying!\", null, this);\r
\n\t\t\t\t    \t\tbreak;\r
\n\t\t\t\t    \tcase \"1a778e3f-0a8e-e111-84a3-00155d054c03\":\r
\n\t\t\t\t    \t\tthis.Terrasoft.utils.showInformation(\"При выполнении запроса произошла ошибка!\", null, this);\r
\n\t\t\t\t    \tdefault:\r
\n\t\t\t\t    \t\t// code\r
\n\t\t\t\t\t\t}\r
\n                    }\r
\n                },\r
\n                scope: this\r
\n            });\r
\n        };\r
\n\r
\n        /**\r
\n         * Выводит результат выполнения запроса на страницу в компонент-таблицу JQueryTablesorter\r
\n         * @param result\r
\n         */\r
\n\r
\n\t\tvar showQueryResult = function(result, scope) {\r
\n\t\t\tclearQueryResult();\r
\n\t\t\tif (result.Success) {\r
\n\t\t\t\tif (result.QueryResults) {\r
\n\t\t\t\t\tfor (var i = 0; i < result.QueryResults.length; i++) {\r
\n\t\t\t\t\t\t$(\"#sqlconsole-module-panel\").append('<table id=\"query-result-table'+ i + '\" class=\"display\" width=\"100%\"></table>');\r
\n\t\t\t\t\t\tvar columns = formDataTableColumns(result.QueryResults[i].Columns);\r
\n\t\t\t\t\t\tvar dataSet = result.QueryResults[i].Rows;\r
\n\t\t\t\t\t\t$(\"#query-result-table\" + i).DataTable({\r
\n\t\t\t\t\t\t\tscrollY: \"auto\",\r
\n\t\t\t\t\t\t\tscrollX: true,\r
\n\t\t\t\t\t\t\tscrollCollapse: false,\r
\n\t\t\t\t\t\t\torder: [],\r
\n\t\t\t\t\t\t\tlanguage: {\r
\n\t\t\t\t\t\t\t//\t\"decimal\": \"\",\r
\n\t\t\t\t\t\t\t\t\"emptyTable\": scope.get(\"Resources.Strings.DataTableEmptyTable\"),//\"No data available in table\",\r
\n\t\t\t\t\t\t\t\t\"info\": scope.get(\"Resources.Strings.DataTableInfo\"),//\"Showing _START_ to _END_ of _TOTAL_ entries\",\r
\n\t\t\t\t\t\t\t\t\"infoEmpty\": scope.get(\"Resources.Strings.DataTableInfoEmpty\"),//\"Showing 0 to 0 of 0 entries\",\r
\n\t\t\t\t\t\t\t\t\"infoFiltered\": scope.get(\"Resources.Strings.DataTableInfoFiltered\"),//\"(filtered from _MAX_ total entries)\",\r
\n\t\t\t\t\t\t\t//\t\"infoPostFix\": \"\",\r
\n\t\t\t\t\t\t\t//\t\"thousands\": \",\",\r
\n\t\t\t\t\t\t\t\t\"lengthMenu\": scope.get(\"Resources.Strings.DataTableLengthMenu\"),//\"Show _MENU_ entries\",\r
\n\t\t\t\t\t\t\t\t\"loadingRecords\": scope.get(\"Resources.Strings.DataTableLoadingRecords\"),//\"Loading...\",\r
\n\t\t\t\t\t\t\t\t\"processing\": scope.get(\"Resources.Strings.DataTableProcessing\"),//\"Processing...\",\r
\n\t\t\t\t\t\t\t\t\"search\": scope.get(\"Resources.Strings.DataTableSearch\"),//\"Search:\",\r
\n\t\t\t\t\t\t\t\t\"zeroRecords\": scope.get(\"Resources.Strings.DataTableZeroRecords\"),//\"No matching records found\",\r
\n\t\t\t\t\t\t\t\t\"paginate\": {\r
\n\t\t\t\t\t\t\t\t//\t\"first\": \"First\",\r
\n\t\t\t\t\t\t\t\t//\t\"last\": \"Last\",\r
\n\t\t\t\t\t\t\t\t\t\"next\": scope.get(\"Resources.Strings.DataTablePaginateNext\"),//\"Next\",\r
\n\t\t\t\t\t\t\t\t\t\"previous\": scope.get(\"Resources.Strings.DataTablePaginatePrevious\")//\"Previous\"\r
\n\t\t\t\t\t\t\t\t},\r
\n\t\t\t\t\t\t\t\t//\"aria\": {\r
\n\t\t\t\t\t\t\t\t//\t\"sortAscending\":  \": activate to sort column ascending\",\r
\n\t\t\t\t\t\t\t\t//\t\"sortDescending\": \": activate to sort column descending\"\r
\n\t\t\t\t\t\t\t\t//}\r
\n\t\t\t\t\t\t\t},\r
\n\t\t\t\t\t\t\tdata: dataSet,\r
\n\t\t\t\t\t\t\tcolumns: columns\r
\n\t\t\t\t\t\t});\r
\n\t\t\t\t\t}\r
\n\t\t\t\t}\r
\n\t\t\t\twindow.$(\"#sqlconsole-module-panel-rowsaffected-container\").html(result.RowsAffected + \" row(s) affected\");\r
\n\t\t\t}\r
\n\t\t\telse {\r
\n\t\t\t\tif (result.SecurityError) {\r
\n\t\t\t\t\t$(\"#sqlconsole-module-panel\").append('<div id=\"query-result-text\" width=\"100%\"><font size=\"3\" color=\"red\" face=\"Consolas\">' + scope.get(\"Resources.Strings.AccessError\") + '</font></div>');\r
\n\t\t\t\t} else {\r
\n\t\t\t\t\tvar htmlErrorMessage = formHtmlErrorMessage(result.ErrorMessage);\r
\n\t\t\t\t\t$(\"#sqlconsole-module-panel\").append('<div id=\"query-result-text\" width=\"100%\"><font size=\"3\" color=\"red\" face=\"Consolas\">' + htmlErrorMessage + '</font></div>');\r
\n\t\t\t\t}\r
\n\t\t\t}\r
\n            var editor = ace.edit(\"editor\");\r
\n            editor.focus();\r
\n        };\r
\n\r
\n\t\tvar formHtmlErrorMessage = function(data) {\r
\n\t\t\tvar lines = data.split('\
\n');\r
\n\t\t\tvar htmlLines = \"\";\r
\n\t\t\tfor (i = 0; i < lines.length; i++) {\r
\n\t\t\t\thtmlLines += lines[i] + '<br>';\r
\n\t\t\t}\r
\n\t\t\treturn htmlLines;\r
\n\t\t};\r
\n\r
\n\t\tvar formDataTableColumns = function(data) {\r
\n\t\t\tvar result = [];\r
\n\t\t\tfor (var i = 0; i < data.length; i++) {\r
\n\t\t\t\tresult.push({title: data[i]});\r
\n\t\t\t}\r
\n\t\t\treturn result;\r
\n\t\t};\r
\n\r
\n\t\tvar NULL_VALUE = \"NULL\";\r
\n\t\tvar DATE_RE = /^\\d{1,4}[.\\/-]\\d{1,2}[.\\/-]\\d{1,4}(?: \\d{1,2}:\\d{2}(?::\\d{2})?(?: ?[AP]M)?)?$/i;\r
\n\t\tvar NUMBER_RE = /^-?\\d+(?:[.,]\\d+)?$/;\r
\n\r
\n\t\tvar parseServerDate = function(value) {\r
\n\t\t\tvar parts = value.match(/\\d+/g);\r
\n\t\t\tif (!parts || parts.length < 3) {\r
\n\t\t\t\treturn NaN;\r
\n\t\t\t}\r
\n\t\t\tvar order = Terrasoft.Resources.CultureSettings.dateFormat.replace(/[^djmnYy]/g, \"\");\r
\n\t\t\tvar dayIdx = order.search(/[dj]/), monthIdx = order.search(/[mn]/), yearIdx = order.search(/[Yy]/);\r
\n\t\t\tif (dayIdx < 0 || monthIdx < 0 || yearIdx < 0) {\r
\n\t\t\t\treturn NaN;\r
\n\t\t\t}\r
\n\t\t\tvar year = +parts[yearIdx];\r
\n\t\t\tif (year < 100) { year += 2000; }\r
\n\t\t\tvar hours = +(parts[3] || 0);\r
\n\t\t\tif (/PM/i.test(value) && hours < 12) { hours += 12; }\r
\n\t\t\tif (/AM/i.test(value) && hours === 12) { hours = 0; }\r
\n\t\t\treturn new Date(year, +parts[monthIdx] - 1, +parts[dayIdx], hours, +(parts[4] || 0), +(parts[5] || 0)).getTime();\r
\n\t\t};\r
\n\r
\n\t\tvar parseServerNumber = function(value) {\r
\n\t\t\tvar normalized = value.replace(Terrasoft.Resources.CultureSettings.decimalSeparator, \".\");\r
\n\t\t\treturn /^-?\\d+(?:\\.\\d+)?$/.test(normalized) ? parseFloat(normalized) : NaN;\r
\n\t\t};\r
\n\r
\n\t\tvar registerSortTypes = function() {\r
\n\t\t\tvar ext = $.fn.dataTable.ext;\r
\n\t\t\tif (ext.type.order[\"sql-date-pre\"]) {\r
\n\t\t\t\treturn;\r
\n\t\t\t}\r
\n\t\t\tvar isNull = function(d) {\r
\n\t\t\t\treturn d === NULL_VALUE || d === \"\" || d === null;\r
\n\t\t\t};\r
\n\t\t\t// детектори перебираються по порядку; свої ставимо перед вбудованими\r
\n\t\t\text.type.detect.unshift(function(d) {\r
\n\t\t\t\tif (isNull(d)) { return \"sql-date\"; }\r
\n\t\t\t\treturn typeof d === \"string\" && DATE_RE.test(d) && !isNaN(parseServerDate(d)) ? \"sql-date\" : null;\r
\n\t\t\t});\r
\n\t\t\text.type.detect.unshift(function(d) {\r
\n\t\t\t\tif (isNull(d)) { return \"sql-num\"; }\r
\n\t\t\t\treturn typeof d === \"string\" && NUMBER_RE.test(d) && !isNaN(parseServerNumber(d)) ? \"sql-num\" : null;\r
\n\t\t\t});\r
\n\t\t\text.type.order[\"sql-date-pre\"] = function(d) {\r
\n\t\t\t\tvar t = typeof d === \"string\" ? parseServerDate(d) : NaN;\r
\n\t\t\t\treturn isNaN(t) ? -Infinity : t;\r
\n\t\t\t};\r
\n\t\t\text.type.order[\"sql-num-pre\"] = function(d) {\r
\n\t\t\t\tvar n = typeof d === \"string\" ? parseServerNumber(d) : NaN;\r
\n\t\t\t\treturn isNaN(n) ? -Infinity : n;\r
\n\t\t\t};\r
\n\t\t};\r
\n\r
\n        return Ext.define(\"Terrasoft.configuration.SqlConsoleModule\", {\r
\n            extend: \"Terrasoft.BaseModule\",\r
\n            alternateClassName: \"Terrasoft.SqlConsoleModule\",\r
\n            mixins: {\r
\n\t\t\t\tSecurityUtilitiesMixin: \"Terrasoft.SecurityUtilitiesMixin\"\r
\n\t\t\t},\r
\n            Ext: null,\r
\n            sandbox: null,\r
\n            Terrasoft: null,\r
\n            isAsync: true,\r
\n\r
\n            /**\r
\n             * Инициализирует модуль.\r
\n             * @param callback Функция, которая будет вызвана после инициализации модуля.\r
\n             * @param scope Область видимости.\r
\n             */\r
\n            init: function (callback, scope) {\r
\n                this.callParent(arguments);\r
\n                this.initDataTables();\r
\n                //this.checkAvailability(function() {\r
\n\t                var localizableStrings = resources.localizableStrings;\r
\n\t                var headerCaption = localizableStrings.HeaderCaption;\r
\n\t                this.sandbox.publish(\"ChangeHeaderCaption\", {\r
\n\t                    isMainMenu: false,\r
\n\t                    caption: headerCaption,\r
\n\t                    dataViews: this.Ext.create(\"Terrasoft.Collection\")\r
\n\t                });\r
\n\t                this.sandbox.subscribe(\"NeedHeaderCaption\", function () {\r
\n\t                    this.sandbox.publish(\"InitDataViews\", {\r
\n\t                        isMainMenu: false,\r
\n\t                        caption: headerCaption,\r
\n\t                        dataViews: this.Ext.create(\"Terrasoft.Collection\")\r
\n\t                    });\r
\n\t                }, this);\r
\n\t                this.initHistoryState();\r
\n\t                this.initViewModel({\r
\n\t                    callback: callback,\r
\n\t                    scope: scope\r
\n\t                });\r
\n                //});\r
\n            },\r
\n\r
\n            //Добавлено из-за проблем с кэшированием jQuery при переходе из другого раздела.\r
\n            initDataTables: function() {\r
\n            \tvar dataTables = require('JQueryDataTables');\r
\n\t\t\t\t$ = dataTables.$;\r
\n\t\t\t\tregisterSortTypes();\r
\n            },\r
\n\r
\n            /**\r
\n             * Инициализирует ViewModel\r
\n             * @param options\r
\n             */\r
\n            initViewModel: function (options) {\r
\n                var callback = options.callback;\r
\n                var scope = options.scope;\r
\n                var values = {\r
\n                    IsExportToCsvVisible: false,\r
\n                    QueryResults: {},\r
\n                    QueryTime: 0,\r
\n                    QueryTimeLabelCaption: \"\",\r
\n                    QueryTimerId: 0\r
\n                };\r
\n                var columns = {\r
\n                    IsExportToCsvVisible: {dataValueType: Terrasoft.DataValueType.BOOLEAN},\r
\n                    QueryResults: {dataValueType: Terrasoft.DataValueType.COLLECTION},\r
\n                    QueryTime: {dataValueType: Terrasoft.DataValueType.INTEGER},\r
\n\t\t            QueryTimeLabelCaption: {dataValueType: Terrasoft.DataValueType.TEXT},\r
\n\t\t            QueryTimerId: {dataValueType: Terrasoft.DataValueType.INTEGER}\r
\n                };\r
\n                this.viewModel = this.createViewModel({\r
\n                    values: values,\r
\n                    columns: columns\r
\n                });\r
\n                this.initResources(this.viewModel, resources);\r
\n                if (callback) {\r
\n                    callback.call(scope);\r
\n                }\r
\n            },\r
\n\r
\n            initResources: function(scope, resources) {\r
\n\t\t\t\tresources = resources || {};\r
\n\t\t\t\tTerrasoft.each(resources.localizableStrings, function(value, key) {\r
\n\t\t\t\t\tscope.set(\"Resources.Strings.\" + key, value);\r
\n\t\t\t\t}, scope);\r
\n\t\t\t\tTerrasoft.each(resources.localizableImages, function(value, key) {\r
\n\t\t\t\t\tscope.set(\"Resources.Images.\" + key, value);\r
\n\t\t\t\t}, scope);\r
\n\t\t\t},\r
\n\r
\n            /**\r
\n             * Создает ViewModel\r
\n             * @param options\r
\n             * @returns {Terrasoft.BaseViewModel}\r
\n             */\r
\n            createViewModel: function (options) {\r
\n                var Terrasoft = this.Terrasoft;\r
\n                var sandbox = this.sandbox;\r
\n                var columns = options.columns;\r
\n                columns.hasChanges = {\r
\n                    dataValueType: Terrasoft.DataValueType.BOOLEAN,\r
\n                    isRequired: false\r
\n                };\r
\n                var values = options.values;\r
\n                values.hasChanges = false;\r
\n                return this.Ext.create(\"Terrasoft.BaseViewModel\", {\r
\n                    columns: columns,\r
\n                    values: values,\r
\n                    methods: {\r
\n                        /**\r
\n                         * Обрабатывает нажатие на кнопку \"Найти\"\r
\n                         */\r
\n                        onExecute: function () {\r
\n\t                        var sqlScript = this.getSqlScript(true);\r
\n\t                        if (!sqlScript) {\r
\n\t                        \treturn this.onClear();\r
\n\t                        }\r
\n                            var scope = this;\r
\n                            this.clearQueryTimer(this);\r
\n                            this.setAttributesToDefaultValues(this);\r
\n                            this.setQueryTimeLabelCaption(this);\r
\n                            var queryTimerId = setInterval(this.setQueryTimeLabelCaption, 1000, this);\r
\n                            this.set(\"QueryTimerId\", queryTimerId);\r
\n\t                        var data = { sqlScript: sqlScript };\r
\n                            callServiceMethod(\"ExecuteSqlScript\", data, function (result) {\r
\n                            \tif (result.Success && result.QueryResults.length != 0) {\r
\n                            \t\tscope.set(\"IsExportToCsvVisible\", true);\r
\n                            \t\tscope.set(\"QueryResults\", result.QueryResults);\r
\n                            \t}\r
\n                                showQueryResult(result, scope);\r
\n                                scope.clearQueryTimer(scope);\r
\n                            });\r
\n                        },\r
\n                        /**\r
\n                         * Обрабатывает нажатие на кнопку \"Закрыть\"\r
\n                         */\r
\n                        onClose: function() {\r
\n                            sandbox.publish(\"BackHistoryState\");\r
\n                        },\r
\n                        /**\r
\n                         * Обрабатывает нажатие на кнопку \"Очистить\"\r
\n                         */\r
\n                        onClear: function() {\r
\n                        \tclearQueryResult();\r
\n                        \tthis.clearQueryTimer(this);\r
\n                            this.setAttributesToDefaultValues(this);\r
\n                        \tvar editor = this.getEditor();\r
\n                            editor.setValue(\"\");\r
\n                            editor.focus();\r
\n                        },\r
\n                        onGetSqlConsoleLog:function () {\r
\n                            var scope = this;\r
\n                            this.clearQueryTimer(this);\r
\n                            this.setAttributesToDefaultValues(this);\r
\n                            this.setQueryTimeLabelCaption(this);\r
\n                            var queryTimerId = setInterval(this.setQueryTimeLabelCaption, 1000, this);\r
\n                            this.set(\"QueryTimerId\", queryTimerId);\r
\n                            var data = { sqlScript: this.getSqlScript() };\r
\n                            callServiceMethod(\"GetSqlConsoleLog\", data, function (result) {\r
\n                            \tif (result.Success && result.QueryResults.length != 0) {\r
\n                            \t\tscope.set(\"IsExportToCsvVisible\", true);\r
\n                            \t\tscope.set(\"QueryResults\", result.QueryResults);\r
\n                            \t}\r
\n                                showQueryResult(result, scope);\r
\n                                scope.clearQueryTimer(scope);\r
\n                            });\r
\n                        },\r
\n                        onExportToCsv: function() {\r
\n                        \tvar scope = this;\r
\n                        \tTerrasoft.SysSettings.querySysSettingsItem(\"CSVDelimiter\",\r
\n\t\t\t\t\t\t\t\tfunction(value) {\r
\n\t\t\t\t\t\t\t\t\tvar csvDelimiter = value;\r
\n\t\t\t\t\t\t\t\t\tvar csvData  = \"\\uFEFF\";\r
\n\r
\n\t\t\t\t\t\t\t\t\tvar queryResults = this.get(\"QueryResults\");\r
\n\t\t\t\t\t\t\t\t\tfor (var p = 0; p < queryResults.length; p++) {\r
\n\t\t\t\t\t\t\t\t\t\tvar selectedColumns = queryResults[p].Columns;\r
\n\t\t\t\t\t\t\t\t\t\tfor (var i = 0; i < selectedColumns.length; i++) {\r
\n\t\t\t\t\t\t\t\t\t\t\tcsvData += selectedColumns[i];\r
\n\t\t\t\t\t\t\t\t\t\t\tif (i != selectedColumns.length  - 1) {\r
\n\t\t\t\t\t\t\t\t\t\t\t\tcsvData += csvDelimiter;\r
\n\t\t\t\t\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\t\t\tcsvData += \"\
\n\";\r
\n\t\t\t\t\t\t\t\t\t\tvar selectedRows = queryResults[p].Rows;\r
\n\t\t\t\t\t\t\t\t\t\tfor (var i = 0; i < selectedRows.length; i++) {\r
\n\t\t\t\t\t\t\t\t\t\t\tfor (var j = 0; j < selectedRows[i].length; j++) {\r
\n\t\t\t\t\t\t\t\t\t\t\t\tcsvData += selectedRows[i][j].replace(/\
\n/g, \" \"); // Для поддержки многострочного текста\r
\n\t\t\t\t\t\t\t\t\t\t\t\tif (j != (selectedRows[i].length - 1)) {\r
\n\t\t\t\t\t\t\t\t\t\t\t\t\tcsvData += csvDelimiter;\r
\n\t\t\t\t\t\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\t\t\t\tif (i != (selectedRows.length - 1)) {\r
\n\t\t\t\t\t\t\t\t\t\t\t\tcsvData += \"\
\n\";\r
\n\t\t\t\t\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\t\t\tif (p != (queryResults.length - 1)) {\r
\n\t\t\t\t\t\t\t\t\t\t\tcsvData += \"\
\n\";\r
\n\t\t\t\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\t\t}\r
\n\r
\n\t\t\t\t\t\t\t\t\tvar blob = new Blob([csvData], {\r
\n\t\t\t\t\t\t\t\t\t\ttype : \"application/csv;charset=utf-8;\"\r
\n\t\t\t\t\t\t\t\t\t});\r
\n\t\t\t\t\t\t\t\t\tvar csvFile = document.createElement(\"a\");\r
\n\t\t\t\t\t\t\t\t\tcsvFile.href = URL.createObjectURL(blob);\r
\n\t\t\t\t\t\t\t\t\tcsvFile.download = \"Select.csv\";\r
\n\t\t\t\t\t\t\t\t\tdocument.body.appendChild(csvFile);\r
\n\t\t\t\t\t\t\t\t\tcsvFile.click();\r
\n\t\t\t\t\t\t\t\t\tdocument.body.removeChild(csvFile);\r
\n\t\t\t\t\t\t\t\t},\r
\n\t\t\t\t\t\t\t\tthis);\r
\n                        },\r
\n                        setQueryTimeLabelCaption: function(scope) {\r
\n                        \tvar queryTime = scope.get(\"QueryTime\");\r
\n                        \tvar queryTimeLabelCaption = scope.get(\"Resources.Strings.QueryTimeLabelCaptionPrefix\") + queryTime + scope.get(\"Resources.Strings.QueryTimeLabelCaptionPostfix\");\r
\n                        \tscope.set(\"QueryTimeLabelCaption\", queryTimeLabelCaption);\r
\n                        \tscope.set(\"QueryTime\", queryTime + 1);\r
\n                        },\r
\n                        setAttributesToDefaultValues: function(scope) {\r
\n                        \tscope.set(\"IsExportToCsvVisible\", false);\r
\n                        \tscope.set(\"QueryTime\", 0);\r
\n                        \tscope.set(\"QueryTimeLabelCaption\", \"\");\r
\n                        \tscope.set(\"QueryTime\", 0);\r
\n                        \tscope.set(\"QueryResults\", {});\r
\n                        },\r
\n                        clearQueryTimer: function(scope) {\r
\n                        \tvar queryTimerId = scope.get(\"QueryTimerId\");\r
\n                            if (queryTimerId) {\r
\n                            \tclearInterval(queryTimerId);\r
\n                            };\r
\n                        },\r
\n\t                    init: function() {\r
\n\t\t                    var sqlScript = this.getLocalStore().getItem(\"SqlConsoleLastScript\") || \"\";\r
\n\t\t                    if (sqlScript.trim()) {\r
\n\t\t\t                    this.getEditor().setValue(sqlScript);\r
\n\t\t                    }\r
\n\t\t                    this.addHotkeys();\r
\n\t\t                    Ext.EventManager.on(window, \"beforeunload\", this.onBeforeUnload, this);\r
\n\t                    },\r
\n\t                    addHotkeys: function() {\r
\n\t\t                    var doc = Ext.getDoc();\r
\n\t\t                    doc.on(\"keydown\", this.onKeyDown, this);\r
\n\t\t                    var editor = this.getEditor();\r
\n\t\t                    editor.commands.removeCommand('gotoline');\r
\n\t                    },\r
\n\t                    removeHotkeys: function() {\r
\n\t\t                    var doc = Ext.getDoc();\r
\n\t\t                    doc.un(\"keydown\", this.onKeyDown, this);\r
\n\t                    },\r
\n\t                    onKeyDown: function(e) {\r
\n\t\t                    if (e.keyCode === e.ENTER && e.ctrlKey && !e.shiftKey && !e.altKey) {\r
\n\t\t\t                    e.preventDefault();\r
\n\t\t\t                    this.onExecute();\r
\n\t\t\t                    return false;\r
\n\t\t                    }\r
\n\t\t                    if (e.keyCode === e.L && e.ctrlKey && !e.shiftKey && !e.altKey) {\r
\n\t\t\t                    e.preventDefault();\r
\n\t\t\t                    this.onClear();\r
\n\t\t\t                    return false;\r
\n\t\t                    }\r
\n\t\t                    if (e.keyCode === e.S && e.ctrlKey && !e.shiftKey && !e.altKey) {\r
\n\t\t\t                    e.preventDefault();\r
\n\t\t\t                    this.onSaveSql();\r
\n\t\t\t                    return false;\r
\n\t\t                    }\r
\n\t\t                    if (e.keyCode === e.S && e.ctrlKey && e.shiftKey && !e.altKey) {\r
\n\t\t\t                    e.preventDefault();\r
\n\t\t\t                    this.onExportToCsv();\r
\n\t\t\t                    return false;\r
\n\t\t                    }\r
\n\t\t                    if (e.keyCode === e.H && e.ctrlKey && e.shiftKey && !e.altKey) {\r
\n\t\t\t                    e.preventDefault();\r
\n\t\t\t                    this.onGetSqlConsoleLog();\r
\n\t\t\t                    return false;\r
\n\t\t                    }\r
\n\t                    },\r
\n\t                    onSaveSql: function() {\r
\n\t\t                    var sqlScript = this.getSqlScript();\r
\n\t\t                    if (!sqlScript) {\r
\n\t\t\t                    return;\r
\n\t\t                    }\r
\n\t\t                    var link = document.createElement(\"a\");\r
\n\t\t                    document.body.appendChild(link);\r
\n\t\t                    link.style = \"display: none\";\r
\n\t\t                    var blob = new Blob([sqlScript], {type: \"text/plain;charset=UTF-8\"});\r
\n\t\t                    var url = URL.createObjectURL(blob);\r
\n\t\t                    link.href = url;\r
\n\t\t                    var d = Ext.util.Format.date(new Date(), 'Ymd_Gis');\r
\n\t\t                    link.download = Terrasoft.getFormattedString(\"script_{0}.sql\", d);\r
\n\t\t                    link.click();\r
\n\t\t                    URL.revokeObjectURL(url);\r
\n\t\t                    setTimeout(function() {\r
\n\t\t\t                    document.body.removeChild(link);\r
\n\t\t                    });\r
\n\t                    },\r
\n\t                    getEditor: function() {\r
\n\t\t                    var id = \"editor\";\r
\n\t\t                    return document.getElementById(id) ? ace.edit(\"editor\") : null;\r
\n\t\t\t            },\r
\n\t\t\t            getSqlScript: function(onlySelected) {\r
\n\t\t                    var editor = this.getEditor();\r
\n\t\t                    var script = '';\r
\n\t\t                    if (onlySelected) {\r
\n\t\t\t                    script = editor.getSelectedText().trim();\r
\n\t\t                    }\r
\n\t\t                    return script || editor.getValue().trim();\r
\n\t                    },\r
\n\t                    getLocalStore: function() {\r
\n\t\t                    if (!Terrasoft.DomainCache) {\r
\n\t\t\t                    var domainCacheConfig = {\r
\n\t\t\t\t                    levelName: \"Domain\",\r
\n\t\t\t\t                    type: \"Terrasoft.LocalStore\",\r
\n\t\t\t\t                    isCache: true\r
\n\t\t\t                    };\r
\n\t\t\t                    Terrasoft.StoreManager.registerStores([domainCacheConfig]);\r
\n\t\t                    }\r
\n\t\t                    return Terrasoft.DomainCache;\r
\n\t                    },\r
\n\t                    saveSqlScript: function() {\r
\n\t\t                    this.getLocalStore().setItem(\"SqlConsoleLastScript\", this.getSqlScript());\r
\n\t                    },\r
\n\t                    onBeforeUnload: function() {\r
\n\t\t                    this.saveSqlScript();\r
\n\t                    },\r
\n\t                    onDestroy: function() {\r
\n                        \tif (this.getEditor()) {\r
\n\t\t                        this.saveSqlScript();\r
\n\t                        }\r
\n\t\t                    this.removeHotkeys();\r
\n\t\t                    Ext.EventManager.un(window, \"beforeunload\", this.onBeforeUnload, this);\r
\n\t                    }\r
\n                    }\r
\n                });\r
\n            },\r
\n\r
\n            /**\r
\n             * Генерирует представление модуля\r
\n             * @returns {Terrasoft.GridLayout} Представление модуля.\r
\n             */\r
\n            generateView: function () {\r
\n                var localizableStrings = resources.localizableStrings;\r
\n                var view = this.Ext.create(\"Terrasoft.GridLayout\", {\r
\n                    id: \"sqlconsole-module-panel\",\r
\n                    items: [\r
\n                        {\r
\n                            item: Ext.create(\"Terrasoft.Container\", {\r
\n                                id: \"sqlconsole-module-panel-buttons-container\",\r
\n                                items: [\r
\n                                    Ext.create(\"Terrasoft.Button\", {\r
\n                                        caption: localizableStrings.ExecuteButton,\r
\n                                        style: Terrasoft.controls.ButtonEnums.style.GREEN,\r
\n\t                                    tips: [{tip: {content: localizableStrings.ExecuteButtonTip}}],\r
\n                                        click: {bindTo: \"onExecute\"}\r
\n                                    }),\r
\n                                    Ext.create(\"Terrasoft.Button\", {\r
\n                                        caption: localizableStrings.CloseButton,\r
\n\t                                    tips: [{tip: {content: localizableStrings.CloseButtonTip}}],\r
\n                                        click: {bindTo: \"onClose\"}\r
\n                                    }),\r
\n                                    Ext.create(\"Terrasoft.Button\", {\r
\n                                        caption: localizableStrings.ClearButton,\r
\n\t                                    tips: [{tip: {content: localizableStrings.ClearButtonTip}}],\r
\n                                        click: {bindTo: \"onClear\"}\r
\n                                    }),\r
\n                                    Ext.create(\"Terrasoft.Button\", {\r
\n                                        caption: localizableStrings.ShowQueryLogButton,\r
\n\t                                    tips: [{tip: {content: localizableStrings.ShowQueryLogButtonTip}}],\r
\n                                        click: {bindTo: \"onGetSqlConsoleLog\"}\r
\n                                    }),\r
\n                                    Ext.create(\"Terrasoft.Button\", {\r
\n                                        caption: localizableStrings.ExportToCsvButton,\r
\n\t                                    tips: [{tip: {content: localizableStrings.ExportToCsvButtonTip}}],\r
\n                                        click: {bindTo: \"onExportToCsv\"},\r
\n                                        enabled: {bindTo: \"IsExportToCsvVisible\"}\r
\n                                    }),\r
\n                                    Ext.create(\"Terrasoft.Button\", {\r
\n                                        caption: localizableStrings.SaveSqlButton,\r
\n\t                                    tips: [{tip: {content: localizableStrings.SaveSqlButtonTip}}],\r
\n                                        click: {bindTo: \"onSaveSql\"}\r
\n                                    }),\r
\n                                    Ext.create(\"Terrasoft.Container\", {\r
\n\t\t                                id: \"sqlconsole-module-panel-rowsaffected-container\",\r
\n\t\t                                items: []\r
\n                                    })\r
\n                                ]\r
\n                            }),\r
\n                            column: 0,\r
\n                            row: 0,\r
\n                            colSpan: 24,\r
\n                            rowSpan: 1\r
\n                        },\r
\n                        {\r
\n                            item: Ext.create(\"Terrasoft.Container\", {\r
\n                                id: \"editor\"\r
\n                            }),\r
\n                            column: 0,\r
\n                            row: 1,\r
\n                            colSpan: 24,\r
\n                            rowSpan: 1\r
\n                        },\r
\n                        {\r
\n                            item: Ext.create(\"Terrasoft.Container\", {\r
\n                                id: \"query-time-container\",\r
\n                                items: [\r
\n                                    Ext.create(\"Terrasoft.Label\", {\r
\n                                        caption: {bindTo: \"QueryTimeLabelCaption\"}\r
\n                                    })\r
\n                                ]\r
\n                            }),\r
\n                            column: 0,\r
\n                            row: 2,\r
\n                            colSpan: 24,\r
\n                            rowSpan: 1\r
\n                        }]\r
\n                });\r
\n                return view;\r
\n            },\r
\n\r
\n            /**\r
\n             * Запускает процесс рендеринга модуля.\r
\n             */\r
\n            render: function (renderTo) {\r
\n                var view = this.generateView();\r
\n                view.bind(this.viewModel);\r
\n                view.render(renderTo);\r
\n                //MaskHelper.HideBodyMask();\r
\n\r
\n                var editor = ace.edit(\"editor\");\r
\n\t\t\t    editor.setTheme(\"ace/theme/sqlserver\");\r
\n\t\t\t    editor.getSession().setMode(\"ace/mode/sqlserver\");\r
\n\r
\n\t\t\t    switch (Terrasoft.SysValue.CURRENT_USER_CULTURE.value) {\r
\n\t\t\t    \tcase \"a5420246-0a8e-e111-84a3-00155d054c03\":\r
\n\t\t\t    \t\teditor.setValue(\r
\n\t\t\t    \t\t\t'--\
\n' +\r
\n\t\t\t\t\t\t\t'-- SQL QUERY CONSOLE\
\n' +\r
\n\t\t\t\t\t\t\t'--\
\n' +\r
\n\t\t\t\t\t\t\t'-- This page allows to perform SQL queries and perform sampling from the database.\
\n' +\r
\n\t\t\t\t\t\t\t'-- To execute the query, enter the query text in this field and execute the query,\
\n' +\r
\n\t\t\t\t\t\t\t'-- by clicking on \"Run\" or the keyboard shortcut Ctrl + Enter.\
\n' +\r
\n\t\t\t\t\t\t\t'-- When you run a SELECT statement, under this field will display the execution\
\n' +\r
\n\t\t\t\t\t\t\t'-- results in the form of tables with sorting by columns.\
\n' +\r
\n\t\t\t\t\t\t\t'-- When the INSERT, UPDATE, DELETE on a given field the number of entries that have\
\n' +\r
\n\t\t\t\t\t\t\t'-- been added/modified/deleted by data operators (ROWS AFFECTED) will be displayed.\
\n' +\r
\n\t\t\t\t\t\t\t'--\
\n');\r
\n\t\t\t    \t\tbreak;\r
\n\t\t\t    \tcase \"1a778e3f-0a8e-e111-84a3-00155d054c03\":\r
\n\t\t\t    \t\teditor.setValue(\r
\n\t\t\t\t\t    \t'--\
\n' +\r
\n\t\t\t\t\t\t\t'-- КОНСОЛЬ SQL ЗАПРОСОВ\
\n' +\r
\n\t\t\t\t\t\t\t'--\
\n' +\r
\n\t\t\t\t\t\t\t'-- Данная страница позволяет выполнять SQL запросы и выполнять выборки из базы данных.\
\n' +\r
\n\t\t\t\t\t\t\t'-- Для выполнения запроса введите текст запроса в данное поле и выполните запрос,\
\n' +\r
\n\t\t\t\t\t\t\t'-- нажав на \"Выполнить\", либо сочетанием клавиш Ctrl+Enter.\
\n' +\r
\n\t\t\t\t\t\t\t'-- При выполнении оператора SELECT, под данным полем будут отображены результаты\
\n' +\r
\n\t\t\t\t\t\t\t'-- выполнения в виде таблиц с возможностью сортировки по столбцам.\
\n' +\r
\n\t\t\t\t\t\t\t'-- При выполнении операторов INSERT, UPDATE, DELETE над данным полем будет отображено\
\n' +\r
\n\t\t\t\t\t\t\t'-- количество записей, добавленных/измененных/удаленных с помощью данных операторов (ROWS AFFECTED).\
\n' +\r
\n\t\t\t\t\t\t\t'--\
\n');\r
\n\t\t\t    \tdefault:\r
\n\t\t\t    \t\t// code\r
\n\t\t\t    }\r
\n\t\t\t\teditor.focus();\r
\n\t            this.viewModel.init();\r
\n            },\r
\n\r
\n\t\t\t/**\r
\n\t\t\t * Возвращает Название операции доступ на которую должен быть у пользователя для использования раздела или\r
\n\t\t\t * страницы\r
\n\t\t\t * @protected\r
\n\t\t\t * @virtual\r
\n\t\t\t * @return {String|null} Название операции.\r
\n\t\t\t */\r
\n\t\t\tgetSecurityOperationName: function() {\r
\n\t\t\t\treturn \"CanUseSqlConsole\";\r
\n\t\t\t},\r
\n\r
\n\t\t\t/**\r
\n\t\t\t * Устанавливает результат проверки возможности выполнения администрируемой операции.\r
\n\t\t\t * @protected\r
\n\t\t\t * @virtual\r
\n\t\t\t * @param {String} operationName Имя администрируемой операции.\r
\n\t\t\t * @param {Boolean} result Результат проверки возможности выполнения администрируемой операции.\r
\n\t\t\t */\r
\n\t\t\tsetCanExecuteOperationResult: Terrasoft.emptyFn,\r
\n\r
\n            /**\r
\n             * Заменяет последний элемент в цепочке состояний, если его идентификатор модуля отличается от текущего\r
\n             * @protected\r
\n             * @virtual\r
\n             */\r
\n            initHistoryState: function () {\r
\n                var sandbox = this.sandbox;\r
\n                var state = sandbox.publish(\"GetHistoryState\");\r
\n                var currentHash = state.hash;\r
\n                var currentState = state.state || {};\r
\n                if (currentState.moduleId === sandbox.id) {\r
\n                    return;\r
\n                }\r
\n                var newState = this.prepareHistorySate(currentState);\r
\n                sandbox.publish(\"ReplaceHistoryState\", {\r
\n                    stateObj: newState,\r
\n                    pageTitle: null,\r
\n                    hash: currentHash.historyState,\r
\n                    silent: true\r
\n                });\r
\n            },\r
\n\r
\n            /**\r
\n             * Подготавливает новое состояние страницы\r
\n             * @protected\r
\n             * @virtual\r
\n             * @return {Object} Возвращает новое состояние страницы\r
\n             */\r
\n            prepareHistorySate: function (currentState) {\r
\n                var newState = this.Terrasoft.deepClone(currentState);\r
\n                newState.moduleId = this.sandbox.id;\r
\n                return newState;\r
\n            },\r
\n\r
\n            /**\r
\n             * Очищает все подписки на события и уничтожает объект.\r
\n             * @overridden\r
\n             * @param {Object} config Параметры уничтожения модуля\r
\n             */\r
\n            destroy: function (config) {\r
\n                if (config.keepAlive !== true) {\r
\n                    if (this.viewModel) {\r
\n                        this.viewModel.destroy();\r
\n                        this.viewModel = null;\r
\n                    }\r
\n                    this.callParent(arguments);\r
\n                }\r
\n            }\r
\n        });\r
\n    });\r
\n",
  "MetaData": "{\r
\n  \"MetaData\": {\r
\n    \"Schema\": {\r
\n      \"ManagerName\": \"ClientUnitSchemaManager\",\r
\n      \"UId\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n      \"A2\": \"SqlConsoleModule\",\r
\n      \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\",\r
\n      \"B1\": [],\r
\n      \"B2\": [\r
\n        {\r
\n          \"UId\": \"dc0a435c-e41d-48d5-b2ba-e6fe5e11c57f\",\r
\n          \"A2\": \"ExecuteButton\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"9d6f6c44-552f-468e-b3aa-9b291d0cd729\",\r
\n          \"A2\": \"ExecuteButtonTip\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"693ea18f-1f02-4188-9d83-eb36aadc50f5\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"5707d805-f6b7-43e1-ba8a-797eab6b1a0b\",\r
\n          \"A2\": \"CloseButton\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"71a707d7-e944-4c5d-9030-16c4849e94c5\",\r
\n          \"A2\": \"ClearButton\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"ddcd4706-15d8-48ea-9159-28059916c95d\",\r
\n          \"A2\": \"ClearButtonTip\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"693ea18f-1f02-4188-9d83-eb36aadc50f5\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"f422ff0d-a268-4838-b684-b3ec8bf96c3d\",\r
\n          \"A2\": \"ExportToCsvButton\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"56f17b88-06c5-46be-b774-74fa815bf1c2\",\r
\n          \"A2\": \"ExportToCsvButtonTip\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"693ea18f-1f02-4188-9d83-eb36aadc50f5\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"5221d1b8-c7ba-4c3d-9735-39ade084f88b\",\r
\n          \"A2\": \"AccessError\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"c8ea33d8-808d-431c-977b-e20a5b9f5010\",\r
\n          \"A2\": \"HeaderCaption\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"a8248fb5-cc61-4880-a948-6fefab6b2b52\",\r
\n          \"A2\": \"QueryTimeLabelCaptionPrefix\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"a61befe5-be2e-4267-8e3f-36df34ba26a6\",\r
\n          \"A2\": \"QueryTimeLabelCaptionPostfix\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"eae7592c-4777-4032-b3c1-9a0e546b9e6a\",\r
\n          \"A2\": \"DataTableEmptyTable\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"9e566c35-d954-4afd-9772-418930dfc117\",\r
\n          \"A2\": \"DataTableInfo\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"a0edbb04-869c-4e6c-be88-67933fccb34d\",\r
\n          \"A2\": \"DataTableInfoEmpty\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"0d492cc7-4237-48b1-8888-b9dd37c60a0c\",\r
\n          \"A2\": \"DataTableInfoFiltered\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"0b7179ba-c152-4d05-8ae5-4870e4e01ed2\",\r
\n          \"A2\": \"DataTableLengthMenu\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"54ec9b40-6d96-403c-b513-290d61851d88\",\r
\n          \"A2\": \"DataTableLoadingRecords\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"8896c5ae-f548-4125-b710-f3a888af65a2\",\r
\n          \"A2\": \"DataTableProcessing\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"f729a21f-dc1b-4f60-99fd-ea06f8323f61\",\r
\n          \"A2\": \"DataTableSearch\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"beac7fdf-cdcb-43a3-bf07-770bb7514a11\",\r
\n          \"A2\": \"DataTableZeroRecords\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"1572a716-15f5-4da3-9c92-784f2eedecf9\",\r
\n          \"A2\": \"DataTablePaginateNext\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"fe274120-8dcd-4675-bd69-c7fb2382ff23\",\r
\n          \"A2\": \"DataTablePaginatePrevious\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"7569f5e8-b2aa-4914-b238-d87d4553e77a\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"1babd933-5a94-4672-acaf-bbb513b8063c\",\r
\n          \"A2\": \"ShowQueryLogButton\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"cbeca07e-df56-4e1a-8327-7253d9586b43\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"3c4916b1-12ef-4401-acb9-5946ba9ec3c9\",\r
\n          \"A2\": \"ShowQueryLogButtonTip\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"693ea18f-1f02-4188-9d83-eb36aadc50f5\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"6319a5b9-8771-4313-8867-e497b55e3eeb\",\r
\n          \"A2\": \"SaveSqlButton\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"693ea18f-1f02-4188-9d83-eb36aadc50f5\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"6f0594f7-7ec5-4dd1-864d-61b1929b879a\",\r
\n          \"A2\": \"SaveSqlButtonTip\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"693ea18f-1f02-4188-9d83-eb36aadc50f5\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"bf63ffbd-17cd-411e-a3ea-5801722c5d5d\",\r
\n          \"A2\": \"CloseButtonTip\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A5\": \"693ea18f-1f02-4188-9d83-eb36aadc50f5\"\r
\n        }\r
\n      ],\r
\n      \"B3\": [],\r
\n      \"B6\": \"4887c1a6-978a-4761-8929-94353166997c\",\r
\n      \"B8\": \"7.8.4.1572\",\r
\n      \"HD1\": \"50e3acc0-26fc-4237-a095-849a1d534bd3\",\r
\n      \"HD4\": 1,\r
\n      \"HD6\": \"null\",\r
\n      \"HD5\": [\r
\n        {\r
\n          \"UId\": \"87cddbbc-43ea-40de-9955-6f286ef6c31c\",\r
\n          \"A2\": \"AceCodeEditor\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HW1\": \"8ed40e79-ea15-418d-abee-5809c25d3c6d\",\r
\n          \"HW2\": \"ClientUnitSchemaManager\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"e985a786-e1bf-4fe7-b3e7-07f9f5e3ce83\",\r
\n          \"A2\": \"JQueryDataTables\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HW1\": \"1936fd6e-41db-4274-97a3-c801b620b439\",\r
\n          \"HW2\": \"ClientUnitSchemaManager\"\r
\n        }\r
\n      ],\r
\n      \"HD7\": [\r
\n        {\r
\n          \"UId\": \"ec22bf06-4c34-428f-b010-104ec975dd81\",\r
\n          \"A2\": \"BackHistoryState\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HX1\": 1\r
\n        },\r
\n        {\r
\n          \"UId\": \"f9377aae-f65f-4bc6-8434-cb5c4f624cf7\",\r
\n          \"A2\": \"ChangeHeaderCaption\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HX1\": 1,\r
\n          \"HX2\": 1\r
\n        },\r
\n        {\r
\n          \"UId\": \"9e0eb378-4cf4-439f-b99b-3027d1d5866e\",\r
\n          \"A2\": \"GetHistoryState\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HX1\": 1,\r
\n          \"HX2\": 1\r
\n        },\r
\n        {\r
\n          \"UId\": \"9400355b-e525-40e4-ae94-58c3cc85ca5f\",\r
\n          \"A2\": \"InitContextHelp\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HX1\": 1,\r
\n          \"HX2\": 1\r
\n        },\r
\n        {\r
\n          \"UId\": \"9b5e8afc-21b5-4edf-b7a9-9545e649e454\",\r
\n          \"A2\": \"InitDataViews\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HX1\": 1,\r
\n          \"HX2\": 1\r
\n        },\r
\n        {\r
\n          \"UId\": \"4383ea72-2a3c-44f0-ac31-dca2862238cf\",\r
\n          \"A2\": \"NeedHeaderCaption\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\"\r
\n        },\r
\n        {\r
\n          \"UId\": \"46fd9531-c732-4058-9060-44f138aabab0\",\r
\n          \"A2\": \"ReplaceHistoryState\",\r
\n          \"A3\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"A4\": \"6783fcb0-748b-441e-a02f-0e0adde4fd93\",\r
\n          \"HX1\": 1,\r
\n          \"HX2\": 1\r
\n        }\r
\n      ],\r
\n      \"HD8\": [],\r
\n      \"HD11\": []\r
\n    }\r
\n  }\r
\n}",
  "LocalizableValues": [
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "Caption",
      "Value": "SqlConsoleModule",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.AccessError.Value",
      "Value": "Текущий пользователь не имеет прав для работы с консолью SQL запросов!",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ClearButtonTip.Value",
      "Value": "Очистить (Ctrl+L)",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ClearButton.Value",
      "Value": "Очистить",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.CloseButtonTip.Value",
      "Value": "Закрыть SQL console",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.CloseButton.Value",
      "Value": "Закрыть",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableInfo.Caption",
      "Value": "Сообщение пользователю 1",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableInfoEmpty.Value",
      "Value": "Показаны 0 - 0 из 0 записей",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableInfoFiltered.Value",
      "Value": "(отфильтрованы из _MAX_ записей)",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableInfo.Value",
      "Value": "Показаны _START_ - _END_ из _TOTAL_ записей",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableLengthMenu.Value",
      "Value": "Показывать _MENU_ записей",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableLoadingRecords.Value",
      "Value": "Загрузка...",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTablePaginateNext.Value",
      "Value": "Следующая",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTablePaginatePrevious.Value",
      "Value": "Предыдущая",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableProcessing.Value",
      "Value": "Обработка...",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableSearch.Value",
      "Value": "Поиск:",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableZeroRecords.Value",
      "Value": "Ни одна запись не найдена",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExecuteButtonTip.Value",
      "Value": "Выполнить скрипт (Ctrl+Enter)",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExecuteButton.Value",
      "Value": "Выполнить",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExportToCsvButtonTip.Value",
      "Value": "Экспорт в CSV (Ctrl+Shift+S)",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExportToCsvButton.Value",
      "Value": "Экспорт в CSV",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.HeaderCaption.Caption",
      "Value": "HeaderCaption",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.HeaderCaption.Value",
      "Value": "Консоль SQL",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.QueryTimeLabelCaptionPostfix.Value",
      "Value": " сек",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.QueryTimeLabelCaptionPrefix.Value",
      "Value": "Время выполнения запроса: ",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.SaveSqlButtonTip.Value",
      "Value": "Сохранить SQL скрипт (Ctrl+S)",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.SaveSqlButton.Value",
      "Value": "Сохранить SQL",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ShowQueryLogButtonTip.Value",
      "Value": "Показать лог запросов (Ctrl+Shift+H)",
      "ImageData": ""
    },
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ShowQueryLogButton.Value",
      "Value": "Показать лог запросов",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "Caption",
      "Value": "SqlConsoleModule",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.AccessError.Value",
      "Value": "The current user does not have rights to work with the SQL query console!",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ClearButtonTip.Value",
      "Value": "Clear (Ctrl+L)",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ClearButton.Value",
      "Value": "Clear",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.CloseButtonTip.Value",
      "Value": "Close SQL console",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.CloseButton.Value",
      "Value": "Close",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableEmptyTable.Value",
      "Value": "No data available in table",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableInfoEmpty.Value",
      "Value": "Showing 0 to 0 of 0 entries",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableInfoFiltered.Value",
      "Value": "(filtered from _MAX_ total entries)",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableInfo.Value",
      "Value": "Showing _START_ to _END_ of _TOTAL_ entries",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableLengthMenu.Value",
      "Value": "Show _MENU_ entries",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableLoadingRecords.Value",
      "Value": "Loading...",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTablePaginateNext.Value",
      "Value": "Next",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTablePaginatePrevious.Value",
      "Value": "Previous",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableProcessing.Value",
      "Value": "Processing...",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableSearch.Value",
      "Value": "Search:",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.DataTableZeroRecords.Value",
      "Value": "No matching records found",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExecuteButtonTip.Value",
      "Value": "Execute script (Ctrl+Enter)",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExecuteButton.Value",
      "Value": "Execute",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExportToCsvButtonTip.Value",
      "Value": "Export to CSV (Ctrl+Shift+S)",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ExportToCsvButton.Value",
      "Value": "Export to CSV",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.HeaderCaption.Value",
      "Value": "SQL console",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.QueryTimeLabelCaptionPostfix.Value",
      "Value": " sec",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.QueryTimeLabelCaptionPrefix.Value",
      "Value": "Query execution time: ",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.SaveSqlButtonTip.Value",
      "Value": "Save SQL script (Ctrl+S)",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.SaveSqlButton.Value",
      "Value": "Save SQL",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ShowQueryLogButtonTip.Value",
      "Value": "Show query log (Ctrl+Shift+H)",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "LocalizableStrings.ShowQueryLogButton.Value",
      "Value": "Show query log",
      "ImageData": ""
    }
  ],
  "Properties": [
    {
      "Name": "CreatedInVersion",
      "Value": "7.8.4.1572"
    },
    {
      "Name": "Group",
      "Value": ""
    },
    {
      "Name": "SchemaType",
      "Value": "Module"
    }
  ]
}