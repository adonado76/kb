---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Icon function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Icon function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/icon.html"
images:
  - "03-media/apptio-tbm-studio/circle-red.png"
  - "03-media/apptio-tbm-studio/circle-pink.png"
  - "03-media/apptio-tbm-studio/circle-green.png"
  - "03-media/apptio-tbm-studio/circle-yellow.png"
  - "03-media/apptio-tbm-studio/up-arrow.png"
  - "03-media/apptio-tbm-studio/right-arrow.png"
  - "03-media/apptio-tbm-studio/down-arrow.png"
  - "03-media/apptio-tbm-studio/up-arrow-red.png"
  - "03-media/apptio-tbm-studio/down-arrow-green.png"
  - "03-media/apptio-tbm-studio/arrow-up-right.png"
  - "03-media/apptio-tbm-studio/arrow-down-right.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Icon function

*Applies to : TBM Studio 12.0 and later*

Evaluates two or more expressions and returns one of up to five HTML <img> tags for colored icons based on the results.

## Where to use

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

Icon(["icon-type"], expression, expression+)

## Arguments

[icon-type]

There are several types of icons available. The table below lists the types, expressions, and results for each expression.

This argument is optional. If you omit the argument, the function defaults to the "redcircles" icon type.

| Icon Type | Expressions and Results |
| --- | --- |
| "redcircles" | Expression 1: red circle Expression 2: pink circle |
| "3colorcircles" | Expression 1: green circle Expression 2: yellow circle Expression 3: red circle |
| "3arrows" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
| "3arrowsinv" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
| "4arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
| "4arrowsinv" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
| "5arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: right arrow Expression 4: down right arrow Expression 5: down arrow |
| "5arrowsinv" | Expression 1: up arrow Expression 2: up right arrow Expression 3: right arrow Expression 4: down right arrow Expression 5: down arrow |
| "redcircles" | Expression 1: red circle Expression 2: pink circle |
| "3colorcircles" | Expression 1: green circle Expression 2: yellow circle Expression 3: red circle |
| "3arrows" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
| "3arrowsinv" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
| "4arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
| "4arrowsinv" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
| "5arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: right arrow Expression 4: down right arrow Expression 5: down arrow |
| "5arrowsinv" | Expression 1: up arrow Expression 2: up right arrow Expression 3: right arrow Expression 4: down right arrow Expression 5: down arrow |

- Expressions are evaluated in the order they are listed in the function.
- If an expression is true, the result for that expression is displayed in the table and the remaining expressions are ignored.
- If a full set of expressions is entered for an icon type, and none of the expressions are true, the cell is left blank.
- If a less than full set of expressions is entered for an icon type, values falling outside the specified expressions are assigned the icon associated with the first expression not specified.For example, assuming you are using the 3colorcircles icon type. You enter expressions for the green circle and yellow circle icons, but not for the red icon. Values falling outside the green and yellow icon expressions will automatically be assigned the red circle icon.

The icon-type argument is optional. If you omit the argument, the function defaults to the "redcircles" icon type.

expression

The number of expressions depends on the icon type selected. The expressions support AND and OR operators.

For example:

Icon("3arrows",Avg CPU Util<40,Avg CPU Util<50,Avg CPU Util<70 AND Disk Image GB=500)

- Expressions are evaluated in the order they are listed in the function.
- If an expression is true, the result for that expression is displayed in the table and the remaining expressions are ignored.
- If a full set of expressions is entered for an icon type, and none of the expressions are true, the cell is left blank.
- If a less than full set of expressions is entered for an icon type, values falling outside the specified expressions are assigned the icon associated with the first expression not specified.
- For example, assume you are using the 3colorcircles icon type. You enter expressions for the green circle and yellow circle icons, but not for the red icon. Values falling outside the green and yellow icon expressions will automatically be assigned the red circle icon.
- The order of evaluation is AND and then OR. Operations within parentheses are evaluated first.

## Return type

String

## Remarks

Only simple expressions, the same as those used in the IF , can be used.

## Example

- A green up arrow if the Average CPU Utilization is greater than 65.
- A yellow right arrow if the Average CPU Utilization is greater than 50.
- A red down arrow if the Average CPU Utilization is greater than 0.

If CostPerGB does not exist, the function returns gray.

Icon("3arrows",Avg CPU Util>65,Avg CPU Util>50,Avg CPU Util>0)

See also : StatusIcon
