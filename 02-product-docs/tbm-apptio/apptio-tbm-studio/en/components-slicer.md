---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Slicer"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
  - "Slicer"
source_path: "SSWRJM/studio/report-studio/components/rs-compact-slicer.html"
images:
  - "03-media/apptio-tbm-studio/slicer.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Slicer

*A Slicer lets users interactively filter data in a report by selecting one or more values from a dimension. Slicers apply their selections across all supported components and visualizations in the report, enabling focused analysis without modifying the report structure. Slicers are also applicable in Editable tables.*

## When to use a Slicer

- Filter a report by a single dimension (for example – Application Family, Region, Cost Centre or Time)
- Quickly change the context of the data

## Add a Slicer to the Report

1. Add a Slicer from the Components pane on the toolbar
1. Click on the Slicer to enable the Data and Format panels.
1. Data Panel Select the model object from the dropdown list Drag a dimension from Dimension Explorer into the Slice by field. This defines the dimension that controls the slicer. Add one or more filters to restrict slicer options. This is useful when you want to expose a controlled subset of values to users.
1. Format Panel General Properties – See Component Properties Slicer-specific Properties Search Contains - Finds all values that include the entered characters. Starts With - Finds all values that begin with the entered characters. Slicer Type Drop-down Displays slicer values in a compact drop-down list. Suitable when there are many slicer values. Expand the list to make a selection. Vertical list Displays slicer values as a visible list. Shows all values at a glance. Enables faster selection without expanding a menu. Sort ABC/123 State Quick Size Options Large, Medium, Small

Example: Slicer

Slicer supports custom formulas and formula dimensions. For more details, see Custom Formulas
