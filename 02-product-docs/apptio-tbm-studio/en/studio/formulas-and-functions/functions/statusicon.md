---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "StatusIcon function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/statusicon.html"
images:
  - "resources/images/studio_images/studioimages/icons/small_blueicon.png"
  - "resources/images/studio_images/studioimages/icons/small_grayicon.png"
  - "resources/images/studio_images/studioimages/icons/small_greenicon.png"
  - "resources/images/studio_images/studioimages/icons/small_redicon.png"
  - "resources/images/studio_images/studioimages/icons/small_yellowicon.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# StatusIcon function

**Applies to**: TBM Studio 12.0 and later

**\*\*\*Deprecated\*\*\*** This function has been replaced by the function [Icon](icon.htm "(Opens in a new tab or window)").

Evaluates two expressions and returns one of five HTML <img> tags for colored icons based on
the results.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables
- Dynamic text
- Calculated metrics and reports with metric columns

## Syntax

`StatusIcon(green_expression,red_expression)`

## Arguments

*green\_expression*

An expression that evaluates to true or false. If true, the function returns a

green icon ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_greenicon.png).

*red\_expression*

An expression that evaluates to true or false. If true, the function returns a

red icon ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_redicon.png).

If both expressions evaluate to true, the function returns a blue icon ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_blueicon.png).

If neither expression evaluates to true, the function returns a yellow icon ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_yellowicon.png).

If there is an error in the rules (for example, if a variable is specified that doesn't exist),
the function returns a gray icon ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/small_grayicon.png).

**Notes**:

The expressions support AND and OR operators.

For example:

```
StatusIcon(green_expression AND
          green_expression,red_expression AND (red_expression OR
      red_expression))
```

The order of evaluation is AND and then OR. Operations within parentheses are evaluated
first.

## Return type

String

## Remarks

Only simple expressions, the same as those used in [IF](if.htm "(Opens in a new tab or window)"), can be used.

## Example

Assume the following example:

`StatusIcon(CostPerGB<2,CostPerGB>3)`

It returns:

- Green if CostPerGB is less than 2.
- Red if CostPerGB is greater than 3.
- Yellow if CostPerGB is between 2 and 3.

Since both expressions cannot be true, this function can never return blue.

If CostPerGB doesn't exist, the function returns gray.

**See also**: [Icon](icon.htm "(Opens in a new tab or window)")
