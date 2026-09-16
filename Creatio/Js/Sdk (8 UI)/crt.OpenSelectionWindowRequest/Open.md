```js title="Preconditions"
```

```js title="Content"
const selectionFilters = await pageMethods.getTemplateAccessLevelSelectionFilter(request);

request.$context.executeRequest({
	type: "crt.OpenSelectionWindowRequest",
	$context: request.$context,
	entitySchemaName: "WhdTemplateAccessLevel",
	filtersConfig: selectionFilters,
	features: {
		showDeactivatedRecords: false,
		select: {
			multiple: true,
			selectAll: false,
			resultType: "lookupValues"
		},
		create: {
			enabled: false
		}
	},
	afterClosed: async function(result) {
		if (!result || result.canceled) {
			return;
		}

		var values = await result?.getLookupValues();
		if (!values || values.length < 1) {
			return;
		}

		const templateAccessInSettingModel = await sdk.Model.create("WhdTemplateAccessLevelInConnectionSetting");
		values.forEach(unit => {
			templateAccessInSettingModel.insert({
				ConnectionSetting: request.$context.attributes.Id,
				TemplateAccessLevel: unit.value
			});
		});
	},
});
```