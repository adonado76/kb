---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Editable Table Configuration"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
  - "Editable Table Configuration"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/editable-table-config.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Editable Table Configuration

Configuring an editable table component involves connecting to a data source, selecting columns, and setting up editing behaviors.

Data Source Connection

To add an editable table component to a report:

1. Check out the report in Report Studio
1. Navigate to the Report tab and select the Editable Table component
1. From the Component Configuration panel, select the editable table from the Tables perspective
1. Drag columns from the table into the Included Columns area

Column Mapping

When configuring the component, you control which columns are visible and in what order:

- Included Columns: Drag columns from the source table to make them visible in the report
- Column Order: Rearrange columns by dragging them within the Included Columns area
- Hidden Columns: Columns not included remain in the underlying table but are not displayed

System columns such as .PK (primary key), .Username, and .EditDate can be shown or hidden by right-clicking on the column header and selecting Show or Hide.

Row Filtering

You can limit which rows appear in the editable table component:

- Drag filter columns into the Filters area of the Component Configuration panel
- Right-click the filter and select Edit Filter to specify filter values
- Filters can be static (fixed values) or linked to slicers for dynamic filtering
