```js title="Prerequirements"
@require modules:
	"ServiceHelper"

url = ServiceHelper.buildConfigurationUrl([Service],[Method]); // 1
	= 'rest/[Service]/[Method]'; // 2
	
var res = await httpClientService.post(url, [data])
```

```js title="Example"
const httpClientService = new sdk.HttpClientService();
const configEndpoint = ServiceHelper.buildConfigurationUrl("DocumentTemplatesService", "CreateFileByReport");
const configData = {
	fileEntitySchemaName: await this.FileEntitySchemaName,
	recordId: await this.MasterRecordId,
	reportId: await this.ReportId,
	parentColumnName: await this.ParentColumnName
};

var result = await httpClientService.post(configEndpoint, configData);

if (result && result.ok && result.body.CreateFileByReportResult) {
	this.CreatedFileId = result.body.CreateFileByReportResult;
}
```

> ```
> result.body.[Method]Result
> ```
> *\[Method\]* is method has been called by 2nd argument of *`post`* method

