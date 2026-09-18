{
  "Version": "8.3.4.2753",
  "UId": "495e7ae4-d007-404e-aefa-ead08bcbe6e5",
  "ManagerName": "SourceCodeSchemaManager",
  "Name": "SqlConsoleService",
  "Caption": "SqlConsoleService",
  "ExtendParent": false,
  "DenyExtending": false,
  "Description": "",
  "SourceCode": "namespace Terrasoft.Configuration.SqlConsoleService\r
\n{\r
\n\tusing System.CodeDom.Compiler;\r
\n\tusing System.ServiceModel;\r
\n\tusing System.ServiceModel.Web;\r
\n\tusing System.ServiceModel.Activation;\r
\n\tusing System.Runtime.Serialization;\r
\n\tusing System.Web;\r
\n\tusing Terrasoft.Common;\r
\n\tusing Terrasoft.Core;\r
\n\tusing Terrasoft.Core.DB;\r
\n\tusing Terrasoft.Core.Entities;\r
\n\tusing Terrasoft.Core.Store;\r
\n\tusing System;\r
\n\tusing System.Data;\r
\n\tusing System.Collections.Generic;\r
\n\tusing System.Linq;\r
\n\tusing System.Text;\r
\n\tusing Newtonsoft.Json.Linq;\r
\n\r
\n\t[ServiceContract]\r
\n\t[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Required)]\r
\n\tpublic class SqlConsoleService {\r
\n\t\t[OperationContract]\r
\n\t\t[WebInvoke(Method = \"POST\", UriTemplate = \"ExecuteSqlScript\", BodyStyle = WebMessageBodyStyle.Wrapped,\r
\n\t\t\tRequestFormat = WebMessageFormat.Json, ResponseFormat = WebMessageFormat.Json)]\r
\n\t\tpublic ExecuteSqlResult ExecuteSqlScript(string sqlScript) {\r
\n\t\t\tExecuteSqlResult result = ExecuteSqlScript(sqlScript, true);\r
\n\t\t\treturn result;\r
\n\t\t}\r
\n\t\t\r
\n\t\t[OperationContract]\r
\n\t\t[WebInvoke(Method = \"POST\", UriTemplate = \"GetSqlConsoleLog\", BodyStyle = WebMessageBodyStyle.Wrapped,\r
\n\t\t\tRequestFormat = WebMessageFormat.Json, ResponseFormat = WebMessageFormat.Json)]\r
\n\t\tpublic ExecuteSqlResult GetSqlConsoleLog() {\r
\n\t\t\tvar userConnection = (UserConnection)HttpContext.Current.Session[\"UserConnection\"];\r
\n\t\t\tvar select = new Select(userConnection).Top(1000)\r
\n\t\t\t\t\t.Column(\"CreatedOn\")\r
\n\t\t\t\t\t.Column(\"ContactId\")\r
\n\t\t\t\t\t.Column(\"IpAdress\")\r
\n\t\t\t\t\t.Column(\"QueryText\")\r
\n\t\t\t\t\t.Column(\"CompletedOn\")\r
\n\t\t\t\t.From(\"SqlConsoleLog\")\r
\n\t\t\t\t.OrderByDesc(\"CreatedOn\") as Select;\r
\n\t\t\tExecuteSqlResult result = ExecuteSqlScript(select.GetSqlText(), false);\r
\n\t\t\treturn result;\r
\n\t\t}\r
\n\t\t\r
\n\t\tprivate ExecuteSqlResult ExecuteSqlScript(string sqlScript, bool logging) {\r
\n\t\t\tExecuteSqlResult result = new ExecuteSqlResult();\r
\n\t\t\tUserConnection userConnection = null;\r
\n\t\t\t\r
\n\t\t\ttry {\r
\n\t\t\t\tuserConnection = (UserConnection)HttpContext.Current.Session[\"UserConnection\"];\r
\n\t\t\t\tuserConnection.DBSecurityEngine.CheckCanExecuteOperation(\"CanUseSqlConsole\");\r
\n\t\t\t} catch (System.Security.SecurityException exc) {\r
\n\t\t\t\tresult.SecurityError = true;\r
\n\t\t\t\treturn result;\r
\n\t\t\t}\r
\n\t\t\t\r
\n\t\t\tList<QueryResult> queryResults = new List<QueryResult>();\r
\n\t\t\tint rowsAffected = 0;\r
\n\t\t\t\r
\n\t\t\ttry {\r
\n\t\t\t\tvar resultQuery = new CustomQuery(userConnection, sqlScript);\r
\n\t\t\t\t\r
\n\t\t\t\tGuid logRecordId = Guid.NewGuid();\r
\n\t\t\t\tif (logging) \r
\n\t\t\t\t{\r
\n\t\t\t\t\tLogQuery(sqlScript, logRecordId, userConnection);\r
\n\t\t\t\t}\r
\n\t\t\t\tusing (DBExecutor dbExecutor = userConnection.EnsureDBConnection()) {\r
\n\t\t\t\t\tusing(var dr = resultQuery.ExecuteReader(dbExecutor)) {\r
\n\t\t\t\t\t\tDataTable dataTable;\r
\n\t\t\t\t\t\twhile (true) {\r
\n\t\t\t\t\t\t\tvar queryResult = new QueryResult();\r
\n\t\t\t\t\t\t\tdataTable = new DataTable();\r
\n\t\t\t\t\t\t\tdataTable.Load(dr);\r
\n\t\t\t\t\t\t\t\r
\n\t\t\t\t\t\t\tqueryResult.Columns = new List<string>();\r
\n\t\t\t\t\t\t\tqueryResult.Columns.AddRange(dataTable.Columns.Cast<DataColumn>().Select(column => column.ColumnName));\r
\n\t\t\t\t\t\t\t\r
\n\t\t\t\t\t\t\tif (queryResult.Columns.Count == 0) {\r
\n\t\t\t\t\t\t\t\trowsAffected = (dr.RecordsAffected > 0) ? dr.RecordsAffected : 0;\r
\n\t\t\t\t\t\t\t\tbreak;\r
\n\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\t\r
\n\t\t\t\t\t\t\tqueryResult.Rows = new List<List<string>>();\r
\n\t\t\t\t\t\t\tforeach (DataRow row in dataTable.Rows)\r
\n\t\t\t\t\t\t\t{\r
\n\t\t\t\t\t\t\t\tvar r = new List<string>();\r
\n\t\t\t\t\t\t\t\tr.AddRange(row.ItemArray.Select(field => (field == DBNull.Value) ? \"NULL\" : field.ToString()));\r
\n\t\t\t\t\t\t\t\tqueryResult.Rows.Add(r);\r
\n\t\t\t\t\t\t\t}\r
\n\t\t\t\t\t\t\tqueryResults.Add(queryResult);\r
\n\t\t\t\t\t\t}\r
\n\t\t\t\t\t\tif (logging) \r
\n\t\t\t\t\t\t{\r
\n\t\t\t\t\t\t\tUpdateLogQuery(logRecordId, userConnection);\r
\n\t\t\t\t\t\t}\r
\n\t\t\t\t\t}\r
\n\t\t\t\t}\r
\n\t\t\t} catch (System.Data.SqlClient.SqlException exc) {\r
\n\t\t\t\tif (exc.Errors != null) {\r
\n\t\t\t\t\tStringBuilder sb = new StringBuilder();\r
\n\t\t\t\t\tfor (var i = 0; i < exc.Errors.Count; i++) {\r
\n\t\t\t\t\t\tvar sqlError = exc.Errors[i];\r
\n\t\t\t\t\t\tsb.AppendLine(String.Format(\"Msg {0}, Level {1}, State {2}, Line {3}\
\n{4}\", sqlError.Number, sqlError.Class, sqlError.State, sqlError.LineNumber, sqlError.Message));\r
\n\t\t\t\t\t}\r
\n\t\t\t\t\tresult.ErrorMessage = sb.ToString();\r
\n\t\t\t\t\treturn result;\r
\n\t\t\t\t} else {\r
\n\t\t\t\t\tresult.ErrorMessage = exc.ToString();\r
\n\t\t\t\t\treturn result;\r
\n\t\t\t\t}\r
\n\t\t\t} catch (Exception exc) {\r
\n\t\t\t\tresult.ErrorMessage = exc.ToString();\r
\n\t\t\t\treturn result;\r
\n\t\t\t}\r
\n\t\t\t\r
\n\t\t\tresult.QueryResults = queryResults;\r
\n\t\t\tresult.RowsAffected = rowsAffected;\r
\n\t\t\tresult.Success = true;\r
\n\t\t\treturn result;\r
\n\t\t}\r
\n\t\t\r
\n\t\tprivate void LogQuery(string text, Guid logRecordId, UserConnection userConnection) {\r
\n\t\t\tvar insert = new Insert(userConnection).Into(\"SqlConsoleLog\")\r
\n\t\t\t\t.Set(\"Id\", Column.Parameter(logRecordId))\r
\n\t\t\t\t.Set(\"CreatedOn\", Column.Parameter(DateTime.UtcNow))\r
\n\t\t\t\t.Set(\"ModifiedOn\", Column.Parameter(DateTime.UtcNow))\r
\n\t\t\t\t.Set(\"ContactId\", Column.Parameter(userConnection.CurrentUser.ContactId))\r
\n\t\t\t\t.Set(\"IpAdress\", Column.Parameter(userConnection.CurrentUser.ClientIP))\r
\n\t\t\t\t.Set(\"QueryText\", Column.Parameter(text));\r
\n\t\t\tinsert.Execute();\r
\n\t\t}\r
\n\t\t\r
\n\t\tprivate void UpdateLogQuery(Guid logRecordId, UserConnection userConnection) {\r
\n\t\t\tUpdate update = new Update(userConnection, \"SqlConsoleLog\");\r
\n\t\t\t\tupdate.Set(\"CompletedOn\", Column.Parameter(DateTime.UtcNow));\r
\n\t\t\t\tupdate.Where(\"Id\").IsEqual(Column.Parameter(logRecordId));\r
\n\t\t\tupdate.Execute();\r
\n\t\t}\r
\n\t\t\r
\n\t\t[DataContract(Namespace = \"http://Terrasoft.WebApp.Service/\")]\r
\n\t\tpublic class QueryResult\r
\n\t\t{\r
\n\t\t\t[DataMember]\r
\n\t\t\tpublic List<string> Columns {\r
\n\t\t\t\tget;\r
\n\t\t\t\tset;\r
\n\t\t\t}\r
\n\r
\n\t\t\t[DataMember]\r
\n\t\t\tpublic List<List<string>> Rows {\r
\n\t\t\t\tget;\r
\n\t\t\t\tset;\r
\n\t\t\t}\r
\n\t\t}\r
\n\t\t\r
\n\t\t[DataContract(Namespace = \"http://Terrasoft.WebApp.Service/\")]\r
\n\t\tpublic class ExecuteSqlResult\r
\n\t\t{\r
\n\t\t\t[DataMember]\r
\n\t\t\tpublic List<QueryResult> QueryResults {\r
\n\t\t\t\tget;\r
\n\t\t\t\tset;\r
\n\t\t\t}\r
\n\r
\n\t\t\t[DataMember]\r
\n\t\t\tpublic int RowsAffected {\r
\n\t\t\t\tget;\r
\n\t\t\t\tset;\r
\n\t\t\t}\r
\n\t\t\t\r
\n\t\t\t[DataMember]\r
\n\t\t\tpublic string ErrorMessage {\r
\n\t\t\t\tget;\r
\n\t\t\t\tset;\r
\n\t\t\t}\r
\n\t\t\t\r
\n\t\t\t[DataMember]\r
\n\t\t\tpublic bool SecurityError {\r
\n\t\t\t\tget;\r
\n\t\t\t\tset;\r
\n\t\t\t}\r
\n\t\t\t\r
\n\t\t\t[DataMember]\r
\n\t\t\tpublic bool Success {\r
\n\t\t\t\tget;\r
\n\t\t\t\tset;\r
\n\t\t\t}\r
\n\t\t}\r
\n\t}\r
\n}",
  "MetaData": "{\r
\n  \"MetaData\": {\r
\n    \"Schema\": {\r
\n      \"ManagerName\": \"SourceCodeSchemaManager\",\r
\n      \"UId\": \"495e7ae4-d007-404e-aefa-ead08bcbe6e5\",\r
\n      \"A2\": \"SqlConsoleService\",\r
\n      \"A5\": \"0874aaa8-6239-4ea7-acdc-f7c3b1e649ce\",\r
\n      \"B1\": [],\r
\n      \"B2\": [],\r
\n      \"B3\": [],\r
\n      \"B6\": \"4887c1a6-978a-4761-8929-94353166997c\",\r
\n      \"B8\": \"7.7.0.2223\",\r
\n      \"HD1\": \"50e3acc0-26fc-4237-a095-849a1d534bd3\"\r
\n    }\r
\n  }\r
\n}",
  "LocalizableValues": [
    {
      "Culture": "ru-RU",
      "ResourceType": "String",
      "Key": "Caption",
      "Value": "SqlConsoleService",
      "ImageData": ""
    },
    {
      "Culture": "en-US",
      "ResourceType": "String",
      "Key": "Caption",
      "Value": "SqlConsoleService",
      "ImageData": ""
    }
  ],
  "Properties": [
    {
      "Name": "CreatedInVersion",
      "Value": "7.7.0.2223"
    }
  ]
}