---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Editable Table Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/editable-table-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editable Table Configuration

Configuring an editable table component involves connecting to a data source, selecting columns,
and setting up editing behaviors.

**Data Source Connection**

To add an editable table component to a report:

1. Check out the report in Report Studio
2. Navigate to the Report tab and select the Editable Table component
3. From the Component Configuration panel, select the editable table from the Tables perspective
4. Drag columns from the table into the Included Columns area

Tip: Only tables created as editable tables in Data Studio will appear as valid sources
for editable table components.

**Column Mapping**

When configuring the component, you control which columns are visible and in what order:

- **Included Columns:** Drag columns from the source table to make them visible in the report
- **Column Order:** Rearrange columns by dragging them within the Included Columns area
- **Hidden Columns:** Columns not included remain in the underlying table but are not displayed

System columns such as .PK (primary key), .Username, and .EditDate can be shown or hidden by
right-clicking on the column header and selecting Show or Hide.

**Row Filtering**

You can limit which rows appear in the editable table component:

- Drag filter columns into the Filters area of the Component Configuration panel
- Right-click the filter and select Edit Filter to specify filter values
- Filters can be static (fixed values) or linked to slicers for dynamic filtering

Warning: *When Row-Level Security (RLS) is active, users only see rows they are
authorized to view, regardless of report-level filters.*

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
