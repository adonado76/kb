---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a Sparkline column to a table"
breadcrumb: []
source_path: "reports/tables/add-sparkline-column-to-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a Sparkline column to a table

Applies to: TBM Studio 12.0 and later

To show trended data, add a sparkline column to a table. In the following image, sparklines are
displayed in the Trend column. The data can be trended both backward and forward in time. For
sparklines to work, the table must have a primary key column that persists throughout the trended
time. Also, there must be data for each month.

![](../../../resources/images/studio_images/studioimages/studio/aug304.png)

Closely related to sparklines are status indicators. Status indicators are icons that indicate
the current state of the data, such as over or under a given value. Status indicators are described
in [Add a status
indicator column to a table](add-status-indicators-to-tables.htm "(Opens in a new tab or window)").

To add sparklines to a table:

1. Select the value column in the table you want to trend in the sparkline.
2. Click the Formulas tab.
3. From the Dates icon menu, click Sparkline Trend. The column is added to the
   table.The formula is `=Sparkline(past,future,column).` The arguments are described below:
   - Past is the number of periods the trend line will go back in time. This must be a
     positive number.
   - Future is the number of periods the trend line will go forward in time. This must be a
     positive number.
   - Column is the name of the column containing the data you want to trend.

For example, the formula below will trend the data in the Cost column backward and forward 4
months.

> =SPARKLINE(4,4,Cost)
