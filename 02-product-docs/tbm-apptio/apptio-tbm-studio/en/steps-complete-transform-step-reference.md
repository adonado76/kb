---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Complete Transform Step Reference"
breadcrumb:
  - "Reference"
  - "Data Studio Reference"
  - "Transform Steps"
  - "Complete Transform Step Reference"
source_path: "SSWRJM/studio/new-uc/reference/complete-transform-steps.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Complete Transform Step Reference

Append Step

Purpose: Add rows from one or more source tables to the target table

When to Use: Combining data from multiple sources into a single table

Can Only Be Added Once: Yes

Behavior:

- Appended data is added as new rows (rows are never combined)
- Source columns can be mapped to existing target columns
- Source columns can be added as new columns to target table

Parameters:

| Parameter | Description |
| --- | --- |
| Parameter | Description |
| Append Data Source | Select source table(s) to append |
| Column Mapping | Map source columns to target columns |
| Additional Source Columns | Add source columns not in target |

Date Partition Step

Purpose: Distribute date-stamped data across time periods automatically

Can Only Be Added Once: Yes

Row-Based Parameters:

| Parameter | Description |
| --- | --- |
| Parameter | Description |
| Start Date | Column containing start dates |
| End Date | Column containing end dates (optional) |

Column-Based Parameters:

| Parameter | Description |
| --- | --- |
| Parameter | Description |
| Interpret Year As | Fiscal Year or Calendar Year |
| New Column Prefix | Label added to partitioned columns |
| Column Sets | Select which column groups to partition |

Filter Step

Purpose: Remove rows based on column value conditions

Can Only Be Added Once: Yes

Filter Operators:

| Operator | Data Type | Description |
| --- | --- | --- |
| Operator | Data Type | Description |
| Contains | String | Partial match |
| Does Not Contain | String | Partial exclusion |
| Starts With | String | Prefix match |
| Ends With | String | Suffix match |
| Less Than | Numeric | Less than value |
| Greater Than | Numeric | Greater than value |
| Equals | All Types | Exact match |
| Not Equals | All Types | Not equal |
| Is Null | All Types | Empty value |
| Is Not Null | All Types | Non-empty value |
| Is In | All Types | Multiple value match |
| Is Not In | All Types | Multiple exclusion |

Combining Filters:

- AND: All conditions must be true
- OR: Any condition must be true
- Parentheses: Group related conditions

Formulas Step

Purpose: Add calculated columns, change column types, or override existing values

Column Operations:

| Operation | Description |
| --- | --- |
| Operation | Description |
| Add Column | Create new calculated column |
| Edit Column | Modify existing column formula or type |
| Delete Column | Remove a formula column |

See Also: Section 5.4 Formulas & Functions for complete formula reference

Group Step

Purpose: Aggregate table data by grouping on one or more columns

Can Only Be Added Once: Yes

Behavior:

- Creates one row per unique combination of group-by values
- Adds {.Count} column showing row count per group
- Numeric columns are summed
- Text columns with varying values show "..." (ellipsis)

Join Step

Purpose: Combine data from multiple tables based on matching column values

Can Only Be Added Once: Yes

Join vs Append:

| Join | Append |
| --- | --- |
| Join | Append |
| Combines data into same rows | Adds data as new rows |
| Based on matching column values | Based on column mapping |
| Use for enrichment | Use for combining datasets |

Map Columns Step

Applies to: TBM Studio 12.7 and later

Purpose: Align table data to master data set schemas for application compliance

Can Only Be Added Once: Yes

Mapping Options:

| Option | Description |
| --- | --- |
| Option | Description |
| Choose source | Select column from dropdown |
| Enter fixed value | Constant value for all rows |
| Add Custom Column | Create new column in master data set |
| Join | Use joined table columns |

Pivot Step

Purpose: Summarize data by converting rows to columns

Can Only Be Added Once: Yes

Parameters:

| Parameter | Description |
| --- | --- |
| Parameter | Description |
| Pivot Row | Column for first column values |
| Pivot Column | Column for column headers |
| Pivot Value | Numeric column to aggregate in cells |

Remove Duplicates Step

Purpose: Filter out rows with duplicate values in specified columns

Can Only Be Added Once: Yes

Parameters:

| Parameter | Description |
| --- | --- |
| Parameter | Description |
| Key Column | Column to check for duplicates |
| Comparison Column | Column used to determine which row to keep |
| Comparison Type | Largest or Smallest - determines kept row |

Row-Level Security Step

Applies to: TBM Studio 12.2 and later

Purpose: Filter table data based on current user for data governance

Can Only Be Added Once: Yes

Filter Entry Parameters:

| Field | Description |
| --- | --- |
| Field | Description |
| First field | Column in table to filter |
| Second field (intersects) | Mapping table with security data |
| Third field | Column in mapping table with permitted values |
| Fourth field (where user is) | Column in mapping table with user IDs |

Unpivot Step

Purpose: Convert column values to additional rows

Can Only Be Added Once: Yes

Output Columns:

| Column | Description |
| --- | --- |
| Column | Description |
| Collapse Column | Original column header names |
| Collapse Value | Original column values |

Warnings:

- Avoid mixing column types in unpivoted columns
- Monitor for excessive row expansion (rows multiply by column count)
