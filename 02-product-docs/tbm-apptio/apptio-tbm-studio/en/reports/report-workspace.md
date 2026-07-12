---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "The report workspace"
breadcrumb: []
source_path: "reports/report-workspace.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# The report workspace

Applies to: TBM Studio 12.0 and later

The report workspace is divided into three panes.

- Project Explorer: Use to select a report you want to edit.
- Component Configuration panel: Use to add columns and values to a table
  or chart.
- Report Editing workspace: Build your report in this panel by adding
  tables and charts.

  ![](../../resources/images/studio_images/studioimages/reports/studio_reports_workspace_800x397.png)

## Project Explorer

The Project Explorer pane displays the documents that are available. The
documents are grouped into sections:

- Tables
- Metrics
- Perspctives
- Reports

When working with reports, you will be focused on the Reports section.

To display the Project Explorer pane, do one of the following.

1. In TBM Studio 12.2+: Open the Project/Applications menu and click TBM Studio.

   ![](../../resources/images/studio_images/studioimages/access_tbm_studio.png)
2. In versions prior to TBM Studio 12.2: click the Studio Mode icon at the right side of the Global
   header.

To change the width of the Explorer pane, drag the right-border handle.

To minimize the Explorer pane, click the minimize arrow in the upper-right corner.

To find a report in the Project Explorer, enter text in the Report section filter.

## Component Configuration panel

Use the Component Configuration panel to build the tables and charts you add to reports.
To build the tables and charts, drag values from the Project Explorer into the areas of the
pane.

To build a table or chart, drag fields from the Project Explorer into the
areas at the bottom of the dialog. The four areas are described below.

- Rows - Provides the entries for the first column in the table or the
  x-axis in a chart. If there are duplicate entries in the source, the entries are grouped and a
  single entry for each unique value is displayed. If you add more than one field to the area,
  sub-groups are created in the first column of the table.
- Values - Provides the data displayed in the body of the table or chart.
  You can hide a value by right-clicking the value and selecting Hide.
- Columns - Provides the column headers for the table. Drag one field here
  from a perspective. Only one field can be put in the Columns area.
- Filters - Filters the entries in a column in the table or chart. Drag
  fields here from perspectives and other areas. If you use a metric, you can right-click on the
  metric and set the number range.
  - Multiple fields can be added to all areas except the Columns area. If a
    field cannot be applied to an area, a warning message is displayed.
  - To remove a field from an area, drag it out of the area or right-click on the field and select
    Remove.

## Report editing workspace

Use the Report Editing workspace panel to build the report by adding tables, charts, and
other report components. To add components, click the Report tab, and click a component.
