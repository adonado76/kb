---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Bubble Charts"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Bubble Charts"
source_path: "SSWRJM/studio/report-studio/visualizations/bubblecharts.html"
images:
  - "03-media/apptio-tbm-studio/bc1.png"
  - "03-media/apptio-tbm-studio/bc2.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Bubble Charts

*Bubble charts help you visualize the relationship between multiple measures in a single view. Each bubble represents an entity, with its position determined by two measures and its size determined by a third measure. This makes it easy to identify patterns, correlations, clusters, and outliers across your data.*

## Create a bubble chart

To create a bubble chart:

1. Add a Bubble Chart visualization to your report.
1. Configure the required fields: X-axis – A numeric measure that determines the horizontal position of each bubble. Y-axis – A numeric measure that determines the vertical position of each bubble. Size – A numeric measure that determines the size of each bubble. Entity/Category – A dimension that defines each individual bubble (for example, Application, Product, or Region).
1. Optionally, add Filters to restrict the data displayed in the visualization.

Each bubble represents a single entity and is plotted based on its associated measure values.

## Data requirements

A bubble chart requires:

- One numeric measure for the X-axis
- One numeric measure for the Y-axis
- One numeric measure for Size
- One Entity/Category dimension

Only one Entity/Category dimension is supported, and at least one data point is required to render the visualization.

## Chart behaviour

- The X-axis determines the horizontal position of each bubble.
- The Y-axis determines the vertical position of each bubble.
- The Size measure controls the relative size of each bubble.
- Each value in the Entity/Category dimension is represented as a separate bubble.

Data points with missing X-axis or Y-axis values are not displayed.

## Tooltips and interactions

Hover over a bubble to view its details, including:

- Entity/Category
- X-axis value
- Y-axis value
- Size value

## Sorting

Bubble charts support sorting based on:

- X-axis values
- Y-axis values
- Size values

By default, bubbles are rendered in the order provided by the dataset unless an alternative sort order is applied.

Compatibility

Bubble charts integrate with other New Report Studio capabilities, including:

- Slicers
- Column Pickers
- Quick Pivots

This enables interactive exploration and comparison of entities across multiple dimensions and measures within a single visualization.

alt
