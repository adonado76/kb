---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create Your First Report"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Quick Start"
source_path: "studio/report-studio/create-first/first-report.html"
images:
  - "resources/images/studio_images/nrs-fc-1.png"
  - "resources/images/studio_images/nrs-fc-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create Your First Report

This guide walks through creating a new report in the new Report Studio. By the end of
this guide, you will have a report with components and visualizations ready to view and share.

1. Navigate to the New Reports Tab
   1. Go to the **New Reports** tab on the landing page
   2. Click the **New** button and select **Report**
2. Enter Report Details
   1. **Report Name** – Give your report a meaningful name.
   2. **Description (Optional)** - Add a short description to help users understand the
      report’s purpose.
   3. **Viewable by** – This property controls who can see and access the report.
      - Everyone – The report is visible to all users with access to the reporting area.
      - Only Me – The report is visible only to you. Useful for drafts, experimentation,
        or personal analysis.
      - Select Roles – The report is visible only to users assigned to the selected roles.
        Roles are selected from a drop-down list. Enables role-based access control for
        reports.
3. Add Components
   1. On the toolbar, select a component from the Components menu.
   2. Choose from the available component types, such as:
      - Slicer
      - Column Picker
      - Quick Pivot
      - HTML
      - Tabs
      - Group
   3. Pick a Slicer
   4. When the slicer is added, the Data and Format panels open on the right.
      1. Data panel is used to configure the data that drives the slicer.
      2. Format panel is used to customize the appearance and formatting of the slicer.
   5. Configure data
      1. In the data panel, select a data model object from the drop-down.
      2. Click “Click here or drag to add data” to open the Dimension Explorer.
         - The Dimension Explorer displays Tables, Editable Tables, Metrics and Time.
      3. Choose the dimension you want to slice the data by.
      4. Drag a dimension from Tables into the Data panel.
      5. Use the filters section to apply additional filtering criteria to the slicer.

      ![image of the data panel](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/nrs-fc-1.png)

   Once configured, the slicer filters the report based on the selected dimension.
4. Add Visualizations
   1. On the toolbar, select a visualization from the Visualizations menu
   2. Choose from the available visualizations:
      - KPI
      - Table
      - Editable Table
      - Bar chart
      - Stacked Bar chart
      - Column chart
      - Stacked Column chart
      - Line chart
      - Pie chart
   3. Select Table
   4. Configure data
      1. In the data panel, select a data model object from the drop-down.
      2. Configure the Rows, Columns, Values sections of the data panel by adding
         dimensions directly from the Dimension Explorer.
      3. Use the filters section to apply additional filtering criteria to the table.

      ![image of the configured data in the table](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/nrs-fc-2.png)
5. Save your Report
   1. Since Autosave is enabled, your changes will be saved automatically as you build the
      report.
   2. You can also manually click **Save** at any time to ensure your work is saved
      immediately.
