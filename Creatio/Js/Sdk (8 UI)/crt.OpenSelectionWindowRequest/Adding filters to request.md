```js title="Preconditions"
```

```js title="Content"
{
	request: "crt.OpenSelectionWindowRequest",
	handler: async function(request, next) {
		if (request.itemsAttributeName === "BnzDocumentRegistratorDS_Contact_4pti1hk_List") {
			this.initObjectSchemaFilter(request);
		}
		await next?.handle(request);
	},
	initObjectSchemaFilter: function(request) {
		var filters = Ext.create("Terrasoft.FilterGroup");
		var account = request.$context.attributes.BnzDocumentRegistratorDS_DTEKAccountORD_oe8yo8z 
			&& request.$context.attributes.BnzDocumentRegistratorDS_DTEKAccountORD_oe8yo8z.value || Terrasoft.GUID_EMPTY;
		var notExistsFilter = Terrasoft.createNotExistsFilter("[BnzDocumentRegistrator:Contact].Id");
		notExistsFilter.subFilters.addItem(Terrasoft.createColumnFilterWithParameter(
			Terrasoft.ComparisonType.EQUAL, "DTEKAccountORD", account)
		);
		filters.addItem(notExistsFilter);

		request.filtersConfig.filterAttributes.push({
			name: 'UserFilter',
			loadOnChange: false
		});
		request.filtersConfig.attributesConfig.UserFilter = {
			value: filters.serialize()
		};
	}
}
```