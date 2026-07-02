---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Icon function"
breadcrumb: []
source_path: "formulas-and-functions/functions/icon.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Icon function

Applies to: TBM Studio 12.0 and later

Evaluates two or more expressions and returns one of up to five HTML <img> tags for colored
icons based on the results.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

`Icon(["icon-type"], expression, expression+)`

## Arguments

*[icon-type]*

> There are several types of icons available. The table below lists the types, expressions, and
> results for each expression.
>
> This argument is optional. If you omit the argument, the function defaults to the "redcircles"
> icon type.
>
> | Icon Type | Expressions and Results |
> | --- | --- |
> | "redcircles" | Expression 1: red circle Expression 2: pink circle |
> | "3colorcircles" | Expression 1: green circle Expression 2: yellow circle Expression 3: red circle |
> | "3arrows" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
> | "3arrowsinv" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
> | "4arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
> | "4arrowsinv" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
> | "5arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: right arrow Expression 4: down right arrow Expression 5: down arrow |
> | "5arrowsinv" | Expression 1: up arrow Expression 2: up right arrow Expression 3: right arrow Expression 4: down right arrow Expression 5: down arrow |
> | "redcircles" | Expression 1: red circle Expression 2: pink circle |
> | "3colorcircles" | Expression 1: green circle Expression 2: yellow circle Expression 3: red circle |
> | "3arrows" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
> | "3arrowsinv" | Expression 1: up arrow Expression 2: right arrow Expression 3: down arrow |
> | "4arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
> | "4arrowsinv" | Expression 1: up arrow Expression 2: up right arrow Expression 3: down right arrow Expression 4: down arrow |
> | "5arrows" | Expression 1: up arrow Expression 2: up right arrow Expression 3: right arrow Expression 4: down right arrow Expression 5: down arrow |
> | "5arrowsinv" | Expression 1: up arrow  Expression 2: up right arrow  Expression 3: right arrow  Expression 4: down right arrow  Expression 5: down arrow |
>
> There are several rules that govern the evaluation of the expressions:
>
> - Expressions are evaluated in the order they are listed in the function.
> - If an expression is true, the result for that expression is displayed in the table and the
>   remaining expressions are ignored.
> - If a full set of expressions is entered for an icon type, and none of the expressions are true,
>   the cell is left blank.
> - If a less than full set of expressions is entered for an icon type, values falling outside the
>   specified expressions are assigned the icon associated with the first expression not specified.For
>   example, assuming you are using the 3colorcircles icon type. You enter expressions for the green
>   circle and yellow circle icons, but not for the red icon. Values falling outside the green and
>   yellow icon expressions will automatically be assigned the red circle icon.
>
> The icon-type argument is optional. If you omit the argument, the function defaults to the
> "redcircles" icon type.

*expression*

> The number of expressions depends on the icon type selected. The expressions support AND and OR
> operators.
>
> For example:
>
> Icon("3arrows",Avg CPU Util<40,Avg CPU Util<50,Avg CPU Util<70 AND Disk Image
> GB=500)
>
> There are several rules that govern the evaluation of the expressions:
>
> - Expressions are evaluated in the order they are listed in the function.
> - If an expression is true, the result for that expression is displayed in the table and the
>   remaining expressions are ignored.
> - If a full set of expressions is entered for an icon type, and none of the expressions are true,
>   the cell is left blank.
> - If a less than full set of expressions is entered for an icon type, values falling outside the
>   specified expressions are assigned the icon associated with the first expression not specified.
> - For example, assume you are using the 3colorcircles icon type. You enter expressions for the
>   green circle and yellow circle icons, but not for the red icon. Values falling outside the green and
>   yellow icon expressions will automatically be assigned the red circle icon.
> - The order of evaluation is AND and then OR. Operations within parentheses are evaluated
>   first.

## Return type

String

## Remarks

Only simple expressions, the same as those used in the [IF](if.htm "(Opens in a new tab or window)"), can be used.

## Example

The following example returns:

- A green up arrow if the Average CPU Utilization is greater than 65.
- A yellow right arrow if the Average CPU Utilization is greater than 50.
- A red down arrow if the Average CPU Utilization is greater than 0.

If CostPerGB does not exist, the function returns gray.

> `Icon("3arrows",Avg CPU Util>65,Avg CPU Util>50,Avg CPU Util>0)`

See also: [StatusIcon](statusicon.htm "(Opens in a new tab or window)")
