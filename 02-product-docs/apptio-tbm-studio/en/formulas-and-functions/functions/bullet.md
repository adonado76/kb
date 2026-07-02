---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Bullet function"
breadcrumb: []
source_path: "formulas-and-functions/functions/bullet.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Bullet function

◆ Applies to: TBM Studio v12.3.4 and later

The Bullet function allows you to generate a bullet chart within a table.

## Where to use

The Bullet function can be used in Formula columns in report tables.

## Syntax

- Base syntax - If you are not certain, start with this syntax:
  `=Bullet(performance_measure)`
- Full syntax - This syntax allows you to override many defaults and behaviors that impact
  how the bullet chart renders:
  `=Bullet(performance_measure,[target|min|max|firstSplit|secondSplit=Expression()]*)`

## Arguments

> `performance_measure`

This required argument should be the name of a numeric column. It will be the primary value
rendered by the bullet chart.

Visual Guide:

![](../../../resources/images/studio_images/studioimages/studio_bullet%20function_performance%20measure.png)

## Optional arguments

One or more optional arguments can be passed as argument=value pairs. This allows you to override
the settings you want, while leaving other settings at their default behavior.

| Argument | Default Value | Meaning | Visual Guide |
| --- | --- | --- | --- |
| target | Only rendered if specified. | What is the value of the comparative measure that the bullet chart should display, if any. The comparative measure renders as a vertical red line. |  |
| Min | The smallest value in the column for either the performanceMeasure, or the specified target. This uses only the values in the displayed table itself, not rows that have been filtered out. | What is the minimum value on the charts scale. |  |
| Max | The largest value in either the performanceMeasure, or the specified target. This uses only the values in the displayed table itself, not rows that have been filtered out. | What is the maximum value on the charts scale. |  |
| firstSplit | (max-min) \* 0.6 | What is the value at which the leftmost background box should be drawn. |  |
| secondSplit | (max-min) \* 0.8 | What is the value at which the middle background box should be drawn. |  |

## Signs

Bullet charts allow for a negative minimum value and a positive maximum value. The bullet chart
will render the same as if you took all the numbers and added an amount to them that made them all
the same sign.

## Examples

This section provides examples of using the Bullet
function.

Display Cost - This Bullet function creates a simple bullet chart showing
Cost. The Min and Max will be set based on the range of values within the displayed column.

> `=bullet(Cost)`

![](../../../resources/images/studio_images/studioimages/studio_bullet%20function_example%20bullet%20chart.png)

Compare Cost to Budget - This is an example that displays Cost as the performance
measure, and displays the budget metric as the target would be:

> `=Bullet(Cost,target=Budget)`

![](../../../resources/images/studio_images/studioimages/studio_bullet_compare%20cost%20to%20budget.png)

Disable the Background split - This example will disable the background splits as long
as your bullet charts contain positive numbers only.

> `=Bullet(Cost,firstSplit=0,secondSplit=0)`

![](../../../resources/images/studio_images/studioimages/studio_bullet%20func_table.png)

Compare a graphed value to 0 - When people compute a budget variance, it's sign means
whether a person is over or under budget. A Bullet graph can be configured to render the signed
value relative to 0.

> `=Bullet(Variance,Target=0)`

![](../../../resources/images/studio_images/studioimages/studio_bullet%20function_simple%20bullet.png)

Overlay statistical information - This example combines the Bullet function with the
Percentile function. It renders a bullet chart that shows one-third of the values are to the left of
the first split, and one-third of the values are to the right of the second split.

> `=Bullet(Cost,Target=0,firstSplit=Percentile(Cost,33),secondSplit=Percentile(Cost,66))`

![](../../../resources/images/studio_images/studioimages/studio_bullet%20function_table.png)
