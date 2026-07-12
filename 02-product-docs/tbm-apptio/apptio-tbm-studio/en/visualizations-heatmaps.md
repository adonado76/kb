---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Heatmaps"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Heatmaps"
source_path: "SSWRJM/studio/report-studio/visualizations/heatmaps.html"
images:
  - "03-media/apptio-tbm-studio/heatmap1.png"
  - "03-media/apptio-tbm-studio/heatmap2.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Heatmaps

*Heatmaps provide a visual way to analyse data by representing aggregated measure values as color intensity across two dimensions. By displaying values in a color-coded grid, heatmaps make it easy to identify patterns, trends, hotspots, and anomalies.*

## Create a heatmap

To create a heatmap:

1. Add a Heatmap visualization to your report.
1. Configure the required fields: Rows – The dimension displayed on the Y-axis (for example, Region or Department ). Columns – The dimension displayed on the X-axis (for example, Product or Month ). Values – The numeric measure used to determine the color intensity of each cell.
1. Optionally, add Filters to limit the data displayed in the visualization.

Each cell in the heatmap represents the aggregated value for the corresponding row and column combination.

## Color encoding

Heatmaps use color intensity to represent the magnitude of a measure:

- Higher values are displayed with more intense colors.
- Lower values are displayed with lighter colors.
- Color scaling is applied across all visible cells in the visualization.
- Depending on the selected configuration, the heatmap can use: Sequential color scales to represent values from low to high. Diverging color scales to represent negative, neutral, and positive values.

Cells with no available data are displayed using a default "no data" appearance.

## Sorting

You can sort the heatmap by:

- Row dimension
- Column dimension
- Measure values

By default:

- Input order is preserved.
- Time-based dimensions are sorted chronologically.
- You can override the default sort order as needed.

## Hover information

Hovering over a cell displays additional details, including:

- Row value
- Column value
- Aggregated measure value

## Requirements and limitations

- A heatmap requires at least one Row dimension and one Column dimension.
- The Values field must contain a numeric measure.
- Only one measure can be used in a heatmap.
- Data must support aggregation at the intersection of the selected row and column dimensions.

Compatibility

Heatmaps are fully supported within the New Report Studio and can be used alongside features such as:

- Slicers
- Column Pickers
- Quick Pivots

This enables you to interactively explore and analyse patterns across large datasets using a compact, intuitive visual representation.
