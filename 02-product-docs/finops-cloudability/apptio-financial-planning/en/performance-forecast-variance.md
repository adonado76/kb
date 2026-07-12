---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Forecast Variance"
breadcrumb:
  - "Working with Plans"
  - "Analyzing Plan Performance"
  - "Forecast Variance"
source_path: "SSVWBC/cloud-financial-planning/creating-and-using-plans/forecast-variance.html"
images:
  - "03-media/apptio-financial-planning/cfp-forecast-variance.png"
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Forecast Variance

*Provides a summary view of forecast vs actual and estimated spending along with key variance drivers.*

The following table describes the index of numbers in the previous screen:

| # | Name | Description |
| --- | --- | --- |
| 1 | Period | This is the time period required for the analysis. Use the dropdown to select between Current Month , Current Quarter , or Current Year . All KPIs and charts will filter to show values only for the selected time period. Changing time period affects granularity of analysis. Current Month analyzes values at daily granularity; Current Quarter and Current Year is at monthly granularity. |
| 2 | KPIs | This Includes the following parameters: Actual Spend - Spending to date. Only considers fully completed months when selected Period is Current Quarter or Current Year . Estimate - Actual-to-date plus system-generated estimate of spending for the remaining days or months in the selected Period. Forecast - Forecast spend (from the Forecast section of the plan). Variance - Computed as Forecast vs Estimate , so negative variances indicate that the estimated spend for the selected period exceeds forecast. |
| 3 | Spend Over Time | This parameter shows actuals (for periods that have completed) and estimated values for the selected Period versus Forecast values (line). Select the Cumulative toggle bar to switch to a cumulative (running total) view of the spends. Hover over a bar or line segment to view values. |
| 4 | Forecast vs Estimate | Shows the top 5 largest variance between Forecast and Estimate for the selected Period . Use the dropdown selector to change the variance driver dimension. Note that only Cloudability dimensions are selectable (Plan-only dimensions are not associated with actuals). Hover over the variance slice to see values. |
| 5 | Cost Ownership filter | Filter page contents to selected cost owner(s). |
