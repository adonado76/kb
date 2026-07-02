---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Trend charts"
breadcrumb: []
source_path: "reports/trend-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Trend charts

Applies to: TBM Studio 12.0 and later

A trend chart displays a value as it changes over time. For example, you could trend data center
costs for the past four quarters as shown in the following image. You create trend-charts-based
tables. To create a trend chart, drag a time field into the Axis area of the **Ad Hoc
Component Configuration** dialog.

![](../../resources/images/studio_images/studioimages/studio/stu557.png)

## Create a trend chart

1. Select the Chart icon on the Report.
2. In the Ad Hoc Component Configuration dialog, drag fields into the appropriate
   areas.
3. Drag a time field into the Axis area.

   The chart shown in the previous image was created using
   the fields shown in the following image:

   ![](../../resources/images/studio_images/studioimages/studio/stu558.png)
4. To set the number of periods displayed in the trend chart, right-click the value in the
   Axis area and select one of the options:
   - This Quarter - Displays the three months in the current fiscal quarter.
   - This Half - Displays the six months in the current fiscal half.
   - This Year - Displays the 12 months in the current fiscal year.
   - Range - Displays a dialog where you can set the number of months to show going backward
     and forward in time from the current month

## Lock the time period

By default, trend charts trend forward and backward relative to the currently selected time
period. If you want to lock the trend chart to a specific time period, set the time period using the
Data Time Period field on the Advanced tab of the Properties dialog.

For example, assume your fiscal year is from January to December, and you want a trend chart to
display data for the fiscal year regardless of the currently selected period. You would set **Date
Time Period** to Start of Current Fiscal Year.
