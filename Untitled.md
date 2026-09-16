```js title="Prerequirements"
@require:
	"ServiceHelper"

url = ServiceHelper.buildConfigurationUrl([Service],[Method]);
var res = await httpClientService.post(url, [data])
OR
var res = await httpClientService.post([rawUrl],[data])
	| [rawUrl] = 'rest/[Service]/[Method]'
```