---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "View and configure Dashboards"
breadcrumb:
  - "Working with dashboards and reports"
  - "Cloudability Dashboards"
  - "View and configure Dashboards"
source_path: "SSVCLNQ/product/view-and-configure-dashboards.html"
images:
  - "03-media/apptio-cloudability-standard/date-range-selector.png"
  - "03-media/apptio-cloudability-standard/duplicate-grey.png"
  - "03-media/apptio-cloudability-standard/delete-grey.png"
  - "03-media/apptio-cloudability-standard/widget-icons.png"
  - "03-media/apptio-cloudability-standard/export-widget.png"
  - "03-media/apptio-cloudability-standard/interactive-widgets.png"
  - "03-media/apptio-cloudability-standard/on-hover-widget.png"
  - "03-media/apptio-cloudability-standard/widget-navigation.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# View and configure Dashboards

Accessing a Dashboard page is a great way to explore your Cloud spend in detail. Dashboards can address a multitude of use cases and can be customized according to your company’s unique requirements.

There are different actions that you can take for each setting, depending on your permissions.

Add Widget

Clicking the “Add Widget” icon allows users to create a new Widget in the current Dashboard. Detailed description of this functionality can be found in the “Create or Edit a Widget in a Dashboard” page of the documentation.

Creating a new Widget requires Edit permissions for the current Dashboard.

Views in Dashboards

Cloudability Views are honored when working with Cloudability Dashboards. Views can be selected using the “Current View” drop-down on the top right-hand side of the page. Users can also navigate to the “Views” page when selecting “Manage Views…” option from the drop-down. Clicking the “X” next to the View name in this drop-down will result in clearing the applied View.

Favorite Dashboards

When viewing a Dashboard, users can quickly navigate to another, favorite Dashboard by clicking on the yellow star icon in the top left-hand side of the Dashboard. This will open a context menu, displaying all their Favorite Dashboards, enabling quick navigation between important Dashboards. The list of Favorite Dashboards can be modified from the “All Dashboards” list.

Dashboard Level Date Range

With this option, users can change the Date Range that is applied for all Widgets in a given Dashboard. This setting adjusts the Date Range temporarily, and only for the current users, allowing different people to work with the same Dashboard at the same time. Dashboard Level Date Range does not require Edit permissions to the Dashboard.

There are multiple, preconfigured selections available for this option:

- Yesterday
- Today (UTC)
- This Week
- Last Week
- This Month
- Last Month
- This Quarter
- Last Quarter
- This Year
- Last Year
- Last 7 days
- Last 14 days
- Last 30 days
- Last 60 days
- Last 90 days

Users can also select any custom date range by picking the dates using the calendar modal or by typing in the date range manually.

![](../images/date-range-selector.png)

The Date Range selection can be cleared by clicking the “X” icon next to the configured date range.

[WARNING] Some data sources do not support the Dashboard Level Date Range settings. Widgets using Rightsizing or Estimate data sources will retain the date range configured at the Widget level.

Share a Dashboard

This option is described in detail in the “Share a Dashboard” section of this documentation.

Annotate

This option is described in detail in the “Annotate in Dashboards” section of this documentation.

Duplicate a Dashboard

Clicking the “Duplicate” icon will result in creating a copy of the current Dashboard. This is another option to Copy a Dashboard, as described in the “Copy a Dashboard” in the Dashboards' List section.

Delete a Dashboard

Clicking the “Delete” icon will permanently delete the current Dashboard. This functionality is equivalent to the “Delete” functionality from the “Dashboards' List page.

From the Dashboard level, users can also take Widget-specific actions. There are multiple options available when hovering-over a Widget.

Edit

Clicking the “Edit” icon allows users to modify the existing widget. Detailed description of this functionality can be found in the “Create or Edit a Widget in a Dashboard” page of the documentation.

Editing a Widget requires Edit permissions for the current Dashboard.

Copy

Clicking the “Copy” icon allows users to copy the selected Widget and add it to the same or a different Dashboards. Copying the Widget requires only View permissions to the current Dashboard, but saving a copy of the Widget requires Edit permissions in the target Dashboard.

Export

Users can choose to download the data for a given Widget in a comma-separated format by clicking the “Export” icon. This option will display an informational modal on the bottom left-hand side of the page, informing the user that the report is being generated. Once the data is ready, data download will start. Each layer of the Widget and each date Comparison will generate a separate comma-separated value file. “View” permission is sufficient to export the data from a Widget.

Rightsizing and Estimate type of Widgets can not be exported.

Delete

Users can delete a Widget by clicking the “Delete” icon. Users will be asked to confirm the deletion of a Widget.

[WARNING] This action can not be undone.

Interactive Widgets

Widgets in Cloudability Dashboards are interactive to allow better, real-time analysis of your data.

Users can choose to hide or display Dimensions by clicking on on each Dimension name in the legend to focus on items that matter the most at the moment.

Hovering over a section of a Widget displays additional information, such as exact value of the metric at a given point in a chart, or displays additional Annotations relevant to a data point.

Clicking on a section of a Widget allows users to navigate to a more detailed Report for further analysis.
