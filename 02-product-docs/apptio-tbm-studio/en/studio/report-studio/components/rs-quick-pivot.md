---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Quick Pivot"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
source_path: "studio/report-studio/components/rs-quick-pivot.html"
images:
  - "resources/images/studio_images/quick-pvt.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Quick Pivot

The Quick Pivot works similar to a Pivot table in Excel, allowing users to dynamically
change how data is grouped and summarized in a table.

## When to use Quick Pivot

Use Quick Pivot when you want to:

- Group data by different dimensions on the fly
- Compare metrics across alternate breakdowns

## Add a Quick Pivot to the Report

1. Add a Quick Pivot from the Components pane on the toolbar
2. Click on the Quick Pivot to enable the Data and Format panels.
3. Data Panel
   1. Select the model object from the dropdown list
   2. Drag dimensions from the Dimension Explorer to the pivots section in the data panel
4. Format Panel
   1. General Properties – See [Component
      Properties](components.html#abt-comp__comprop)

Example: Quick Pivot

![quick pivot](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/quick-pvt.png)

Quick Pivot supports custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")
