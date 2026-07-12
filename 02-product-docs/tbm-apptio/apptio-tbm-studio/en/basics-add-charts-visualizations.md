---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Add Charts and Visualizations"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Basics"
  - "Add Charts and Visualizations"
source_path: "SSWRJM/studio/new-uc/howtoguides/create-reports/add-chart-visual.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Add Charts and Visualizations

Objective: Add charts to visualize data patterns, trends, and comparisons

When to use: When you want to communicate insights quickly, show trends over time, compare categories, or highlight proportions

Time estimate: 10–15 minutes

## Choosing the Right Chart Type

Before adding a chart, consider what story you want to tell:

| Chart Type | Best For | Example Use Case |
| --- | --- | --- |
| Chart Type | Best For | Example Use Case |
| Bar (Horizontal) | Comparing categories with long names | Costs by application name |
| Column (Vertical) | Comparing categories | Costs by business unit |
| Pie/Donut | Showing proportions (parts of whole) | Budget allocation across departments |
| Line/Trend | Showing change over time | Monthly cost trends |
| Waterfall | Variance analysis | Year-over-year cost variance |

## Guidelines for Choosing Chart Types:

- Use bar/column charts when comparing discrete items (data centers, business units, vendors)
- Use line charts when you have time-series data and want to show trends
- Use pie charts sparingly —they work best with 3–7 categories and positive values only
- Use stacked charts when you need to show both totals and breakdowns
- Use waterfall charts for variance analysis or showing cumulative effect of sequential values

## Steps

1. Open your report and check it out .
1. Click the Report tab, then click Chart . A placeholder chart appears (horizontal bar by default), and the Ad Hoc Component Configuration panel opens.
1. Select a model object from the dropdown at the top of the Configuration panel.
1. Drag a dimension field into the Legend area. For example, drag "Data Center" to create bars for each data center.
1. Drag a metric into the Values area. For example, drag "Cost" to measure costs.
1. (Optional) For trend charts, drag a time field into the Axis area.
1. To change the chart type, click the Ad Hoc tab and select a chart style from the Visualize section (Bar, Column, Stacked Bar/Column, Pie, Line).

## Expected Results

- The chart displays your data visually
- Hovering over chart elements shows tooltips with values
- Clicking legend items hides/shows that series

## Common Pitfalls

- Pie charts with negative numbers: Pie charts can't display negative values. If your data might contain negatives, use a bar chart instead.
- Too many legend items: Charts with more than 7–10 series become hard to read. Use filters or switch to a table.
- Missing trend data: If your trend chart looks wrong, verify that the time field is in the Axis area, not the Legend.
