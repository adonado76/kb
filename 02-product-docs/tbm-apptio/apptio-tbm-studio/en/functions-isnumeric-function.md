---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "IsNumeric function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "IsNumeric function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/isnumeric.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# IsNumeric function

*Evaluates an expression to determine if it is a valid number, returning 'true' or 'false' as a string.*

## Syntax

IsNumeric("value")

or

IsNumeric({column name})

IsNumeric(expression)

## Parameters

value

The string to be evaluated. It must be enclosed in quotes.

{column name}

The name of a column in a table.

## Behavior

- Checks if the provided expression evaluates to a numeric value.
- Returns the string 'true' if the value is a number.
- Returns the string 'false' if the value is not a number.
- Can evaluate both quoted strings and column references.
- Ignores non-numeric characters such as '%' when determining numeric validity.

## Return type

The function returns boolean true or false .

## Remarks

You can use the function inside the IF function on both sides of the equation and in the STATUSICON function.

For example:

```
IF(IsNumeric("423"),"OK","Check for
        error.")
```

STATUSICON(IsNumeric("123"), LEN(TRIM(" hello ")) = 5 )

## Examples

- IsNumeric("95") = true
- IsNumeric("95%") = true
- IsNumeric("95 Percent") = false
- IsNumeric({Location}) = false
- IsNumeric({345}) = true
