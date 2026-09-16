
[[#PreConditions]]
[[#ViewConfigDiff]]
[[#Items]]


## PreConditions

```json title="Preconditions"
//-----viewModelConfigDiff-----
"DataGrid_wak7xqj": {
	"isCollection": true,
	"modelConfig": {
		"path": "DataGrid_wak7xqjDS",
		"filterAttributes": [...]
	},
	"viewModelConfig": {
		"attributes": {
			"DataGrid_wak7xqjDS_Id": {
				"modelConfig": {
					"path": "DataGrid_wak7xqjDS.Id"
				}
			},
			...
		}
	}
},

//-----modelConfigDiff-----
{
	"operation": "merge",
	"path": [],
	"values": {
		"dataSources": {
			"DataGrid_wak7xqjDS": {
				"type": "crt.EntityDataSource",
				"scope": "viewElement",
				"config": {
					"entitySchemaName": "SomeEntitySchema",
					"attributes": {
						"Id": {
							"path": "Id"
						},
						...
					}
				}
			}
		}
	}
}
```



> [!NOTE] Attention
> rowToolbarItems.{item}.clicked.params **{Items}** is need to = "items" grid.values of your grid, ex.

## ViewConfigDiff

```json title="Example"
//Preconditions
viewConfigDiff.{SomeDataGrid}.values.items = "$DataGrid_wak7xqj"

//Example
viewConfigDiff.{SomeDataGrid}.values.rowToolbarItems.{item}.clicked.params:
{
	"itemsAttributeName": "DataGrid_wak7xqj", // {grid items}
	"recordId": "$DataGrid_wak7xqj.DataGrid_wak7xqjDS_Id" // ${grid items}.[viewModelConfigDiff.{grid items}.viewModelConfig.attributes.{column}]

}
```

> [!NOTE] P.S.
> For List_Page DataTable default items data source is (main grid of list page)
> //-----viewConfigDiff-----
> ***DataTable.values.items = "$Items"***

## Items


```json title="Content"
//-----viewConfigDiff-----
{
	"operation": "insert",
	"name": "DataGrid_wak7xqj",
	"values": {
		"type": "crt.DataGrid",
		"columns": [...],
		"features": {...},
		//default condition
		"rowToolbarItems": [
			{
				"type": "crt.MenuItem",
				"caption": "DataGrid.RowToolbar.Open",
				"icon": "edit-row-action",
				"disabled": "$Items.PrimaryModelMode | crt.IsEqual : 'create'",
				"clicked": {
					"request": "crt.UpdateRecordRequest",
					"params": {
						"itemsAttributeName": "DataGrid_wak7xqj", //Items {grid items}
						"recordId": "$DataGrid_wak7xqj.DataGrid_wak7xqjDS_Id" //$Items ${grid items}.{viewModelConfigDiff.{grid items}.viewModelConfig.attributes.{column}}
					}
				}
			},
			{
				"type": "crt.MenuItem",
				"caption": "DataGrid.RowToolbar.Copy",
				"icon": "copy-row-action",
				"clicked": {
					"request": "crt.RunCopyCardProcess",
					"params": {
						"itemsAttributeName": "Items",
						"recordId": "$Items.DataGrid_wak7xqjDS_Id"
					}
				}
			},
			{
				"type": "crt.MenuItem",
				"caption": "DataGrid.RowToolbar.Delete",
				"icon": "delete-row-action",
				"clicked": {
					"request": "crt.DeleteRecordRequest",
					"params": {
						"itemsAttributeName": "Items",
						"recordId": "$Items.DataGrid_wak7xqjDS_Id"
					}
				}
			}
		],
		"items": "$DataGrid_wak7xqj",
		"layoutConfig": {},
		"classes": [
			"section-data-grid"
		],
		"primaryColumnName": "DataGrid_wak7xqjDS_Id",
		"visible": true,
		"fitContent": true,
		"selectionState": "$DataGrid_wak7xqj_SelectionState",
		"_selectionOptions": {
			"attribute": "DataGrid_wak7xqj_SelectionState"
		}
	},
	"parentName": "FlexContainer_srbvktw",
	"propertyName": "items",
	"index": 0
},
```



[^1]: 
