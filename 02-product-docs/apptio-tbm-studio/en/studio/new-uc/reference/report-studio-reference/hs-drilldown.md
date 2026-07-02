---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Hierarchical Slicers for Drill-Down"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Navigation"
source_path: "studio/new-uc/reference/report-studio-reference/hs-drilldown.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Hierarchical Slicers for Drill-Down

Hierarchical slicers provide a navigation-like experience within a single report, allowing users
to drill down through data hierarchies. Unlike drill-through navigation to other reports,
hierarchical slicers filter the current report at increasing levels of detail.

**Creating a Hierarchical Slicer**

1. Create a custom perspective group with fields ordered from highest to lowest level
2. Rename fields with numeric prefixes to control order (e.g., 01\_Type, 02\_SubType, 03\_OS)
3. On the Report tab, click Row Slicer
4. Drag the perspective group into the Slice By area

**Parent topic:** [Report Components: Navigation](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
