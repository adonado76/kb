---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Hierarchical and Cascading Filters"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
source_path: "studio/new-uc/reference/report-studio-reference/h-c-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Hierarchical and Cascading Filters

**Creating a Hierarchical Slicer**

Hierarchical slicers enable drill-down filtering through multiple classification levels.

**Prerequisites:**

- Custom perspective with grouped fields
- Fields ordered to represent hierarchy levels

**Steps:**

1. Create a custom perspective group containing the hierarchy fields
2. Order fields using sequential prefixes (e.g., 01\_Type, 02\_SubType, 03\_OS)
3. On the Report tab, click Row Slicer
4. Drag the perspective group (not individual fields) into the Slice By area

**Note:** You cannot use dashes (-) in field names. Use colons (:) or underscores (\_) instead.

**Hierarchy Code Search**

For fields representing hierarchy codes (e.g., account codes, cost center IDs), enable special
grouping behavior:

1. Right-click the field in the custom perspective
2. Select Edit '[field name]'
3. Check Represents a hierarchy code

**Behavior:** When a user enters text in the slicer search, the system finds all values
beginning with that text plus one additional character, creates a group entry for each unique
combination, and selecting a group filter to all matching values.

**Parent topic:** [Report Components: Filters and Slicers](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
