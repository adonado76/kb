---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Hierarchical and Cascading Filters"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
  - "Hierarchical and Cascading Filters"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/h-c-filter.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Hierarchical and Cascading Filters

Creating a Hierarchical Slicer

Hierarchical slicers enable drill-down filtering through multiple classification levels.

Prerequisites:

- Custom perspective with grouped fields
- Fields ordered to represent hierarchy levels

Steps:

1. Create a custom perspective group containing the hierarchy fields
1. Order fields using sequential prefixes (e.g., 01_Type, 02_SubType, 03_OS)
1. On the Report tab, click Row Slicer
1. Drag the perspective group (not individual fields) into the Slice By area

Note: You cannot use dashes (-) in field names. Use colons (:) or underscores (_) instead.

Hierarchy Code Search

For fields representing hierarchy codes (e.g., account codes, cost center IDs), enable special grouping behavior:

1. Right-click the field in the custom perspective
1. Select Edit '[field name]'
1. Check Represents a hierarchy code

Behavior: When a user enters text in the slicer search, the system finds all values beginning with that text plus one additional character, creates a group entry for each unique combination, and selecting a group filter to all matching values.
