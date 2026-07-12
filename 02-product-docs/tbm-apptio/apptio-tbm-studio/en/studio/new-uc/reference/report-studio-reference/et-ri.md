---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Editable Table + Report Integration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/et-ri.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editable Table + Report Integration

Editable table components interact with other report elements and the data pipeline.

**Impact on Other Report Components**

Changes to editable table data do not immediately affect other report components:

- Charts and tables linked to transform tables show data from the last publish

- Saved but unpublished changes are only visible in the editable table component

- After publishing, a build or calculation must complete before other components reflect changes

**Refresh Behavior**

After saving or publishing:

- The editable table component refreshes automatically
- Other components may require manual refresh or a full report reload
- For real-time updates, configure recurring publish schedules

**Calculated Columns**

You can add formula columns to editable table components:

- Calculated columns can reference editable column values
- Values update as users enter data
- Formula columns are always read-only

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
