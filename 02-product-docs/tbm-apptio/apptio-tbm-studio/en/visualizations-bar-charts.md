---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Bar Charts"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Bar Charts"
source_path: "SSWRJM/studio/report-studio/visualizations/rs-bar.html"
images:
  - "03-media/apptio-tbm-studio/rs-bar.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Bar Charts

*A bar chart displays values as horizontal bars, making it easy to compare metrics across categories. Bar charts are especially effective when comparing values across many categories.*

## When to use a Bar Chart

- Compare values across multiple categories
- Rank categories from highest to lowest
- Highlight differences clearly at a glance

## Add a Bar Chart to a Report

1. Add a Bar Chart from the Visualizations pane on the toolbar
1. Click on the Bar Chart to enable the Data and Format panels.
1. Data Panel Select the model object from the drop-down menu Categories – Defines how data is grouped along the axis using a dimension. Click here or drag to add dimensions from the Dimension Explorer Values – Specifies the metric(s) displayed as bars Legend – Splits values into multiple series based on a dimension. Filters – Limits the data displayed in the chart based on selected conditions Results to display – Indicate the number of bars to display Configure Sorting – Controls the order of bars by value in ascending or descending order.
1. Format Panel General Properties – See Component Properties Bar chart specific Properties Categories Show category title Show category labels Choose the Font size, style (bold, italics, underline) and color Toggle to switch categories position Show grid lines Values Show values title Show values labels Choose the Font size, style (bold, italics, underline) and color Toggle to invert range Show grid lines Legend Toggle to show the legend Font size and style for the legend (bold, italics, underline) Color of the legend text (with option to reset the color) Bars Padding between bars (thickness of the bars) Padding between groups (spacing between groups) Data Labels Toggle to show the data labels – the options are inside or outside the bar. Choose the Font size, style (bold, italics, underline) and color Set colors automatically – automatically assigns colors to bars based on the selected data and theme. Define a label outline and color

Example: Bar chart

Bar charts support custom formulas and formula dimensions. For more details, see Custom Formulas

Bar charts also support compatible visualizations. For more details, see Compatible Visualizations .

## Stacked Bar Charts

Bar charts can be converted to stacked bars to show sub-category contributions within each category, while keeping the total value visible.
