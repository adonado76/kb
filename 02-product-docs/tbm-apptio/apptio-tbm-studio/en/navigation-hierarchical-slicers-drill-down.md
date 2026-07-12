---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Hierarchical Slicers for Drill-Down"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Navigation"
  - "Hierarchical Slicers for Drill-Down"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/hs-drilldown.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Hierarchical Slicers for Drill-Down

Hierarchical slicers provide a navigation-like experience within a single report, allowing users to drill down through data hierarchies. Unlike drill-through navigation to other reports, hierarchical slicers filter the current report at increasing levels of detail.

Creating a Hierarchical Slicer

1. Create a custom perspective group with fields ordered from highest to lowest level
1. Rename fields with numeric prefixes to control order (e.g., 01_Type, 02_SubType, 03_OS)
1. On the Report tab, click Row Slicer
1. Drag the perspective group into the Slice By area
