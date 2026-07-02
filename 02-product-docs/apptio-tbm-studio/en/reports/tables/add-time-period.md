---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a time period to the columns in a table"
breadcrumb: []
source_path: "reports/tables/add-time-period.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a time period to the columns in a table

Applies to: TBM Studioo 12.0 and later

If you want to add time periods such as months or quarters to a table, select the Time
perspective and drag a time period into the Columns area or Rows area. In the
following image, months have been added to the table. The application supports periods, months,
quarters, and years. You can use more than one time period per table. The table in the following
image was created using the settings in the following image. You can add a time period to
object-based and transform tables.

![](../../../resources/images/studio_images/studioimages/studio/aug371.png)

![](../../../resources/images/studio_images/studioimages/reports/rep059.png)

You can drag more than one time period into the Axis area of a chart or the Columns
area of a table. For example, you can drag in January, February, and March, and then drag in 1st
Quarter.

You can convert the table in Figure A to a trended line chart by selecting the Line icon
from the Ad Hoc tab.

## Add time to a column

You can add periods, months, quarters, and years to a column by adding the time fields to the
Rows area of the dialog as shown in the following image:

![](../../../resources/images/studio_images/studioimages/studio/stu616.png)

Note: The file upload is not possible for closed time periods. It will not display the start of
project period, but the actual period it was uploaded. If it is a closed period, then it appears as
"<MMM FYYYYY (closed)".

## Control the periods displayed

In a trend table, you can control the periods displayed by right-clicking the Time field
in the Columns area of the Component Configuration pane and selecting one of the
following options:

|  |  |
| --- | --- |
| This Quarter | Displays the periods in the quarter selected in the date picker. |
| This Half | Displays the periods in the half selected in the date picker. |
| This Year | Displays the periods in the year selected in the date picker. |
| Range | Enter the number of periods to display from the past and into the future. |

Add columns to a trended table

To add a column to a trended table like the Manager column shown in the following image, drag the
field into the Rows area and turn off subtotals. To turn off subtotals, select the
Data tab, click the Subtotal icon, and then click the Clear button. The Manager
column was added using the settings shown in the following image:

![](../../../resources/images/studio_images/studioimages/studio/aug480.png)

Settings to create the table:

![](../../../resources/images/studio_images/studioimages/reports/rep285.png)

## Offset months, quarters, and periods

If you add Current Month, Current Quarter, or Current Period to the Columns area, you can
offset the date by right-clicking the field and selecting Shift. The Time Shift dialog
is displayed as shown in the following image. You can enter a positive or negative number in the
Offset field to display a future or previous period. For example, if the field is
CurrentMonth, and you enter *3* in the Offset field, the table will display data
from three months in the future. If the date picker for the report was set for March, the table
would show data from June.

![](../../../resources/images/studio_images/studioimages/reports/rep181.png)

## Trailing Twelve Month time aggregation

**Applies to**: 12.11.8 and later

A new feature **Trailing Twelve Months** aggregation is added in the Time selection. It helps
to look at a running 12-month total rather than from the “fiscal calendar” perspective, as explained below:

- Sums the previous 12 months (e.g., if current period = August 2024, it will sum values for
  August 2023 – July 2024)
- If 13 Period Fiscal calendar, it will sum the trailing 13-months
- If less than 12 (or 13) periods are available, it will annualize the amount

![](../../../resources/images/studio_images/12-month.png)
