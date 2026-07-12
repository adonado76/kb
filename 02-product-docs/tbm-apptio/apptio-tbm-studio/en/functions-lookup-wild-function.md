---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Lookup_Wild function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Lookup_Wild function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/lookup_wild.html"
images:
  - "03-media/apptio-tbm-studio/aug036.png"
  - "03-media/apptio-tbm-studio/aug037.png"
  - "03-media/apptio-tbm-studio/aug039.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Lookup_Wild function

*Searches for a value in a lookup table using pattern matching (regular expressions) in the matching column, and returns the corresponding value from a replacement column.*

## Syntax

```
Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value)
```

Lookup_Wild(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])

## Parameters

- source_column : The column in the current table used to find matches. Supports multiple columns joined with & or &&. Required
- lookup_table : The name of the lookup table that contains the matching and replacement values. Must be a constant. Required
- matching_column : The column in the lookup table to match against the source column. Supports regular expressions only in Lookup_Wild. Required
- replacement_column : The column in the lookup table from which to return the value. Prefix with '=' to dynamically select a column using the source table. Required
- leave_original_value : Returns the original source value if no match is found. If false, returns blank. Optional (default: False)
- replace_nulls : Determines behavior when the source value is null. If true, attempts to match a null value in the lookup column. Optional (default: False)
- ignore_case : If true, performs a case-insensitive match. If false, matching is case-sensitive. Optional (default: False)
- default_value : Optional default value to return when no match is found and leave_original_value is false. Optional

## Behavior

- Finds a match between the source column and the matching column in the lookup table.
- Returns the value from the replacement column for the last match found.
- If multiple rows match, returns '{Various}'.
- Supports optional boolean flags for behavior customization: leave_original_value, replace_nulls, and ignore_case.
- Only works with label-type columns in source and matching columns (numeric types not supported).

## Return type

Matches the data type of the replacement column

## Examples

Lookup_Wild(ProductCode, ProductTable, CodePattern, Description) : Returns the Description where the ProductCode matches a regular expression in the CodePattern column.

Lookup_Wild(Name, PatternsTable, RegexPattern, Category, false, true, true) : Performs a case-insensitive, null-replacing pattern-based lookup for 'Name'.

Assume you have the following table called Data Centers that lists data centers and their location:

Based on the location, you want to fill in the Time Zone column. You have the following table called Time Zone that can supply the GMT offset.

You enter the following in the Value Override field for the Location column in the Data Centers table:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

The result is:

- If using replace_nulls or ignore_case, you must also include all preceding optional parameters.
- When no match is found and leave_original_value is false, the function returns blank unless a default_value is specified.
- Supports pattern matching using regular expressions in the matching_column.
- If multiple matching rows are found, Lookup_Wild returns '{Various}'. If this is not acceptable, use LookupEx instead.
- Inference linking is preferred over Lookup_Wild when possible, especially if the result does not need to persist in the data set.
