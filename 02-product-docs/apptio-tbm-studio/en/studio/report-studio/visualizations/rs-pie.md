---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Pie Charts"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
source_path: "studio/report-studio/visualizations/rs-pie.html"
images:
  - "resources/images/studio_images/rs-pie.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pie Charts

A pie chart displays data as slices of a circle, showing the relative proportions of
each category to the whole. It is ideal for illustrating percentage or part-to-whole
relationships.

## When to use a Pie Chart

Use a pie chart when you want to:

- Show proportions of a total for a small number of categories
- Highlight the largest or smallest segments
- Provide a quick visual comparison of parts to the whole

## Add a Pie Chart to a Report

1. Add a Pie Chart from the Visualizations pane on the toolbar
2. Click on the Pie Chart to enable the Data and Format panels.
3. Data Panel
   1. Select the model object from the drop-down menu
   2. Categories – Defines the slices of the pie using a dimension. Click here or drag to
      add dimensions from the Dimension Explorer
   3. Values – Specifies the metric(s) that determine slice size
   4. Filters – Limits the data displayed in the chart based on selected conditions
4. Format Panel
   1. General Properties – See [Component Properties](../components/components.html#abt-comp__comprop)
   2. Pie chart specific Properties
      1. Total
         1. Toggle to show the Total count.
         2. Font size and style for the legend (bold, italics, underline)
         3. Color of the total text (with option to reset the color)
      2. Data Labels
         1. Toggle to show the Label position – the options are Outside or Inside.
         2. Label content – Choose from the options - Category, Value, and Percentage.
         3. Choose the Font size, style (bold, italics, underline) and color
         4. Set colors automatically – automatically assigns colors to bars based on the
            selected data and theme.
         5. Define a label outline and color
      3. Legend
         1. Toggle to show the legend
         2. Font size and style for the legend (bold, italics, underline)
         3. Color of the legend text (with option to reset the color)

Example: Pie chart

![pie chart](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-pie.png)

Pie chart supports custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")
