---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "StatusIcon function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "StatusIcon function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/statusicon.html"
images:
  - "03-media/apptio-tbm-studio/small_greenicon.png"
  - "03-media/apptio-tbm-studio/small_redicon.png"
  - "03-media/apptio-tbm-studio/small_blueicon.png"
  - "03-media/apptio-tbm-studio/small_yellowicon.png"
  - "03-media/apptio-tbm-studio/small_grayicon.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# StatusIcon function

*Applies to : TBM Studio 12.0 and later*

***Deprecated*** This function has been replaced by the function Icon .

Evaluates two expressions and returns one of five HTML <img> tags for colored icons based on the results.

## Where to use

- Data sets
- Formula columns in report tables
- Dynamic text
- Calculated metrics and reports with metric columns

## Syntax

StatusIcon(green_expression,red_expression)

## Arguments

green_expression

An expression that evaluates to true or false. If true, the function returns a

green icon .

red_expression

An expression that evaluates to true or false. If true, the function returns a

red icon .

If both expressions evaluate to true, the function returns a blue icon .

If neither expression evaluates to true, the function returns a yellow icon .

If there is an error in the rules (for example, if a variable is specified that doesn't exist), the function returns a gray icon .

Notes :

The expressions support AND and OR operators.

For example:

```
StatusIcon(green_expression AND
          green_expression,red_expression AND (red_expression OR
      red_expression))
```

The order of evaluation is AND and then OR. Operations within parentheses are evaluated first.

## Return type

String

## Remarks

Only simple expressions, the same as those used in IF , can be used.

## Example

Assume the following example:

StatusIcon(CostPerGB<2,CostPerGB>3)

- Green if CostPerGB is less than 2.
- Red if CostPerGB is greater than 3.
- Yellow if CostPerGB is between 2 and 3.

Since both expressions cannot be true, this function can never return blue.

If CostPerGB doesn't exist, the function returns gray.

See also : Icon
