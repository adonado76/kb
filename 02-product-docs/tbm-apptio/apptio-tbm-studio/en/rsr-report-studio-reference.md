---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Report Studio Reference"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Studio Reference"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/report-studio-reference.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Report Studio Reference

## Overview

Report Studio enables you to create interactive reports that present data from your models to stakeholders. Reports can include tables, charts, and a variety of components for filtering, navigation, and data entry. This reference section provides comprehensive documentation for all Report Studio features and components.

Use this section to look up specific component properties, configuration options, and technical details. For step-by-step instructions on creating reports, see Section 3.3 Create Reports .

## Key Capabilities

- Data Visualization: Display model data using configurable tables and charts with drill-through navigation
- Interactive Filtering: Enable data discovery through slicers, column pickers, and quick pivots
- Data Entry: Allow end users to input data directly through editable tables and upload components
- Consistent Branding: Apply master reports and custom color palettes for organizational standards
- Access Control: Manage report visibility through role-based permissions

## Section Contents

This section contains 11 subsections covering all Report Studio components and features:

| Topic | Description |
| --- | --- |
| Topic | Description |
| Tables | Configure object-based and transform tables, add columns (formula, calculated, calendar, sparkline, total), set grouping, sorting, and table properties including conditional formatting and navigation links. |
| Charts | Create visualizations including bar, stacked bar, column, stacked column, line, pie, KPI, treemap, and waterfall charts. Configure color palettes, legends, and chart-to-report navigation. |
| Filters and Slicers | Add slicers for interactive filtering, configure compact slicers, column pickers, and quick pivots. Enable data discovery through dynamic filter combinations. |
| Navigation | Create drill-through links between reports, configure Wiki-style navigation buttons, build report collection navigators, and set up modal pop-up reports. |
| Input Components | Add buttons, HTML text boxes, notes, group boxes, and tabbed components. Configure Table Upload components for end-user data entry without Studio access. |
| Editable Tables | Configure editable table report components for direct data entry. Set up dropdown lists, possible values, cell locking, upload permissions, and publish workflows. |
| Report Properties | Configure report settings including active status, report type (breakdown, filtered, unit), auto-search fields, calculation options, and advanced properties. |
| Layout | Apply dynamic sizing and positioning options (center, fill, dock). Configure responsive layouts, tabbed group visibility, and component arrangement within containers. |
| Master Reports | Create and apply master reports for consistent layouts. Use standard master reports or create custom templates with reusable containers, buttons, and branding elements. |
| Report Collections | Create and manage report collections to group related reports. Add/remove reports, configure collection navigators, and control report visibility within collections. |
| Report Permissions | Configure role-based access control for reports. Set view, edit, and delete permissions at report and collection levels. Manage component visibility by role. |

## Navigation Guidance

Using This Reference

This section is organized as a reference guide for looking up specific details about Report Studio features. Navigate to the relevant subsection based on what you need to accomplish:

- Building data displays: See Tables and Charts
- Adding interactivity: See Filters and Slicers and Navigation
- Enabling data entry: See Input Components and Editable Tables
- Customizing appearance: See Report Properties and Layout
- Standardizing reports: See Master Reports
- Managing access: See Report Collections and Report Permissions

Related Sections

For task-oriented guidance on creating and customizing reports, refer to these how-to sections:

- Report Basics Step-by-step instructions for creating reports , adding tables and charts
- Report Customization Procedures for custom perspectives , collections , and master reports
- Advanced Reporting Guidance on drill-through reports , editable components , and exports

## Prerequisites

Before working with Report Studio, ensure:

- Data has been uploaded through Data Studio
- Allocation models have been built in Model Studio (for object-based reports)
- You have appropriate role permissions (Admin or Power User for editing; Business User for viewing)
- The project has calculated data for the time period you want to report on

## Component Configuration Panel

When building tables and charts, you use the Component Configuration panel to define what data appears. The panel includes four main areas: Rows (grouping dimension), Values (metrics to display), Columns (time periods), and Filters (data restrictions). Drag fields from the Project Explorer into these areas to configure your report components. The panel displays differently for Power Users (full access) versus Analysts (custom perspectives only).
