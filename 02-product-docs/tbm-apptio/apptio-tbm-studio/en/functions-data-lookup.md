---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Data lookup"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Data lookup"
source_path: "SSWRJM/studio/formulas-and-functions/data-lookup.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Data lookup

Data lookup is a feature that allows a cell to reference a value from one or more cells. Depending on the location of the cells, there are two data lookup variants:

- Internal data lookup

- External data lookup

Data lookup that references a value in another table, but in the same project.

## Internal data lookup

Internal data lookup allows a cell to reference a value from one or more cells in the same row.

Internal data lookup syntax

=column

The formula returns the values of all cells that are in the same row and are in the column column, where column is any column name in the same table.

## Examples

We create a new column called Space Usage Percent and assign the following formula:

=(Used Space/Total Space)*100

1. References the cells of the Used Space and Total Space columns in the same row.
1. Does the computation of the formula.
1. Assigns the final value to the cell containing the formula.

## External data lookup

External data lookup allows a cell to reference a value from one or more cells in a column of another table.

Read about use case and performance considerations

Read about alternative external data lookup methods

```
={table}:{column1}

or

={table}:{column1}[selector]
```

- {table} - name of another table that contains the cells we want ro reference.
- {column1} - any column name in the table table.
- [selector] - additional criteria of the cells. In the selector, you can use relational operators, for example = , != , IN , NOT IN , > , and < . The selector can reference one or more columns in the table table and in the table where this formula is defined.

## Examples

=GL:Cost[ID="95847"]

Returns the sum of all cells in column Cost of the GL table, where the ID value in that cells equals 95847 .

=GL:Cost[ID="95847"]*PercentColumn

Returns the sum of all cells in the Cost column of the GL table, where the value in the ID column of that table equals 95847 .

Then, uses an internal data lookup to multiply the returned value by the value of the cell in the PercentColumn column . The PercentColumn must be in the same row as this formula.

This formula uses both an external data lookup and an internal data lookup.

=GL:Cost[Type=Expense Type]

Returns the sum of all cells in the Cost column of the GL table, where the value in the Type column and in the same rows equals the value of the Expense Type column in the cell where this formula is defined.

- The left side of each comparison looks for a column with that name in the target table.
- The right side looks for a column in the table, where the formula is defined.

In this example, GL .

This formula uses an internal data lookup inside an external data lookup.

=GL:Cost[Type="ServerType"]

Returns the sum of all cells in the Cost column of the GL table, where the value in the Type column of that table equals the label: ServerType .

=Labor:Amount[Equipment IN ("server","router","desktop") ]

Returns the sum of all cells in the Amount column of the Labor table, where the value in the Equipment column of that table equals server , router , or desktop .

=Labor:Amount[Equipment NOT IN ("server","router","desktop")]

Returns the sum of all cells in the Amount column of the Labor table, where the value in the Equipment column of that table doesn't equal server , router , or desktop .

=Storage:Amount[Amount>Threshold]

Returns the sum of all cells in the Amount column of the Storage table, where the value in the Amount column of that table is greater than the value in the cell in the Threshold column in the same row (in the table where the formula is defined, not in the Storage table).

## Use Case and Performance Considerations

Because the external data lookup performs the equivalent of a SumIf on the destination table (by finding all the cells that meet the criteria, and then summing them), it is a potentially costly operation which may have a negative impact on performance.

Whenever possible, use the lookup function which supports the required use case. The lookup function only returns the first match it finds, which reduces the impact on performance. The external data lookup finds all the rows that match the selector criteria.

If there is need to perform the same external data lookup selector criteria in the same table more than once, we suggest to create a new column in the table which would be the equivalent of the selector criteria (and would potentially include a SumIf, if needed), and then use that as the column that’s looked up in multiple lookup functions in other tables. This way the more expensive operation of finding the matching rows is only done once, and the less expensive operation of referring the columns across tables is done multiple times.

## Alternative external data lookup methods

- Lookup
- LookupEx
- TableMatch
- Join step in the transform pipeline
