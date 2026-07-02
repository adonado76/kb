---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Lookup_Wild function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/lookup_wild.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug036.png"
  - "resources/images/studio_images/studioimages/studio/aug037.png"
  - "resources/images/studio_images/studioimages/studio/aug039.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lookup_Wild function

Searches for a value in a lookup table using pattern matching (regular expressions) in
the matching column, and returns the corresponding value from a replacement column.

## Syntax

```
Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value)
```

`Lookup_Wild(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

## Parameters

- *source\_column*: The column in the current table used to find matches. Supports
  multiple columns joined with & or &&. Required
- *lookup\_table*: The name of the lookup table that contains the matching and
  replacement values. Must be a constant. Required
- *matching\_column*: The column in the lookup table to match against the source
  column. Supports regular expressions only in Lookup\_Wild. Required
- *replacement\_column*: The column in the lookup table from which to return the
  value. Prefix with '=' to dynamically select a column using the source table.
  Required
- *leave\_original\_value*: Returns the original source value if no match is found. If
  false, returns blank. Optional (default: False)
- *replace\_nulls*: Determines behavior when the source value is null. If true,
  attempts to match a null value in the lookup column. Optional (default: False)
- *ignore\_case*: If true, performs a case-insensitive match. If false, matching is
  case-sensitive. Optional (default: False)
- *default\_value*: Optional default value to return when no match is found and
  leave\_original\_value is false. Optional

## Behavior

- Finds a match between the source column and the matching column in the lookup table.
- Returns the value from the replacement column for the last match found.
- If multiple rows match, returns '{Various}'.
- Supports optional boolean flags for behavior customization: leave\_original\_value,
  replace\_nulls, and ignore\_case.
- Only works with label-type columns in source and matching columns (numeric types not
  supported).

## Return type

Matches the data type of the replacement column

## Examples

`Lookup_Wild(ProductCode, ProductTable, CodePattern, Description)`: Returns
the Description where the ProductCode matches a regular expression in the CodePattern
column.

`Lookup_Wild(Name, PatternsTable, RegexPattern, Category, false, true,
true)`: Performs a case-insensitive, null-replacing pattern-based lookup for
'Name'.

Assume you have the following table called Data Centers that lists data centers and their
location:

![lookup function](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug036.png)

Based on the location, you want to fill in the Time Zone column. You have the following table
called Time Zone that can supply the GMT offset.

![lookup function](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug037.png)

You enter the following in the Value Override field for the Location column in the Data Centers
table:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

The result is:

![lookup function](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug039.png)

- If using replace\_nulls or ignore\_case, you must also include all preceding optional
  parameters.
- When no match is found and leave\_original\_value is false, the function returns blank
  unless a default\_value is specified.
- Supports pattern matching using regular expressions in the matching\_column.
- If multiple matching rows are found, Lookup\_Wild returns '{Various}'. If this is not
  acceptable, use LookupEx instead.
- Inference linking is preferred over Lookup\_Wild when possible, especially if the result
  does not need to persist in the data set.
