---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Report Components: Editable Tables in Reports"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
source_path: "studio/new-uc/reference/report-studio-reference/report-component-editable-components.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Report Components: Editable Tables in Reports

The Editable Table report component enables data entry workflows directly within the reporting
interface. Users can enter, modify, and publish data without requiring access to TBM Studio, making
it ideal for distributed data collection scenarios such as budget entry, data enrichment, and data
classification workflows.

## Editable Table Component Overview

The Editable Table report component displays data from an underlying editable table (created in
Data Studio) and allows authorized users to modify that data directly from a report. Understanding
how this component differs from other table types is essential for proper implementation.

**Difference from Standard Report Tables**

Standard tables in reports (Section 5.3.1) display read-only data from transform tables or model
objects. Key differences with editable table components include:

- Standard tables cannot be modified by end users; editable table components allow direct data
  entry
- Standard tables display calculated or aggregated data; editable tables store user-entered values
- Standard tables update automatically when data sources change; editable tables require explicit
  save and publish actions
- Editable tables include additional controls for add row, delete row, save, and publish
  operations

**Difference from Data Studio Editable Tables**

Editable tables are defined in Data Studio (Section 5.1) and exposed through report components.
The relationship works as follows:

- Data Studio: Defines the editable table schema, column types, validation rules, and possible
  values
- Report Studio: Creates the user-facing component that displays and enables editing of the table
- The report component inherits column definitions from the Data Studio configuration
- Report-level settings control which columns are visible, editable, and how data is presented

**Common Use Cases**

Editable table components are ideal for the following scenarios:

- **Budget entry:** Enable cost center managers to enter budget forecasts directly into reports
- **Data enrichment:** Allow users to add classifications, categories, or mappings to imported
  data
- **Labor mapping:** Enable HR or finance teams to assign personnel to cost centers or projects
- **Variance explanations:** Capture justifications for budget variances from department heads
- **Approval workflows:** Track approval status and comments for line items

- **[Editable Table Configuration](../../../../studio/new-uc/reference/report-studio-reference/editable-table-config.html)**
- **[Column Editing Options](../../../../studio/new-uc/reference/report-studio-reference/column-editing-options.html)**
- **[Validation Configuration](../../../../studio/new-uc/reference/report-studio-reference/validation-config.html)**
- **[Row Operations](../../../../studio/new-uc/reference/report-studio-reference/row-operations.html)**
- **[Save Behavior](../../../../studio/new-uc/reference/report-studio-reference/save-behavior.html)**
- **[Edit Permissions](../../../../studio/new-uc/reference/report-studio-reference/edit-permissions.html)**
- **[Styling Editable Tables](../../../../studio/new-uc/reference/report-studio-reference/styling-editable-tables.html)**
- **[Editable Table + Report Integration](../../../../studio/new-uc/reference/report-studio-reference/et-ri.html)**
- **[Common Patterns](../../../../studio/new-uc/reference/report-studio-reference/common-patterns.html)**
- **[Troubleshooting](../../../../studio/new-uc/reference/report-studio-reference/editable-troubleshoot.html)**
