---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Slicer"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
source_path: "studio/report-studio/components/rs-compact-slicer.html"
images:
  - "resources/images/studio_images/slicer.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Slicer

A Slicer lets users interactively filter data in a report by selecting one or more
values from a dimension. Slicers apply their selections across all supported components and
visualizations in the report, enabling focused analysis without modifying the report structure.
Slicers are also applicable in Editable tables.

## When to use a Slicer

Use a Slicer when you want to:

- Filter a report by a single dimension (for example – Application Family, Region, Cost
  Centre or Time)
- Quickly change the context of the data

## Add a Slicer to the Report

1. Add a Slicer from the Components pane on the toolbar
2. Click on the Slicer to enable the Data and Format panels.
3. Data Panel
   1. Select the model object from the dropdown list
   2. Drag a dimension from Dimension Explorer into the Slice by field. This defines the
      dimension that controls the slicer.
   3. Add one or more filters to restrict slicer options. This is useful when you want to
      expose a controlled subset of values to users.
4. Format Panel
   1. General Properties – See [Component
      Properties](components.html#abt-comp__comprop)
   2. Slicer-specific Properties
      1. Search
         1. Contains - Finds all values that include the entered characters.
         2. Starts With - Finds all values that begin with the entered characters.
      2. Slicer Type
         - Drop-down
           - Displays slicer values in a compact drop-down list.
           - Suitable when there are many slicer
             values.
           - Expand the list to make a selection.
         - Vertical list
           - Displays slicer values as a visible list.
           - Shows all values at a glance.
           - Enables faster selection without expanding a menu.
      3. Sort
         1. ABC/123
         2. State
      4. Quick Size Options
         1. Large, Medium, Small

Example: Slicer

![slicer component](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/slicer.png)

Slicer supports custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")
