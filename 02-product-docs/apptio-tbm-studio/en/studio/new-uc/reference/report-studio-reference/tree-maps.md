---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Tree Maps"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/tree-maps.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tree Maps

Tree maps display hierarchical data as nested rectangles, where the size of each rectangle
represents the relative magnitude of its value. This visualization excels at showing proportions and
making it easy to spot outliers or dominant categories at a glance.

**Single Value Tree Maps**

A basic tree map displays a single metric (such as cost) with rectangle sizes representing the
relative values for each category. This is useful for quickly identifying which items contribute the
most to a total.

**Variance Tree Maps**

Tree maps can display two values (such as Cost and Budget) with color indicating the variance
between them. A color scale helps viewers quickly identify which items are over or under budget.

**Variance calculation:** (First Value - Second Value) / Second Value

**Creating a Tree Map**

1. Create a table with the data you want to visualize.
2. On the Ad Hoc tab, select Tree Map.
3. Use the options on the Tree Map tab to configure the visualization.

\

Note: Tree maps support up to 4 columns in the legend. Custom color palettes cannot be applied
to tree maps.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
