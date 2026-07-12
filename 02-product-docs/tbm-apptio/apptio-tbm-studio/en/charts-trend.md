---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Trend Charts"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
  - "Trend Charts"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/trend-chart.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Trend Charts

Trend charts are specialized line charts designed specifically for displaying values as they change over time. They include built-in support for time period ranges and can include statistical projections to forecast future values.

Creating a Trend Chart

1. On the Report tab, click Chart.
1. In the Component Configuration panel, drag fields into the appropriate areas.
1. Drag a time field (Months, Quarters, Years) into the Axis area. This is what transforms the chart into a trend chart.
1. Right-click the time field in the Axis area to configure the time range.

Time Range Options

When you right-click a time field in the Axis area, you can select from these preset ranges:

- This Quarter: Displays the three months in the current fiscal quarter.
- This Half: Displays the six months in the current fiscal half.
- This Year: Displays the 12 months in the current fiscal year.
- Range: Opens a dialog where you can set custom months backward and forward from the current period.

Locking the Time Period

By default, trend charts display data relative to the currently selected time period. To lock the chart to a specific time period regardless of the report's date selection, use the Data Time Period field on the Advanced tab of the Properties dialog. For example, set Date Time Period to "Start of Current Fiscal Year" to always display the full fiscal year.

Adding Projections

Trend charts can include projections that forecast future values based on historical data. TBM Studio offers multiple regression algorithms:

| Algorithm | Description |
| --- | --- |
| Algorithm | Description |
| Regression | Standard linear regression for simple trend lines. |
| Multiple Linear Regression | Regression using multiple independent variables. |
| Polynomial Regression | Fits a polynomial curve to capture non-linear trends. |
| Simple Exponential Smoothing | Smooths data to reduce noise and highlight trends. |
| Double Exponential Smoothing | Accounts for both level and trend in the data. |
| Moving Average | Calculates averages over rolling time windows. |
