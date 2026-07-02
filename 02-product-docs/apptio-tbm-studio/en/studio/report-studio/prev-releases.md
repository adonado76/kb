---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Previous Releases"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Release Notes"
source_path: "studio/report-studio/prev-releases.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Previous Releases

## 12.11.21 - April 2026

Attention: The new report studio is now generally available, offering a modern,
intuitive experience for creating, customizing, and consuming reports. This release enables
end-to-end adoption, including report creation, migration, and sharing.

- **Admin Control for New Report Viewer Access:** Admins can now control whether end users have
  access to the Report Viewer. This setting is enabled by default, ensuring end users can view
  reports. Admins can disable it from the Project settings if they wish to restrict access.
- **Button Component:** Adds a configurable button component in the Report Studio that allows
  users to trigger actions such as navigation and script execution on click. Includes flexible
  formatting options to customize the appearance and behaviour of buttons within reports.
- **Tab Visibility Rules:** Configure visibility expressions for tabs within a tabbed group
  component. Tabs will dynamically show or hide in the Report Viewer based on the defined conditions.
- **Share Axis in Overlay Charts:** Overlay charts now support a shared axis, enabling multiple
  data series to be aligned on a common scale for easier comparison and improved readability.
- **Auto-Wrapping for Table Headers and Cells:** Tables & Editable Tables now support
  auto-wrapping of text in both column headers and cells, improving readability and ensuring content
  is fully visible without manual resizing.
- **Saved Views in Report Viewer:** Save personalised snapshots of reports with your preferred
  filters and interactions. Easily switch between views or set a landing view for faster navigation.
- **Email Report in Report Viewer:** Users can now send reports directly from the report viewer
  via email. The report can be shared as a PDF attachment or as a link to view or download the PDF.
- **Migration Assistant for Reports:** Use the Migration Assistant to migrate reports from
  classic TBM studio to the new Report Studio.
- Introduced OOTB Report Collections in Public Preview.

## 12.11.20 - February 2026

- **Show Values in Tables:** Explore column-level data distribution by viewing unique
  values and their counts from the column menu.
- **Tree View for Tables**: Tables now support a new Tree View option that lets you
  visualise hierarchical data with expandable and collapsible rows.
- **Export Reports to PDF:** You can now export reports to PDF directly from the New
  Report Studio via **File -> Download as -> PDF**, enabling quick sharing without
  switching to the Report Viewer.
- **Export Tables to Excel:** You can now export individual tables from a report
  directly to Excel via the table’s overflow menu, making it easier to analyse and share
  report data outside the application. Currently available in the New Report Viewer.
- **Multi-currency Support:** Multi-currency support is now available in Report Studio
  and Report Viewer. Admins can test reports using different currencies and rate types, and
  users can switch currencies in the viewer – with selections reflected in PDF and Excel
  reports.

## 12.11.19 - January 2026

**Report & Report Collection creation with visibility settings**

- Reports now include a **Viewable by** setting during creation, allowing you to
  control whether a report is visible to everyone, only you or specific roles.
- Report collections now support a **Viewable by** property, allowing visibility to
  be restricted to everyone, only you, or selected roles.

**Report Canvas Panel Layout Update** - The dimension explorer, data and format panels
for components and visualisations have moved from right side to the left side of the report
canvas.

**Report Components Enhancements**

- Table - Support for compatible visualizations
- Slicer - Added a new Slicer Type property to slice components with drop-down and
  vertical list options, enabling flexible presentation based on report layout and user
  interaction needs.
- KPI - KPIs now support independent display of primary and secondary metrics, allowing
  you to show each metric on its own instead of only in a comparison view.
- KPIs, Column Pickers, Quick Pivots now support custom formulas.

**Visualisations**

- Column + Line charts
- Stacked Column + Line charts
- Chart data sorting – Charts now support configurable data sorting, allowing you to
  sort data by a selected value in ascending or descending order from the data panel.

**Enhanced widget debugging & data refresh options** - Added new widget header
actions to refresh data, view full data paths, and open debug data in /data for easier
troubleshooting and validation.

**Export reports to PDF** - The report viewer allows you to export the currently viewed
report to a PDF file, making it easy to download, share, or archive the report in a
printable format.

## 12.11.18 - November 2025

- **Localization Support** - Added localization support across the new Report Studio
  experience, allowing users across regions to experience a seamless and consistent interface
  in their preferred language and format.
- **New Components** - Group component to organize and manage multiple report components
  on the canvas as a single unit.
- **Table Enhancements**
  - Ability to **rename columns** directly within tables.
  - Support for **zero filters** to explicitly include or exclude zero values.
  - Option to **hide intermediate dimensions** to simplify table views.
  - Enhancements to **editable tables** for improved data entry and usability.
- **Column Picker Enhancements** - Column Picker now supports date-based selection, allowing
  users to control date columns dynamically.
- **Visualizations & Interactions** - Support for compatible visualizations with
  drill navigation enabled in charts for deeper data exploration.
