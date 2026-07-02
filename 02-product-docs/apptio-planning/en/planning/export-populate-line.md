---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Export and populate line-item tables or layouts"
breadcrumb: []
source_path: "planning/export-populate-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Export and populate line-item tables or layouts

In tables with line items, any user who can access the Services, Financial, or Projects views and
tabs can export that data to a .csv file. There are two levels of line-item data export:

![](../../resources/images/it%20planning_images/export_formatting_options.png)

- Export all (Recommended for bulk editing)

  Exports all editable fields
  in a format compatible for re-importing into the system. Use this option to make external updates or
  adjustments and re-import your changes.

  This export is only limited by the current level in
  the department hierarchy and by permissions set for Hide Sensitive Labor, and is not affected by
  filters or the time selector.

  [Learn more about Hide Sensitive Labor Data](faq-senslabdat.htm "(Opens in a new tab or window)")

  Note: To export all fields in the schema,
  configure a Layout with the desired fields and use the Export Layout option.
- Export Layout Only

  Exports the data visible in the selected layout,
  including all columns and filters defined in the layout.

  Note: The 'Created' column is included
  by default for "Export All" and "Export Layout Only" options.

Exported data is limited to data you can access, based on the following:

- For budget owners, their scope of Cost Object ownership (see [Manage Cost Object Permissions reference data](manage-cost-object.htm "(Opens in a new tab or window)")).
- Your role and permissions. For example, if your access to a page has been restricted.

Before exporting a populated table, customize the data organization. See [Customize, save, and share table
layouts](customize-save-share.htm "(Opens in a new tab or window)"). The Budget Process Owner and Admin can also customize the default layout for all
users. See [Create and share
custom table layouts](customize-save-share.htm "(Opens in a new tab or window)").

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.htm#Toolbar)
2. Select the required view from the navigation menu under Planning.
3. If your view includes tabs, select a tab.
4. At the upper right of the page, click Actions and select the Export option.
5. Set your export options and click OK to download a .csv template file.
6. Open the .csv template file. Do not change the column headings or structure of this template, it
   represents a required data structure.
7. Enter your line-item data. Note that setting any line item External column value set to
   TRUE causes that line item to be treated as external data.
8. Save the template in .csv format for import into your Apptio planning application. For details
   on importing data, see [Enter or
   import line item data](enter-import-line.htm "(Opens in a new tab or window)").

NOTES:

- If present, remove any sample data rows.
- Every line-item row must include a valid value in the Cost Object cell. All other cells are
  optional.
- The layout template supports importing values for all of the supported built-in dimensions,
  including the Cost Objects, Cost Centers and Accounts, as well as Vendors, Locations, and Projects
  dimensions (see [Manage
  built-in dimensions](manage-reference-data.html "(Opens in a new tab or window)")).
- You can delete any line items designated as external (those with the value of TRUE in the
  External column) without affecting other line items in a plan. To delete external line items, click
  Actions, then click Delete All External Items.
- Apptio planning applications always export the lowest level of grouped data, regardless of how
  the grouped data appear.
- Months that have been collapsed to quarterly columns will be exported as monthly line-item
  data.
- Multi-year plans support up to 72 time periods. Each time period is labeled P1 through P72, or
  P1 FYnnnn, where nnnn represents the four-digit fiscal year (see [Plan for multiple years](plan-multiple-years.htm "(Opens in a new tab or window)")).
