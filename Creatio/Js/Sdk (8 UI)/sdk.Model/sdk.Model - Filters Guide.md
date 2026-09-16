## Table of Contents

- [[#Creating a Model]]
- [[#Loading Records]]
- [[#Updating Records]]
- [[#FilterGroup]]
- [[#Comparison Filters]]
- [[#IN Filter]]
- [[#IS NULL Filter]]
- [[#EXISTS / NOT EXISTS Filter]]
- [[#Logical Operators (AND / OR)]]
- [[#Nested Filter Groups]]
- [[#Aggregate Columns (COUNT)]]
- [[#Fetch by Primary Key]]
- [[#Paging Options]]
- [[#Reverse Reference Path Syntax]]
- [[#Quick Reference Table]]

---

## Creating a Model

```js
const model = await sdk.Model.create("SchemaName");
```

Always `await` — model creation is async.

---
````tabsdown
tab: General params

```js
```

tab: Load
```js
const rows = await model.load({
	attributes: ["Id", "UsrName", "UsrProduct"],   // columns to recieve
	parameters: [
		{ type: sdk.ModelParameterType.Filter, value: filterGroup }
	],
	options: {}
});
```

`rows` is an array. Each element has the requested column names as properties:

```js
const id    = rows[0].Id;
const name  = rows[0].UsrName;
const value = rows[0].UsrProduct?.value;        // lookup → .value / .displayValue
```

tab: Update
```js
const model = await sdk.Model.create("UsrLegalDocumentParticipant");
const result = await model.update(
    { UsrEndDate: expDate },                      // fields to set
    [{ type: sdk.ModelParameterType.Filter, value: filterGroup }]
);
```

> Filter the rows to update exactly as you would for `load`.

tab: Delete
```js
```

````

---

## Updating Records



---

## FilterGroup

A `FilterGroup` is a container for one or more filter conditions joined by a logical operator (default **AND**).

```js
const filterGroup = new sdk.FilterGroup();
```

Add conditions with the methods described below, then pass the group to `model.load` or `model.update`.

---

## Comparison Filters

### Basic comparison

```js
filterGroup.addSchemaColumnFilterWithParameter(
    sdk.ComparisonType.Equal,
    "ColumnName",
    value
);
```

### All ComparisonType variants

| Constant                              | Meaning             |
| ------------------------------------- | ------------------- |
| `sdk.ComparisonType.Equal`            | `=`                 |
| `sdk.ComparisonType.Not_equal`        | `<>`                |
| `sdk.ComparisonType.Greater`          | `>`                 |
| `sdk.ComparisonType.Greater_or_equal` | `>=`                |
| `sdk.ComparisonType.Less`             | `<`                 |
| `sdk.ComparisonType.Less_or_equal`    | `<=`                |
| `sdk.ComparisonType.Exists`           | EXISTS subquery     |
| `sdk.ComparisonType.Not_exists`       | NOT EXISTS subquery |

### Examples

```js
// Equality
filterGroup.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Equal, "UsrAccount", accountId);

// Inequality
filterGroup.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Not_equal, "Id", currentId);

// Greater-than date
filterGroup.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Greater, "UsrEndDate", new Date());

// Greater-or-equal date
filterGroup.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Greater_or_equal, "UsrLineExpiry", new Date());

// Boolean
filterGroup.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Equal, "UsrIsDeleted", false);
filterGroup.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Equal, "UsrIsCreatedManually", true);

// GUID constant fallback (when value may be undefined)
filterGroup.addSchemaColumnFilterWithParameter(
    sdk.ComparisonType.Equal,
    "UsrAccount",
    usrAccountId || sdk.EMPTY_GUID
);

// Traversal through a related schema column
filterGroup.addSchemaColumnFilterWithParameter(
    sdk.ComparisonType.Equal,
    "UsrContact.UsrStatus",
    constants.ContactStatus.Current
);

filterGroup.addSchemaColumnFilterWithParameter(
    sdk.ComparisonType.Equal,
    "UsrProduct.UsrConsumptionBased",
    constants.YesNo.Yes
);
```

---

## IN Filter

Match a column against an **array** of values.

```js
filterGroup.addSchemaColumnInFilterWithParameters(
    sdk.ComparisonType.Equal,
    "UsrProduct",
    [productId1, productId2, productId3]
);
```

> The first argument must always be `sdk.ComparisonType.Equal` for IN filters.

**Examples:**

```js
// Filter billing lines whose product is in a dynamic list
filterGroup.addSchemaColumnInFilterWithParameters(
    sdk.ComparisonType.Equal,
    "UsrProduct",
    products          // string[]
);

// Filter legal document products by document IDs
filterGroup.addSchemaColumnInFilterWithParameters(
    sdk.ComparisonType.Equal,
    "UsrLegalDocument",
    legalDocumentIds  // string[]
);

// Using a reverse reference path (see section below)
filterGroup.addSchemaColumnInFilterWithParameters(
    sdk.ComparisonType.Equal,
    "[UsrLegalDocumentProduct:UsrProduct:UsrProduct].UsrLegalDocument",
    legalDocumentsIds
);
```

---

## IS NULL Filter

```js
filterGroup.addSchemaColumnIsNullFilter("UsrTerminationDate");
filterGroup.addSchemaColumnIsNullFilter("UsrEndDate");
filterGroup.addSchemaColumnIsNullFilter("UsrLineExpiry");
```

Commonly paired with a `>` check inside an **OR** group to express "null or in the future":

```js
const dateFilter = new sdk.FilterGroup();
dateFilter.logicalOperation = sdk.LogicalOperatorType.Or;
dateFilter.addSchemaColumnIsNullFilter("UsrTerminationDate");
dateFilter.addSchemaColumnFilterWithParameter(
    sdk.ComparisonType.Greater,
    "UsrTerminationDate",
    new Date()
);
parentGroup.add(dateFilter);
```

---

## EXISTS / NOT EXISTS Filter

Two ways to add an exists subquery:

### Option A – `addExistsFilter` (shorthand)

```js
const subFilters = new sdk.FilterGroup();
subFilters.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Equal, "UsrProduct", productId);

filterGroup.addExistsFilter(
    "[UsrLegalDocumentProduct:UsrLegalDocument:UsrLegalDocument].Id",
    subFilters
);
```

### Option B – `sdk.ExistsFilter` constructor (full control)

```js
const subFilter = new sdk.FilterGroup();
subFilter.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Equal, "UsrAccount", accountId);
subFilter.add(this.getActiveParticipantFilter());

const existsFilter = new sdk.ExistsFilter(
    new sdk.ColumnExpression({ columnPath: "[UsrLegalDocumentParticipant:UsrLegalDocument:UsrLegalDocument].Id" }),
    subFilter,
    sdk.ComparisonType.Exists          // or sdk.ComparisonType.Not_exists
);

filterGroup.add(existsFilter);
```

### NOT EXISTS

Replace `sdk.ComparisonType.Exists` with `sdk.ComparisonType.Not_exists`:

```js
const notExistsFilter = new sdk.ExistsFilter(
    new sdk.ColumnExpression({ columnPath: "[UsrLegalDocumentParticipant:UsrLegalDocument:UsrLegalDocument].Id" }),
    subFilters,
    sdk.ComparisonType.Not_exists
);

filterGroup.add(notExistsFilter);
```

### Nested EXISTS inside NOT EXISTS

```js
// Outer: NOT EXISTS on participants
const notExistsFilter = new sdk.ExistsFilter(
    new sdk.ColumnExpression({ columnPath: "[UsrLegalDocumentParticipant:UsrLegalDocument:UsrLegalDocument].Id" }),
    subFilters,
    sdk.ComparisonType.Not_exists
);

// Inner: EXISTS on billing lines – added into subFilters before passing above
const billingLineExists = new sdk.FilterGroup();
billingLineExists.addSchemaColumnInFilterWithParameters(sdk.ComparisonType.Equal, "UsrProduct", productIds);
billingLineExists.add(activeBillingLineFilter);
subFilters.addExistsFilter("[UsrBillingLine:UsrAccount:UsrAccount].Id", billingLineExists);
```

---

## Logical Operators (AND / OR)

Default logical operation for a `FilterGroup` is **AND**. Override to OR:

```js
const orGroup = new sdk.FilterGroup();
orGroup.logicalOperation = sdk.LogicalOperatorType.Or;

orGroup.addSchemaColumnIsNullFilter("UsrLineExpiry");
orGroup.addSchemaColumnFilterWithParameter(sdk.ComparisonType.Greater, "UsrLineExpiry", new Date());
```

| Constant | Behavior |
|---|---|
| *(not set)* | AND (default) |
| `sdk.LogicalOperatorType.Or` | OR |

---

## Nested Filter Groups

Combine AND and OR groups by composing them:

```js
// "IsDeleted = false AND (TerminationDate IS NULL OR TerminationDate > now)"
const isActiveFilter = new sdk.FilterGroup();                          // AND
isActiveFilter.addSchemaColumnFilterWithParameter(
    sdk.ComparisonType.Equal, "UsrIsDeleted", false);

const terminationDateFilter = new sdk.FilterGroup();                   // OR
terminationDateFilter.logicalOperation = sdk.LogicalOperatorType.Or;
terminationDateFilter.addSchemaColumnIsNullFilter("UsrTerminationDate");
terminationDateFilter.addSchemaColumnFilterWithParameter(
    sdk.ComparisonType.Greater, "UsrTerminationDate", new Date());

isActiveFilter.add(terminationDateFilter);                             // nest OR inside AND
```

Add a group with an optional string key:

```js
parentGroup.add(childGroup);           // no key
parentGroup.add(childGroup, "myKey"); // named key (useful for later removal)
```

---

## Aggregate Columns (COUNT)

Use a function-type column descriptor instead of a plain string in `attributes`:

```js
const countColumn = {
    type: "function",
    path: "Id",
    name: "IdCount",           // property name on the result object
    caption: "IdCountCaption",
    dataValueType: sdk.DataValueType.Integer,
    functionConfig: {
        aggregation: sdk.AggregationFunction.Count,
        type: "aggregation",
        aggregationEval: "distinct"    // COUNT DISTINCT
    }
};

const res = await model.load({
    attributes: [countColumn],
    parameters: [{ type: sdk.ModelParameterType.Filter, value: filterGroup }],
    options: {}
});

const count = res && res.length > 0 ? res[0].IdCount : 0;
```

> `sdk.AggregationFunction.Count` with `aggregationEval: "distinct"` produces `COUNT(DISTINCT Id)`.

---

## Fetch by Primary Key

Use `sdk.ModelParameterType.PrimaryColumnValue` instead of a filter group when fetching a single record by ID:

```js
const entities = await model.load({
    attributes: ["Id", "Name"],
    parameters: [
        {
            type: sdk.ModelParameterType.PrimaryColumnValue,
            value: entityId     // GUID string
        }
    ],
    options: {}
});
```

---

## Paging Options

Limit the number of rows returned:

```js
const res = await model.load({
    attributes: ["Id"],
    parameters: [{ type: sdk.ModelParameterType.Filter, value: filterGroup }],
    options: {
        pagingConfig: {
            rowCount: 1    // return at most 1 row
        }
    }
});
```

---

## Reverse Reference Path Syntax

Used in `addExistsFilter`, `addSchemaColumnInFilterWithParameters`, and `addSchemaColumnFilterWithParameter` to traverse reverse (detail) relations.

```
[ReferenceSchema:ReferenceSchemaColumn:MasterSchemaColumn].ColumnToFilter
```

| Segment | Meaning |
|---|---|
| `ReferenceSchema` | The schema that holds the foreign key |
| `ReferenceSchemaColumn` | The FK column **on ReferenceSchema** pointing to the master |
| `MasterSchemaColumn` | The column on the **current (master) schema** being matched |
| `.ColumnToFilter` | The column on `ReferenceSchema` to expose or check |

**Examples from the codebase:**

| Path | Reads as |
|---|---|
| `[UsrLegalDocumentParticipant:UsrLegalDocument:UsrLegalDocument].Id` | Participants whose `UsrLegalDocument` FK matches the current `UsrLegalDocument.Id` |
| `[UsrLegalDocumentProduct:UsrLegalDocument:UsrLegalDocument].Id` | Products whose `UsrLegalDocument` FK matches the current `UsrLegalDocument.Id` |
| `[UsrBillingLine:UsrAccount:UsrAccount].Id` | Billing lines whose `UsrAccount` FK matches the current `UsrAccount.Id` |
| `[UsrLegalDocumentProduct:UsrProduct:UsrProduct].UsrLegalDocument` | The `UsrLegalDocument` column on products whose `UsrProduct` FK matches |
| `[UsrLegalDocumentParticipant:UsrAccount:UsrAccount].UsrLegalDocument` | The `UsrLegalDocument` column on participants whose `UsrAccount` FK matches |
| `[UsrTransaction:UsrBillingLine].Id` | Transactions linked to the current billing line |
| `[UsrFeeTypeToOperatingUnit:UsrFeeType].UsrProduct` | OperatingUnit mappings for fee types, traversed from the fee type |

---

## Quick Reference Table

| Goal | Method / Constructor |
|---|---|
| Create filter group | `new sdk.FilterGroup()` |
| Set OR logic | `group.logicalOperation = sdk.LogicalOperatorType.Or` |
| Nest a group | `parent.add(child)` |
| Column = value | `group.addSchemaColumnFilterWithParameter(ComparisonType.Equal, col, val)` |
| Column <> value | `group.addSchemaColumnFilterWithParameter(ComparisonType.Not_equal, col, val)` |
| Column > value | `group.addSchemaColumnFilterWithParameter(ComparisonType.Greater, col, val)` |
| Column >= value | `group.addSchemaColumnFilterWithParameter(ComparisonType.Greater_or_equal, col, val)` |
| Column IN (array) | `group.addSchemaColumnInFilterWithParameters(ComparisonType.Equal, col, arr)` |
| Column IS NULL | `group.addSchemaColumnIsNullFilter(col)` |
| EXISTS (shorthand) | `group.addExistsFilter("[Schema:FK:PK].Id", subFilters)` |
| EXISTS (full) | `new sdk.ExistsFilter(new sdk.ColumnExpression({columnPath}), sub, ComparisonType.Exists)` |
| NOT EXISTS | `new sdk.ExistsFilter(..., ComparisonType.Not_exists)` |
| Load with filter | `model.load({ attributes, parameters: [{type: ModelParameterType.Filter, value: fg}], options })` |
| Load by primary key | `model.load({ ..., parameters: [{type: ModelParameterType.PrimaryColumnValue, value: id}] })` |
| Update with filter | `model.update({ col: val }, [{type: ModelParameterType.Filter, value: fg}])` |
| COUNT aggregate | `attributes: [{ type:"function", path:"Id", name:"Count", functionConfig:{aggregation: AggregationFunction.Count} }]` |
| Limit rows | `options: { pagingConfig: { rowCount: N } }` |
