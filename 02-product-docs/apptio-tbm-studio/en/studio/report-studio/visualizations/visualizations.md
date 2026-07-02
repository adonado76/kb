---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Visualizations Overview"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
source_path: "studio/report-studio/visualizations/visualizations.html"
images:
  - "resources/images/studio_images/cv-2b.png"
  - "resources/images/studio_images/num-prec.png"
  - "resources/images/studio_images/zero-filter.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visualizations Overview

Visualizations help you represent data visually, so trends, patterns, and comparisons
are easier to understand at a glance. Report Studio provides a range of visualization types that
work seamlessly with filters, slicers, and drill navigation to support interactive analysis.

## What You Can Do with Visualizations

With visualizations, you can:

- Compare values across categories
- Identify trends and changes over time
- Highlight patterns and outliers
- Enable interactive exploration through filtering and drill navigation

## Supported Visualization Types

Report Studio supports multiple visualization types, including:

- KPIs, Tables and Editable Tables
- Bar and Column Charts
- Stacked Bar and Stacked Column Charts
- Line Charts
- Pie Charts
- Column + Line and Stacked Column + Line Charts

## Compatible Visualizations

Compatible Visualizations feature allows you to quickly switch between compatible chart
types without rebuilding your visualization. This helps you experiment with different visual
formats and find the one that best represents your data.

**Steps to use** 

1. Select a chart
   1. Click on a chart (for example, a Bar chart) in your report.
2. Use the conversion option
   1. On the widget header, locate the Compatible Visualizations icon.
   2. Select the icon to view a list of compatible visualizations for the selected chart
      type.

      ![image of compatible visualizations](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cv-2b.png)
3. Select a visualization type
   1. Select from options such as:
      1. Column chart
      2. Stacked Bar chart
      3. Stacked Column chart
   2. The chart updates instantly to the chosen visual type, retaining existing data,
      formatting, and configuration.

## Zero Filters

Zero-value filters are now supported for chart visualizations, allowing users to include or
exclude data points with zero values during analysis. This provides greater flexibility in focusing
on relevant trends, reducing visual noise, and improving the overall readability and interpretation
of chart data. image for zero filter in tables

![image for zero filter in tables](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/zero-filter.png)

## Numeric Precision for Cartesian Charts

You can control the number of decimal places displayed for values in Cartesian charts using the
**Numeric Precision** setting available in the **Format Panel** of the chart. The setting
accepts formatting patterns such as:

- #.00 → Displays values with 2 decimal places
- Example: 10 → 10.00

This enhancement helps improve readability and consistency of numeric values displayed in
charts.

Note: Numeric Precision formatting is currently supported only for **Cartesian charts**.

![numeric precision for Cartesian charts](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/num-prec.png)
