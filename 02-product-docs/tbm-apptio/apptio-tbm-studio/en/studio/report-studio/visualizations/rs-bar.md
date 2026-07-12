---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Bar Charts"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
source_path: "studio/report-studio/visualizations/rs-bar.html"
images:
  - "resources/images/studio_images/rs-bar.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Bar Charts

A bar chart displays values as horizontal bars, making it easy to compare metrics across
categories. Bar charts are especially effective when comparing values across many categories.

## When to use a Bar Chart

Use a bar chart when you want to:

- Compare values across multiple categories
- Rank categories from highest to lowest
- Highlight differences clearly at a glance

## Add a Bar Chart to a Report

1. Add a Bar Chart from the Visualizations pane on the toolbar
2. Click on the Bar Chart to enable the Data and Format panels.
3. Data Panel
   1. Select the model object from the drop-down menu
   2. Categories – Defines how data is grouped along the axis using a dimension. Click
      here or drag to add dimensions from the Dimension Explorer
   3. Values – Specifies the metric(s) displayed as bars
   4. Legend – Splits values into multiple series based on a dimension.
   5. Filters – Limits the data displayed in the chart based on selected conditions
   6. Results to display – Indicate the number of bars to display
   7. Configure Sorting – Controls the order of bars by value in ascending or descending
      order.
4. Format Panel
   1. General Properties – See [Component Properties](../components/components.html#abt-comp__comprop)
   2. Bar chart specific Properties
      1. Categories
         1. Show category title
         2. Show category labels
         3. Choose the Font size, style (bold, italics, underline) and color
         4. Toggle to switch categories position
         5. Show grid lines
      2. Values
         1. Show values title
         2. Show values labels
         3. Choose the Font size, style (bold, italics, underline) and color
         4. Toggle to invert range
         5. Show grid lines
      3. Legend
         1. Toggle to show the legend
         2. Font size and style for the legend (bold, italics, underline)
         3. Color of the legend text (with option to reset the color)
      4. Bars
         1. Padding between bars (thickness of the bars)
         2. Padding between groups (spacing between groups)
      5. Data Labels
         1. Toggle to show the data labels – the options are inside or outside the bar.
         2. Choose the Font size, style (bold, italics, underline) and color
         3. Set colors automatically – automatically assigns colors to bars based on the
            selected data and theme.
         4. Define a label outline and color

Example: Bar chart

![bar chart sample](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-bar.png)

Bar charts support custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")

Bar charts also support compatible visualizations. For more details, see [Compatible Visualizations](visualizations.html#abt-visual__compvis).

## Stacked Bar Charts

Bar charts can be converted to stacked bars to show sub-category contributions within each
category, while keeping the total value visible.
