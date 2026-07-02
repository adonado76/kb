---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "LookupEx function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/lookupexandlookupex_wild.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug160.png"
  - "resources/images/studio_images/studioimages/studio/aug161.png"
  - "resources/images/studio_images/studioimages/studio/aug162.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupEx function

Performs a lookup across tables and returns all matching values, creating new rows for
each match. This function enables a one-to-many relationship by joining every matching row from
the lookup table into the transformed table.

## Syntax

```
LookupEx(source_column, lookup_table, matching_column, lookup_value_column, leave_original_value, replace_nulls, ignore_case)
```

## Parameters

- *source\_column*: The column in the current dataset whose values are used to find
  matches in the lookup table. Note: This parameter accepts an expression, meaning you can
  provide a literal value, a column reference, or the result of another function. Required
- *lookup\_table*: The name of the table that contains the values to return. Must
  refer to an existing table in the dataset. Required
- *matching\_column*: The column in the lookup\_table in which to look for a match with
  the source\_column values. Required
- *lookup\_value\_column*: The column in the lookup\_table that supplies the return
  values for matched rows. Required
- *leave\_original\_value*: If true, returns the original value from the source\_column
  when no match is found; otherwise, returns NULL. Defaults to false. Optional (default:
  false)
- *replace\_nulls*: If true, replaces NULL or empty values in the source\_column by
  matching against NULLs in the matching\_column. Defaults to false. Optional (default:
  false)
- *ignore\_case*: If true, performs case-insensitive matching between the
  source\_column and matching\_column. Defaults to false. Optional (default: false)

## Behavior

- Performs a one-to-many lookup and adds a new row for each additional match found in the
  lookup table.
- If there are no matches, the original row is preserved with a NULL value in the lookup
  column.
- If there are multiple matches, the original row is duplicated for each match, and each
  copy receives one of the matched values.
- Optional parameters must be used in sequence if later ones are specified.

## Return type

Type of the column specified in lookup\_value\_column

## Examples

`LookupEx(Cost Center Category, Cost Category Resources, Cost Center Category,
Resources)`

In the BU Cost Centers table, adds a new column called Resources that retrieves all
matching values from the Cost Category Resources table based on the Cost Center Category. If
multiple resources match a single category, multiple rows are created. If no match is found,
the original row remains with a NULL value in the Resources column.

**BU Cost Centers Table (before):**

| Business Unit | Location | Manager | Cost Center Category |
| --- | --- | --- | --- |
| Research | Dallas | Smith | Level 1 |
| Development | New York | Jones | Level 1 |
| Production | Seattle | Wilson | Level 2 |
| Marketing | London | Brown | Level 3 |
| Sales | Vienna | Deider | Level 3 |

**Cost Category Resources Table:**

| Cost Center Category | Resources |
| --- | --- |
| Level 1 | Applications |
| Level 1 | Hardware |
| Level 1 | Network |
| Level 2 | Hardware |
| Level 2 | Network |
| Level 3 | Network |

**BU Cost Centers Table (after applying LookupEx):**

| Business Unit | Location | Manager | Cost Center Category | Resources |
| --- | --- | --- | --- | --- |
| Development | New York | Jones | Level 1 | Network |
| Development | New York | Jones | Level 1 | Applications |
| Development | New York | Jones | Level 1 | Hardware |
| Marketing | London | Brown | Level 3 | Network |
| Production | Seattle | Wilson | Level 2 | Network |
| Production | Seattle | Wilson | Level 2 | Hardware |
| Research | Dallas | Smith | Level 1 | Network |
| Research | Dallas | Smith | Level 1 | Applications |
| Research | Dallas | Smith | Level 1 | Hardware |
| Sales | Vienna | Deider | Level 3 | Network |

Assume you have the following BU Cost Centers table:

![image lookupex](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug160.png)

You want to match each cost center category with the resources assigned to that category.
To do the matching, you have created the following Cost Category Resources table that lists
the resources for each category:

![image lookupex](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug161.png)

You add a new column to the BU Cost Centers table called Resources that uses the LookupEx
function. Below is the syntax for the function and the function as it would appear in the
Resources column.

```
LookupEx(source_column,lookup_table,matching_column,replacement_column
)
```

```
=LookupEx(Cost Center Category,Cost Category
            Resources,Cost Center
      Category,Resources)
```

The result is shown in the following image. Note that the application added rows to the
table for each match it found. For example, there are three rows for the **Development**
business unit representing the three resources: Network, Applications, and Hardware.

![image lookupex](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug162.png)

Note:

- Use this function cautiously on large datasets, as it can result in large row
  expansions.
- Only one instance of this function should be used per table to avoid incorrect
  results.
- This function is not supported in the Ribbon formula bar or Data tab preview.
- Do not use curly braces { } to escape column names in this function.
