---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Operators"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Operators"
source_path: "SSWRJM/studio/formulas-and-functions/operators.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Operators

*Applies to : TBM Studio 12.0 and later*

The application syntax supports many standard operators, as well as rollup operators, which reference the source or target units of a data rollup.

- + - Addition and String Concatenation
- - - Subtraction
- * - Multiplication
- / - Division
- = - Equal (this operator can be used with dates and strings as well as with numerical values)
- != - Not equal
- < - Less than
- <= - Less than or equal to
- > - Greater than
- >= - Greater than or equal to
- & - Concatenation
- @ - Rollup operator, source
- ~ - Rollup operator, target

## Rollup operators

Rollup operators can be used in data sets but not in tables on reports.

- @SOURCE - @ or SOURCE can be used to represent the sum of the values in the source object that will roll up to the current row in the target table.
- ~TARGET - ~ or TARGET can be used to represent the sum of the values in the target object that will receive values from the source table.

- In a model, when rolling up values from one object to another. In this case @ or SOURCE refers to all of the rows that are rolling up from the source object, and ~ or TARGET refers to all of the rows that are being rolled up to.
- In a table transform with a grouping, you can use statistical functions such as AVERAGE , LARGE , and SMALL . For example, you can use AVERAGE(@column) to have a cell contain the average of the named column for all of the source rows that were grouped together. For more information, see Referencing Grouped Columns . The column being operated on must have the Group By option set in the Column Details panel. Rollup operators are optional for these functions.

For example, consider the following unit table for a target object called Servers and source table called Utility:

## Servers table

| Hostname | Data Center | Space | CPUs | .Count |
| --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 |
| Host2 | Seattle | 1 | 1 | 1 |
| Host3 | Boston | 2 | 4 | 1 |
| Host4 | Seattle | 1 | 1 | 1 |

## Utility table

| ID | Host | .Count | Cost |
| --- | --- | --- | --- |
| A | Host1 | 1 | $100 |
| B | Host2 | 1 | $100 |
| C | Host3 | 1 | $100 |
| D | Host4 | 1 | $100 |

In the case of a direct rollup from Utility to Servers, you can allocate costs from All Utilities to Servers by Servers.Hostname using the following formula in the Advanced allocation option:

=@Cost

This means for each row in the target table, find the rows in the source table that match the identifier Hostname and allocate the sum of the Cost column for those rows.

The resulting unit table for Servers is:

| Hostname | Data Center | Space | CPUs | .Count | Cost |
| --- | --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 | $200 |
| Host2 | Seattle | 1 | 1 | 1 | $100 |
| Host3 | Boston | 2 | 4 | 1 | $100 |
| Host4 | Seattle | 1 | 1 | 1 | $0 |

Examining the first row in the unit table above, the value in the Cost column is $200 because two rows in the source Utilities table match the identifier Host1, each worth $100, so the sum is $200. The last row contains 0 in the Cost column, because no rows in the source table match the identifier Hostname.Host4.

To illustrate the ~ operator, consider the following source table called Data Centers:

| Data Center | .Count | Cost |
| --- | --- | --- |
| Boston | 1 | $1000 |
| Seattle | 1 | $1000 |

In the case of a direct rollup from Data Centers to Servers, you can allocate costs from All Data Centers to Data Centers.Data Center using the following formula in the Advanced allocation option:

=@Cost*(Servers.Space/~Servers.Space)

This formula multiplies the summed values by the Space ratio, which is Space divided by the total Space consumed by hosts in a given data center. In the example above, Boston is rolling up to two servers, Host1 and Host3, so for Host1 in the target table, the formula says to take the Cost value for the Boston Data Center ($1000) and multiply it by the space ratio for Host1. The space ratio for Host1 is derived by taking the value in the Space column (4) and dividing it by the sum of the Space column for rows where Data Center = Boston, which is 6 (4 for Host1 plus 2 for Host3).

So, the allocation for Host1 is:

```
=$1000 * (4 / 6)
=$1000 * 0.6667
=$666.6667
```

The resulting unit table for Servers is:

| Hostname | Data Center | Space | CPUs | .Count | Cost |
| --- | --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 | $667 |
| Host2 | Seattle | 1 | 1 | 1 | $500 |
| Host3 | Boston | 2 | 4 | 1 | $333 |
| Host4 | Seattle | 1 | 1 | 1 | $500 |
