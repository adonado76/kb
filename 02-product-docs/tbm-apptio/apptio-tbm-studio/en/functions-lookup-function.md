---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Lookup function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Lookup function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/lookup.html"
images:
  - "03-media/apptio-tbm-studio/aug036.png"
  - "03-media/apptio-tbm-studio/aug037.png"
  - "03-media/apptio-tbm-studio/aug039.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Lookup function

*Searches for a value in a lookup table based on a match between a column in the current table and a column in the lookup table, and returns the corresponding value from a replacement column.*

Finds the value in a specified source column in the current table and in a specified column of a lookup table. Lookup and Lookup_Wild return the value in the corresponding specified replacement column of the lookup table. If two or more values are found in the lookup table, the value {Various} is returned. The only difference between the two functions is that Lookup_Wild supports regular expressions in the matching column and Lookup does not.

To increase row count by creating a new row for every return value instead of {Various}, use LookupEx .

If you are using Lookup to bring in a numeric value, and you want the values summed instead of returning various, use the Data lookup syntax.

## Syntax

```
Lookup(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value)
```

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

Lookup({Product ID}, ProductTable, ProductCode, Description) : Returns the Description from the ProductTable that matches the current row's Product ID.

Lookup(ProductType, LookupTable, Type, Label, true) : Returns the Label for matching ProductType; if no match is found, returns the original ProductType.

Lookup(Region & SubRegion, GeographyTable, Region & SubRegion, Code, false, false, true) : Performs a case-insensitive lookup using two combined columns.

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
- Use Lookup_Wild if you need pattern matching via regular expressions in the matching column.
- If multiple matching rows are found, Lookup returns '{Various}'. If this is not acceptable, use LookupEx instead.
