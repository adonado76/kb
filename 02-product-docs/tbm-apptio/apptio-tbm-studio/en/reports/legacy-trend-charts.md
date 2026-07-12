---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Legacy trend charts"
breadcrumb: []
source_path: "reports/legacy-trend-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Legacy trend charts

Applies to: TBM Studio 12.0 and later

For legacy charts, there is a Trend tab in the Properties dialog. The properties
control the appearance of the chart and the data displayed. Included in the controls is the ability
to project values over a specified number of periods based on historical data. You can add future
projections to trend charts, where the projections are based on a specified number of previous
months.

The Trend tab is available only for legacy charts created with older versions of the
application. If you convert a trend chart to a legacy chart, the tab will not be available.

The standard chart properties also are available from the other tabs in the Properties
dialog. For information on the standard properties, see [Set chart properties](set-chart-properties.htm "(Opens in a new tab or window)").

Field descriptions:

The Trend fields are described below:

- Trend Value - The column used to provide the values charted.
- Trend Key - The unit identifier column. This should be the same as the value in the **X Axis
  Tag** field on the Chart tab.
- Trend Past Range - How far back from the current period do you want the chart to go? The number
  entered will apply to the currently selected period: months, quarters, years. For example, if the
  period selected is months and you enter 6 in the field, the chart will show the current month plus
  the previous five months.
- Trend Future Range - How far forward from the current period do you want the chart to go? The
  number entered will apply to the currently selected period: months, quarters, years. For example, if
  the period selected is months and you enter 6 in the field, the chart will show the current month
  plus the next six months.
- Trend Reverse Order - By default, time on the X axis runs from past to future, left to right. If
  you select this option, the time will run from the future to the past. For example, if the chart
  displays data from Jan 2010 to December 2010, the reverse order would display the data from December
  2010 to Jan 2010.
- Trend Add Total Column - This field applies only to trend tables, not trend charts. Leave this
  field blank.
- Trend Add Average Column - This field applies only to trend tables, not trend charts. Leave this
  field blank.
- Projection Future Range - The number of time periods to project into the future based on the
  currently selected time period. For example, if the current time period is months, the projection
  will go six months into the future.
- Past Range to Use for Projections - The number of time periods moving backwards in time to use
  to do the projection calculations. This must be two or greater. If you enter a 0 or 1, the
  application will use the value from the Trend Past Range field.
- Units to Project - The units in the chart to project. For example, if the units displayed in the
  chart are divisions called Eastern, Central, and Western, you could choose to project only the
  Eastern division.
- Projection Algorithm - Select the projection algorithm you want to use. The algorithms are the
  standard algorithms used in statistical analysis. The default is algorithm is
  Regression.
- Group Projection and Trend - This field applies only to trend tables. Leave this field
  blank.
- Strip Leading and Trailing Zero Values - Removes any zero values at the start or end of the
  chart. This prevents the trend line from dropping down to the X axis at the beginning and end of the
  chart.

## Add projections directly from a trend chart

If you have created a legacy trend chart and would like to project values into the future based
on the existing data in the chart, you can add a projection. To add a projection, right-click in the
graph and select Project Trend from the pop-up menu. The application will add a regression
projection for a period of time equivalent to the period of time being trended.

To remove the projection from the graph, right-click in the graph and select **Remove
Projection** from the pop-up menu.

Note: Projections are not available for Ad Hoc Query charts.
