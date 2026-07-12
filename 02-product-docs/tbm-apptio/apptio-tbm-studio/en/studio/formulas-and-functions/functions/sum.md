---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Sum function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/sum.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sum function

Returns the total sum of the values in the specified numeric column.

## Syntax

`Sum(column)`

## Arguments

*column*: The numeric column to sum. Optional

## Return type

Number

## Examples

The following table shows the results when the column Sum contains the function =Sum(Value):

| Group | Value | Sum |
| --- | --- | --- |
| A | 4 | 108 |
| A | 8 | 108 |
| B | 15 | 108 |
| B | 16 | 108 |
| B | 23 | 108 |
| C | 42 | 108 |

The following grouped table shows the results when the column Sum contains the function
=Sum(Value):

| Group | Value | .Count | Sum |
| --- | --- | --- | --- |
| A | 12 | 2 | 108 |
| B | 54 | 3 | 108 |
| C | 42 | 1 | 108 |

## Possible misleading results

The Sum function can result in technically correct but misleading results. For example, assume
you have the following table:

| Data Center | Number ofServers | Total Cost | Cost per Server |
| --- | --- | --- | --- |
| East | 1 | $100 | $100 |
| West | 4 | $200 | $50 |
| Total | 5 | $300 | $60 |

The Cost per Server column is calculated by dividing the total cost by the number of servers. The
Cost per Server value in the Total row is calculated as well based on 5 servers with a total cost of
$300: $300/5 = $60.

If you use the Sum function for the Cost per Server column, you get the following result:

| Data Center | Number ofServers | Total Cost | Cost per Server |
| --- | --- | --- | --- |
| East | 1 | $100 | $300 |
| West | 4 | $200 | $300 |
| Total | 5 | $300 | $60 |

`Sum(Cost)` : Returns the total of all values in the {Cost} column.
