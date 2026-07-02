---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Overlay charts"
breadcrumb: []
source_path: "reports/overlay-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Overlay charts

Applies to: TBM Studio 12.0 and later

An overlay chart displays two data series in one chart. For example, you can display budget and
actuals on a chart, or storage capacity available and storage capacity used in a chart. A sample
overlay chart is shown in the following image:

![](../../resources/images/studio_images/studioimages/reports/rep303.png)

## Columns and lines

In an overlay chart, the data can be displayed using columns, stacked bars, and lines.

To select columns or lines for the base chart, select the Overlay tab and select an
option. Columns can be a separate bar for each value or stacked.

## Slicers

Slicers apply to overlay charts as well as to the other types of charts.

## Create an overlay chart

1. On the Report tab, click Overlay. The Ad Hoc Component Configuration dialog
   is displayed.
2. Click the Overlay tab.
3. To add the first data series, click Edit Base Layer.
4. To define the labels displayed on the x-axis, drag a field into the Axis area.
5. To define the element that will be graphed, drag a field into the Values area.
6. Format the data displayed by clicking a Layer Visualization option.
7. To add the second data series, click Edit Layer 1 and repeat steps 4-6 above.
8. If you need to simplify the chart, add a filter.

The chart now should be complete.

## Sort

You can sort the data using the base layer only.

1. Click Edit Base layer.
2. Click Sort.

## Navigate (Drill)

Navigation is supported using the Drill option.

## Enable navigation

Makes the elements in the chart active as links for navigation.

## Use Per Metric Drills

When you enable navigation, pie slices and bar chart bars are available for drilldowns.

Checking the Use Per Metric Drills option activates drill-down for the figures displayed
within pie slices and on bar chart bars.

## Navigate

Enter the name of a custom report to drill down to. The report must be a child of the current
report. If this field is filled in, all non-metric links in the chart will lead to the designated
report.
