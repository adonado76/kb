---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "05-dashboards-and-reports-Cloudability"
source_files_count: 22
last_updated: "2026-07-13"
---

# 05-dashboards-and-reports-Cloudability

## Cloudability Dashboards

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards
- **source_path:** SSVCLNQ/product/cloudability-dashboards.html
- **original_file:** reports-cloudability-dashboards.md
- **images:**
  - 03-media/apptio-cloudability-standard/cloudability-dashboards.png

## Cloudability Dashboards

Cloudability Dashboards is a simple, self-service tool that can be used to create fully customizable dashboards, using the data available in Cloudability. Users can choose from a variety of Widgets to visualize the information and adjust the visualization options to tailor the Dashboards to individual needs, ensuring that insights are exposed quickly and in the right context.

Dashboards can be shared with other team members to improve collaboration and visibility. Widget annotations can ensure shared understanding of Cloud Cost and Spend, without the need for external collaboration tools. Applying Cloudability Views in a Dashboard can be used to narrow down the scope of each Dashboard to drill down into the details and see the data from a more focused perspective.

---

## Dashboards' List

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > Dashboards' List
- **source_path:** SSVCLNQ/product/dashboards-list.html
- **original_file:** dashboards-list.md
- **images:**
  - 03-media/apptio-cloudability-standard/all-dashboards.png
  - 03-media/apptio-cloudability-standard/dashboards-list.png
  - 03-media/apptio-cloudability-standard/home-grey.png
  - 03-media/apptio-cloudability-standard/home-blue.png
  - 03-media/apptio-cloudability-standard/star-grey.png
  - 03-media/apptio-cloudability-standard/star-blue.png
  - 03-media/apptio-cloudability-standard/copy-grey.png
  - 03-media/apptio-cloudability-standard/trash-grey.png
  - 03-media/apptio-cloudability-standard/add-blue.png

## Dashboards' List

When accessing Cloudability users are presented with their Home Dashboard. Other Dashboards can be access by clicking on the “All Dashboards” button after navigating to “My Dashboard” under “Home” section in the left-hand navigation bar.

The Manage Dashboards page allows users to see the full list of Dashboards, that they have access to.

The Dashboards' List displays a table that contains:

- The Name of each Dashboard.
- The Owner of each Dashboard.
- The “Shared With” column that helps to understand which users have access to each Dashboard. This field will either show “Org” when a Dashboard is accessible to all users in your organization or will display a number, that indicates the number of users that a given Dashboard has been shared with.

There are also several icons visible next to each Dashboard that provide additional configuration options.

The “Home” icon allows users to configure the default Dashboard that will be displayed when logging into Cloudability. This will be their “Home” Dashboard. Currently configured “Home” Dashboard will be displayed with a blue “Home” icon.

The “Star” icon allows users to add a Dashboard to their list of personal “Favorite” Dashboards, making it easier to access Dashboards from their Favorite Dashboard [ADD A LINK TO “CONFIGURING DASHBOARDS → FAVORITE DASHBOARDS], without having to navigate to the Dashboards' List. Favorite Dashboards are displayed with a blue star icon and all of the remaining Dashboards are displayed with a grey star icon.

The “Copy” icon allows users to create an exact copy of a given Dashboard. Clicking this icon will open a new Dashboard that contains exactly the same Widgets and configuration options. The sharing permissions are NOT copied and by default the new Dashboard is not shared with other users. The new Dashboard is created with a “copy” suffix to the Dashboard’s name, for example copying a Dashboard name “Executive cost summary” will create a Dashboard named “Executive cost summary copy”.

The “Delete” icon allows users to permanently delete a Dashboard. Users can only delete a Dashboard if they have “Edit” permissions for this Dashboard.

[WARNING] Users will be asked for a confirmation before deleting a Dashboard. Deleting a Dashboard can not be undone!

Manage Dashboards page can be used to create a new Cloudability Dashboard. Clicking the blue “plus” icon will create a new, empty Dashboard that can be then populated with Widgets.

---

## View and configure Dashboards

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards
- **source_path:** SSVCLNQ/product/view-and-configure-dashboards.html
- **original_file:** dashboards-view-configure.md
- **images:**
  - 03-media/apptio-cloudability-standard/date-range-selector.png
  - 03-media/apptio-cloudability-standard/duplicate-grey.png
  - 03-media/apptio-cloudability-standard/delete-grey.png
  - 03-media/apptio-cloudability-standard/widget-icons.png
  - 03-media/apptio-cloudability-standard/export-widget.png
  - 03-media/apptio-cloudability-standard/interactive-widgets.png
  - 03-media/apptio-cloudability-standard/on-hover-widget.png
  - 03-media/apptio-cloudability-standard/widget-navigation.png

## View and configure Dashboards

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

---

## Annotate in Dashboards

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Annotate in Dashboards
- **source_path:** SSVCLNQ/product/annotate-in-dashboards.html
- **original_file:** dashboards-annotate-in.md
- **images:**
  - 03-media/apptio-cloudability-standard/annotate-in-dashboards.png
  - 03-media/apptio-cloudability-standard/annotate-hover.png

## Annotate in Dashboards

To easily communicate spikes in Cost, or label important events on Widgets, users can decide to add “Annotations” that will be visible directly in the Widgets.

Clicking “Annotate” button will open a left-hand side modal that displays all currently configured Annotations and allow users to create new Annotations by clicking on the “Create New” button on the bottom of the Annotations menu. Creating new Annotations requires Edit permission to the Dashboard.

Annotations can be created only for a specific day and can not span multiple days. Moreover, Annotations will be displayed only on Charts that use “Date” as the X-Axis and are represented by a grey, vertical line on the Chart. Creating an Annotation requires specifying its Name and its Description.

Hovering over an Annotation will display its Name, associated Date and the Description.

---

## Create or Edit a Widget in a Dashboard

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard
- **source_path:** SSVCLNQ/product/create-or-edit-a-widget-in-a-dashboard.html
- **original_file:** dashboards-create-edit-widget-in-dashboard.md
- **images:**
  - 03-media/apptio-cloudability-standard/create-widget.png
  - 03-media/apptio-cloudability-standard/widget-range.png
  - 03-media/apptio-cloudability-standard/date-picker.png
  - 03-media/apptio-cloudability-standard/dimension-picker.png
  - 03-media/apptio-cloudability-standard/filters.png

## Create or Edit a Widget in a Dashboard

Widgets are the building blocks for Cloudability Dashboards. Each Widget is configured separately and can serve a different purpose. This page explains the configuration steps and options available to users when creating or editing Widgets in Cloudability Dashboards.

There are several different types of Widgets that can be added to a Dashboard. Available Widget types are:

- Chart
- Estimate
- Rightsizing
- Pie
- Number
- Table

There are certain differences between each Widget type and each Widget is described in detail on its own page in Help Center. There are certain common configuration options that are shared between all Widget types, with the exception of “Estimate” and “Rightsizing” Widgets.

Date Range configuration

[WARNING: Date range configuration is not available for “Estimate” and “Rightsizing” Widget types.]

Each Widget can be configured to display the data for a given time range. The date range applied for a Widget is displayed on the top of the Widget panel, both in the Edit mode and when viewing a Dashboard where a Widget is used. This can either be a relative date range (such as “Last 7 days” or “Last Month”) or a static, absolute date range (for example “Jul 16, 2025 - Jul 24, 2025”).

Date range can be configured by using the date range picker modal when editing a Widget:

There are several, pre-configured date ranges to chooses from:

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

All of the pre-configured ranges are “Relative”, meaning that the date range will automatically update as the time passes. For example, “Last 7 days” with be converted to “Jun 1, 2025 - Jun 7, 2025” on the June 7th but will update to “Jun 2, 2025 - Jun 8, 2025” on the June 8th.

Users can also pick a custom date range by selecting “Custom” from the drop-down or by picking the desired date range using the calendar interface. “Custom” date ranges can be static, meaning that they will not change as the time passes, or can be configured as “Rolling”, which means that they will be adjusted by one day, each day.

Another option for configuring the date range is “Custom start date-to-date”. Using this option, users can define the start of the date range and the end of the date range will always be the current (today’s) date.

Finally, Widgets can be configured to include a “Compare” date range. With this options, Widgets will display two values (or two data series): one of each of the selected date ranges. This allows easy comparison of two distinct periods - for example, to quickly understand the difference in Cost for two consecutive months. When using this option, Table Widgets will also display either the “Net” change between two dates ranges or a “Percent” difference. Number Widget will display the “Percent” difference between two date ranges.

Filters configuration in Widgets

[WARNING: Filters configuration is not available for “Estimate” and “Rightsizing” Widget types.]

For each Widget, users can choose to narrow down the data set to exclude Costs that are not relevant to a given use case. For example, users can choose to exclude or include Costs for a particular Cloud Service Provider.

Filters can be configured to match either a chosen Dimension or Metric. This includes Business Metrics, Business Dimensions, Account Groups or Tags.

To configure a Filter, users have to select a Measure that will be used to evaluate, using the “Measure” drop-down menu.

Next, a Filter operator has to be selected, using one of the available options from the list:

- equals
- not equals
- less than
- greater than
- less than or equals
- greater than or equals
- contains
- does not contain

Finally, users need to select a Value for the Filter condition. This can either be a number (for Metric-based Filters), text value or a date. For Dimensions, Cloudability enables selecting values from the list of Values available in the User’s data set. Additionally, to populate a large number of values into a Filter, users can copy and paste a list of comma-separated values into the filter text input field.

[WARNING]

When using "equals" or "not equals" match condition, the following inputs are treated equivalently:

"One-time", "one-time charge", "one-time-charge", "one_time charge", "one_time_charge"

"Recurring Charge", "recurring-charge", "recurring", "recurring_charge"

Multiple Filters can be created for a single Widget.

Filters applied on the same Measure will be created using the logical “OR” condition, while the “AND” condition will be used between different Measures. For example:

---

## Chart Widget

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard > Chart Widget
- **source_path:** SSVCLNQ/product/chart-widget.html
- **original_file:** dashboard-chart-widget.md
- **images:**
  - 03-media/apptio-cloudability-standard/chart-widget.png

## Chart Widget

Chart Widget allows Cloudability Users to visualize their data in the form of a Line Chart, Area Chart, Bar Chart or a Column Chart. This Widget type is most useful when what matters the most are the overall trends, spikes or differences between values on the Chart, and not the exact values.

When configuring a Chart Widget, users can choose any Dimension either from the “Cost and Usage” or the “Utilization” data source for the Chart’s X-axis.

Any Metric from the “Cost and Usage” or the “Utilization” data source can be used as the Y-axis on the Chart.

The data can then be broken down further into separate data series by using the “Group by” feature, which will display a separate data series for each Dimension selected.

For “Line Chart” or “Area Chart” users can select the “Spline” option which will create a smoother line in the chart.

Populating the “Series Name” field will add a prefix to each Dimensions used as a legend on the Chart.

“Scale From Lowest Value” option allows to decide if the Chart scale should start from the lowest value on the chart or allow users to manually decide the start of the Y-axis. The default value when “Scale From Lowest Value” is not selected is to start the scale at “0”.

Finally, users are able to display multiple Charts on a single Widget. Click the “Add Layer” button on the bottom of the configuration screen to create another type of Chart. The configuration steps for each Layer are the same as for the primary Layer.

---

## Estimate Widget

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard > Estimate Widget
- **source_path:** SSVCLNQ/product/estimate-widget.html
- **original_file:** dashboard-estimate-widget.md
- **images:**
  - 03-media/apptio-cloudability-standard/estimate-widget.png

## Estimate Widget

Cloudability Dashboards have an option to visualize the data from the “Estimate” data source.

Currently, the Estimate Widget can only display the KPI difference between “This Month” and “Last Month” using one of the following Cost metrics:

- Cost (Total Blended)
- Cost (Amortized)
- Cost (Adjusted)
- Cost (Adjusted Amortized)
- Cost (List)

Charges that are yet to appear in the billing file will be forcasted for the purpose of displaying the Estimate Widget KPI.

---

## Number Widget

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard > Number Widget
- **source_path:** SSVCLNQ/product/number-widget.html
- **original_file:** dashboard-number-widget.md
- **images:**
  - 03-media/apptio-cloudability-standard/number-widget.png

## Number Widget

The Number Widget can be used in Cloudability Dashboards to see a summary of a single Metric in a Dashboard. This Widget displays a single value of a Metric (KPI) over a given date range.

Any Metric from the “Cost and Usage” or the “Utilization” data source can be used to display the Number Widget.

Users can also decide to display a small line chart next to the KPI on the Number Widget, to understand how the Metric changed over time.

---

## Pie Widget

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard > Pie Widget
- **source_path:** SSVCLNQ/product/pie-widget.html
- **original_file:** dashboard-pie-widget.md
- **images:**
  - 03-media/apptio-cloudability-standard/pie-widget.png

## Pie Widget

Pie Widget allows Cloudability Users to visualize their data so that the Metrics can be displayed as a fraction of the whole, allowing to easily understand which Dimensions correspond to the largest part of the Cost.

When configuring a Pie Widget, users can choose any Dimension either from the “Cost and Usage” or the “Utilization” data source for the Pie breakdown.

Any Metric from the “Cost and Usage” or the “Utilization” data source can be used as the Widget’s data.

To improve visibility, Users can narrow down the number of results to the top N or bottom N values.

---

## Rightsizing Widget

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard > Rightsizing Widget
- **source_path:** SSVCLNQ/product/rightsizing-widget.html
- **original_file:** dashboard-rightsizing-widget.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing-widget.png

## Rightsizing Widget

Cloudability Dashboards have an option to visualize the data from the “Rightsizing” data source.

Currently, the Rightsizing Widget can only display the last 10 days of Rightsizing savings.

Rightsizing in Cloudability Dashboards is available for the following products:

- AWS EC2 (Elastic Compute Cloud)
- AWS EBS (Elastic Block Store)
- AWS RDS (Relational Database Service)
- Azure Compute
- Azure Managed Disk
- Azure SQL Database

---

## Table Widget

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard > Table Widget
- **source_path:** SSVCLNQ/product/table-widget.html
- **original_file:** dashboard-table-widget.md
- **images:**
  - 03-media/apptio-cloudability-standard/table-widget.png

## Table Widget

Table Widget allows detailed overview of the data and is used for accurate and in-depth analysis of the Costs. Table Widget can be created using either “Cost and Usage” or “Utilization” data.

Users can choose up to 15 Dimensions and up to 8 Metrics to build the table.

Tables can be sorted by any of the selected Dimensions or Metrics.

Finally, to improve clarity of the Table Widget, users can decide to display only Top N or Bottom N values in the table. The remaining values will be aggregated under the “Other” category.

Table Widgets in Cloudability Dashboards will automatically sum all rows and display the Total value on the bottom of the Widget.

---

## Text Widget

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Create or Edit a Widget in a Dashboard > Text Widget
- **source_path:** SSVCLNQ/product/text-widget.html
- **original_file:** dashboard-text-widget.md
- **images:**
  - 03-media/apptio-cloudability-standard/text-widget.png

## Text Widget

Text Widget can be used to provide additional description, comments or explanation to the Dashboard. Most important features include:

- Built-in basic editor options
- Markdown support
- Embedding links to external content

---

## Share a Dashboard

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Dashboards > View and configure Dashboards > Share a Dashboard
- **source_path:** SSVCLNQ/product/share-a-dashboard.html
- **original_file:** dashboards-share-dashboard.md
- **images:**
  - 03-media/apptio-cloudability-standard/share-a-dashboard.png

## Share a Dashboard

To improve collaboration between multiple users and teams, Cloudability Dashboards support the Dashboard Sharing functionality.

All users (both having View and Edit permissions) can share a Dashboard by URL. This functionality enables generating a URL that directly points to the currently viewed Dashboard.

Users can choose to include the currently applied View and/or currently applied Dashboard Level Date Range in the URL, to further specify the context visible when following the URL.

Additionally, users with “Edit” permission to a given Dashboard can choose to share a Dashboard with other Cloudability users or the entire organization.

“Share to User” drop-down menu enables selecting the list of users to share the Dashboard with. “Permissions” drop-down allows users to decide if the Dashboard will be shared with the “View” or “Edit” permissions.

[NOTE] Admins can edit any dashboard shared with them, view-only permissions don't apply.

---

## Cloudability Reports

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Reports
- **source_path:** SSVCLNQ/product/cloudability-reports.html
- **original_file:** reports-cloudability.md
- **images:**
  - 03-media/apptio-cloudability-standard/cloudability-reports.png

## Cloudability Reports

Cloudability Reports is self-service tool that allows users to access their Cost and Utilization data to answer ad-hoc questions, schedule Reports to send on a given cadence or export the raw data for a given set of Dimensions, Metrics and Filters.

---

## Create or Edit a Report

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Reports > Create or Edit a Report
- **source_path:** SSVCLNQ/product/create-or-edit-a-report.html
- **original_file:** reports-create-edit-report.md
- **images:** []

## Create or Edit a Report

New Reports can be created by clicking the "New Report" button on the Reports List page. Existing Reports can be edited by accessing the Report and clicking the blue "Edit Report" button. "Edit" permissions are required a modify an existing Report.

When creating a Report, several configuration options are available:

- Report Name - provide a descriptive name for a Report so that it can be easily accessed later.
- Date Range - configure the date range that will be used to populate the Report.
- Category - select a category to which a Report will be assigned. Category can later be used to sort Reports and assign them to certain groups. A new Category can also be created by clicking the "Add Category" button.
- Shared Cost - this checkbox enables the Cost Sharing rules to be applied to generate the Report.

Dimensions & Metrics

In this section, users can select the Data Source to query the data. Currently there are two Data Sources available: Cost Data or Utilization Data.

Users can select which Dimensions and Metrics from a given Data Source to visualize in the Report.

When selecting multiple Metrics, the relevant KPI numbers are displayed on the top of the Report. Users can click one of the KPI numbers to focus on a given Metric in the Report Chart below. All selected Metrics are included in the raw data export.

When selecting multiple Dimensions, the Table on the bottom of the Report will be broken down by each Dimension and a separate row will be displayed for each unique combination of Dimension values. This selection is also considered for exporting raw Report data.

Next, users can decide how to sort the data in the Table on the bottom of the Report. Any Dimension or Metric can be used for sorting in descending or ascending order.

Finally, users can configure a set of Filters that will be used to narrow down the data set visible to users. Any Measure (either Metric or Dimension) can be used to include or exclude data from the Report.

[WARNING]

When using "equals" or "not equals" match condition, the following inputs are treated equivalently:

"One-time", "one-time charge", "one-time-charge", "one_time charge", "one_time_charge"

"Recurring Charge", "recurring-charge", "recurring", "recurring_charge"

---

## Copy a Report to a Dashboard

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Reports > Create or Edit a Report > Copy a Report to a Dashboard
- **source_path:** SSVCLNQ/product/copy-a-report-to-a-dashboard.html
- **original_file:** report-copy-dashboard.md
- **images:**
  - 03-media/apptio-cloudability-standard/copy-a-report-to-a-dashboard.png

## Copy a Report to a Dashboard

Existing Reports can also be saved as new Widgets in existing Dashboards by clicking the "Copy to Dashboard" button in the dot menu:

Then, users can select an existing Dashboard where a Report will be saved and choose which type of widget to add to the Dashboard. Users can save the KPI, Chart or Table in a Dashboard.

---

## Export a Report

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Reports > Create or Edit a Report > Export a Report
- **source_path:** SSVCLNQ/product/export-a-report.html
- **original_file:** report-export.md
- **images:**
  - 03-media/apptio-cloudability-standard/export-menu.png
  - 03-media/apptio-cloudability-standard/export-modal.png
  - 03-media/apptio-cloudability-standard/generate-report.png

## Export a Report

To extract raw data from a Report, users can Export the data to a CSV file by navigating to the "Export" option from the dot menu:

Clicking the "Export" menu item will initiate the Report generation. It may take several minutes to prepare the Report for download, depending on the size of the data set being exported. The following modal will be displayed on the bottom right side of the page to confirm that the Report is being generated:

Reports that are being generated can be found in the menu on the top of the page, next to the View selector:

---

## Share a Report

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Reports > Create or Edit a Report > Share a Report
- **source_path:** SSVCLNQ/product/share-a-report.html
- **original_file:** report-share.md
- **images:**
  - 03-media/apptio-cloudability-standard/share-grey.png
  - 03-media/apptio-cloudability-standard/share-a-report.png

## Share a Report

Users may decide to share a saved Report with other Users in their Organization. Reports can be shared by clicking the "Share" icon on the Report page.

Then, User can decide if the Share link should also include the currently used View, so that the other User will see exactly the same data as currently viewed by the User sharing the Report.

Next, Users can decide if the Report should be shared with a specific User or the entire Organization. Finally, Users can decide if the Report is shared with Edit permissions or only View access.

---

## Subscribe to a Report

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Reports > Create or Edit a Report > Subscribe to a Report
- **source_path:** SSVCLNQ/product/subscribe-to-a-report.html
- **original_file:** report-subscribe.md
- **images:**
  - 03-media/apptio-cloudability-standard/envelope-grey.png
  - 03-media/apptio-cloudability-standard/subscribe-to-a-report.png

## Subscribe to a Report

Users can Subscribe to a Report to receive the Report on a given cadence. Report Subscription can be configured by clicking the envelope icon when accessing a Report:

This will open the Subscription configuration menu that allows users to configure the time interval at which the Report will be generated.

Reports can be delivered daily, weekly or monthly.

---

## Reports List

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cloudability Reports > Reports List
- **source_path:** SSVCLNQ/product/reports-list.html
- **original_file:** reports-list.md
- **images:**
  - 03-media/apptio-cloudability-standard/reports-list.png
  - 03-media/apptio-cloudability-standard/ootb-reports.png

## Reports List

When navigating to "Home" => "Reports" users are presented with a list of all Reports accessible to them. The list of Reports can be further narrowed down to focus only on Reports in a certain category:

- Starred - displays only reports labeled as "Starred" by the user
- Mine - displays only reports created by the current user
- Shared - displays only reports that are shared with the current user
- Subscribed - displays only reports that the current user is currently subscribed to

The list of Reports in Cloudability is automatically populated with the default (out of the box) reports, created by Cloudability, that address most common use cases and can be further modified to customize them by including additional Dimensions, Filters and other changes. All out-of-the-box Reports are owned by "Cloudability" and can not be directly modified. Instead, users can create their copy and include any required changes.

Below is the list of out-of-the-box Reports available in Cloudability:

- AWS CloudFront Distributions
- AWS CloudWatch Overview
- AWS Data Transfer Detail
- AWS DynamoDB Tables
- AWS EBS Overview
- AWS EBS Volumes and Snapshots
- AWS EC2 Instances
- AWS EC2 Overview
- AWS EMR Overview
- AWS ElastiCache Clusters
- AWS Elasticsearch Domains
- AWS Elasticsearch Overview
- AWS Fargate Overview
- AWS Invoice - All Services and Support Last Month
- AWS Invoice - CloudFront and Direct Connect Last Month
- AWS Invoice - Data Transfer Last Month
- AWS Invoice - RI Purchases Last Month
- AWS Kinesis Overview
- AWS Kinesis Streams
- AWS Lambda Functions
- AWS Lambda Overview
- AWS RDS DB Instance Hours
- AWS RDS Database Storage
- AWS RDS Overview
- AWS RDS Provisioned IOPS
- AWS Redshift Clusters
- AWS Redshift Overview
- AWS S3 Buckets (including Glacier)
- AWS S3 Overview
- Aggregated Monthly RI Vacancy
- All Services - Last Month
- Amortized RI Costs by Reservation ID
- Azure Compute Overview
- Azure Compute Virtual Machines
- Azure Database Overview
- Azure Database Resources
- Azure Networking Overview
- Azure Networking Resources
- Azure Storage Overview
- Azure Storage Resources
- Azure Web Overview
- Costs by Account Last Month
- Costs by Account Monthly Comparison
- Costs by Cloud Vendor
- Costs by Lease Type (On-Demand vs Reserved vs Spot)
- Costs by Transaction Type (Usage, RIs, Credits, Taxes)
- Costs by Usage Family (Compute, Storage, etc.)
- Databricks Costs Overview
- Datadog Costs Overview
- Detailed Kubernetes Costs
- GCP Cloud Bigtable Overview
- GCP Cloud Dataflow Overview
- GCP Cloud Pub/Sub Overview
- GCP Cloud SQL Overview
- GCP Cloud Storage Overview
- GCP Compute Engine Discounts
- GCP Compute Engine Overview
- GCP Kubernetes Engine Overview
- Highly Underutilized Instances
- Instances Provisioned in the Last Day
- Last Month's RI Vacancy Deep Dive
- Long Term Utilization Trends
- Marketplace Monthly Summary
- MongoDB Costs Overview
- OCI Block Storage Overview
- OCI Compute Overview
- OCI Costs Overview
- OCI Database Overview
- OCI Object Storage Overview
- Oldest Instances (Over a Month)
- Reservation Coverage Rate (EC2)
- Snowflake Costs Overview
- Spot Instance Usage and Effective Rate (EC2)
- Unassociated ElasticIP Addresses
- Underutilized Compute Optimized Instances
- Underutilized General Purpose Instances (Non Burst)
- Underutilized Storage Optimized Instances
- Utilization of Massive Instances

---

## Cost and Usage Data availability in Reporting

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Cost and Usage Data availability in Reporting
- **source_path:** SSVCLNQ/chatbot/cost-and-usage-data-availability-in-reporting.html
- **original_file:** reports-cost-usage-data-availability-in-reporting.md
- **images:** []

## Cost and Usage Data availability in Reporting

Overview

To report on Cloudability cost and usage data, the billing files from the vendor must first be processed through our data pipeline. The process begins with raw cost and usage data ingestion. Once that data is ingested, it goes through a series of data normalization, transformation, aggregation, and decoration steps before being made available to reporting.

Cost Pipeline Details

Cost and usage data ingestion in Cloudability begins after successful vendor credentialing where you grant Cloudability access to your billing data. Once Cloudability confirms that it has appropriate permissions from the credentialing process, it begins retrieving data from the vendor. Cloudability checks for new data multiple times a day for each credentialed account. As soon as new data is discovered on the vendor side, the ingestion process begins to pull the latest available data.

After the raw billing data ingestion, Cloudability’s data pipeline proceeds with various data processing steps. This next stage of the pipeline is responsible for enriching the raw data with many of the valuable data points and measures you use every day, such as tag mappings, business dimensions, account groups, and business metrics among others. Also, if you have clusters provisioned for use with Cloudability Container Insights, this is when container cost allocation is performed. Finally, the processed and decorated cost data is loaded into our data platform for use by Cloudability reporting, dashboards, and Apptio BI.

Frequently Asked Questions (FAQ)

What impacts my data processing time?

Data processing time is directly impacted by data volume. In addition the overall vendor raw file size and record count per credentialed account, the important considerations for the processing time include:

- Number of provisioned clusters and associated pod count (if provisioned within Cloudability ). Container cost allocation generates additional granularity which leads to many more records.
- Customer-defined dimensions such as Business Mappings and Tag Mappings. Mapping quantity and statement complexity.
- Time of the month –MTD data volume increases with every month. It is common for end of month processing to take longer due to data volume being at its peak.

When can I expect my new data to be available for reporting?

With respect to the inconsistent frequency in which the billing files are updated by the vendor and the variability of the overall data size per customer, we cannot guarantee an exact time that the new data will become available in Cloudability. Generally, this is within an average of 24 hours after a new billing file update is published by the vendor.

The “business as usual” (BaU) data processing including raw data ingestion as described in this article by default occurs on recent data . By definition that means current month’s data set, along with the addition of the previous month's data if there is an update to it by the vendor (typically previous month updates can occur up to two weeks after month end). Anything historical processing outside of this would require either a reprocess or refetch, depending on the use case.

What is a reprocess?

A typical customer action is a reprocess , which is a manually triggered action that performs the post-ingestion processing again on historical data . This means that we do not ingest any new vendor data during this operation, but instead process it through the latter part of our pipeline to decorate and transform the data again with updated information. A common use case for a reprocess would be to update Business Mappings on historical data in Cloudability. A reprocess is not necessary during the current month as it is processed automatically as explained previously. Reprocesses are performed in month units, and can take longer than the business as usual processing depending on the number of months requested.

What is a refetch?

A refetch is where we go through the entire pipeline process again, including retrieval the raw vendor data – this should only be performed in rare circumstances such as backfilling missing vendor data due to an error. Or, onboarding a new payer account in which historical data exists in the vendor’s storage and needs to be pulled into Cloudability. If required, work with your TAM or open an Apptio Support case.

This article specifically relates to cost and usage (billing) data availability in reporting/ dashboards for Cloudability and also Apptio BI Reporting.

Other features such as Rightsizing, Resource Inventory, and Cloudability Financial Planning require additional feature-specific processing after the billing data is processed. Additionally, cloud cost data import into TBM Studio (Cost Transparency) requires additional steps not outlined here.

What are future dated line items?

- Future dated line items are invoice line items whose Usage Start Time is later than the processing date .
- Common examples include, but are not limited to: AWS Savings Plans billed for the entire month upfront Pre-paid items such as AWS re:Invent tickets

Possible Discrepancies and How to Resolve

Sometimes, UI KPIs and API/Export totals won’t match until the data is fully processed. Depending on the source of the discrepancy, this can be resolved manually by adding Date or a similar report dimension.

- Within the Report UI, the total shown in the metric KPI across the top does not match the same metric’s total shown in the corresponding report table.
- The metric KPI’s total displayed in the UI does not match against the total in the corresponding report’s export.
- The metric KPI’s total displayed in the UI does not match against the total returned from equivalent report API result.

Reports including the current date

When the UI updates to the current date (e.g., end date advances from Dec 2 to Dec 3), a temporary discrepancy occurs during the ~4-hour window before first data ingestion. The UI KPI/Graph queries the Daily View and includes future dated line items, while Report Table/Export/API queries hit the Monthly View and exclude them. The discrepancy equals the future dated cost total for accounts without current date ingestion. This resolves after the first normal file drop for the impacted payer accounts.

- UI/KPIs use daily data → may include charges for the current date not yet ingested into Monthly Table when the UTC date changes
- Monthly table (exports/API) excludes them until first ingestion of current day occurs
- Common source of Discrepancy: AWS Savings Plans costs

TIP: If the totals match after filtering out AWS Savings Plan Costs, then you can assume the discrepancy is due to future dated line items

Possible Fixes/Workarounds

As previously mentioned, this type of discrepancy will automatically resolve once the next cost ingestion job completes. Otherwise, the following mitigation steps can be used if seeking a workaround sooner:

1. Update Report to include a dimension like Date or any of the other dimensions listed, so that both the API/Export and UI KPIs use the Daily View : Day Day of Week Week (Category) Week (Year) Invoice Date
1. Create a validation Report like the example below If the total shown in the KPI, and the Report Table are the same than you should not run into discrepancies due to future dated line items

Reports ending on yesterday’s date

Reports with the previous day as the end date show discrepancies. When the UTC date changes, UI prevents sudden total shifts by continuing to use the Monthly Table for the previous day. If customers don't update the end date, Report Table/Export/API totals will exceed KPI totals as the monthly table ingests data for the current date while the KPI only includes data through the set end date.

- Monthly table ingests current-day data, but UI report is fixed to yesterday
- This can make API/export totals appear higher than the UI KPIs

1. Update Report to include a dimension like Date or any of the other dimensions listed, so that both the API/Export and UI KPIs use the Daily View : Day Day of Week Week (Category) Week (Year) Invoice Date
1. Or update the date range to include the current date

---

## Invoice Reconciliation in Cloudability

<!-- sub-header -->
- **breadcrumb:** Working with dashboards and reports > Invoice Reconciliation in Cloudability
- **source_path:** SSVCLNQ/chatbot/invoice-reconciliation-reporting.html
- **original_file:** reports-invoice-reconciliation-in-cloudability.md
- **images:**
  - 03-media/apptio-cloudability-standard/inv_recon_filters.png
  - 03-media/apptio-cloudability-standard/inv_recon_calendarpicker.png

## Invoice Reconciliation in Cloudability

Invoice Reconciliation refers to the process of validating that the total billed amount on a finalized Cloud Service Provider (CSP) invoice matches the total cost reported in Cloudability. This alignment is verified by generating a focused Cloudability report with a small set of filters. While the workflow itself is straightforward, there are several important considerations and nuances that can affect the accuracy of the reconciliation. This document outlines those key considerations and provides guidance for completing the exercise effectively.

### Before you proceed

Verify account credentialing

For the specified billing month, check that the Payer Account in question was successfully credentialed during the entire period and that cost data exists in Cloudability as expected.

Validate currency configuration

If the invoice currency differs from the Cloudability account currency, ensure multi‑currency settings are configured correctly.

Reconcile at the correct scope

Perform reconciliation at the combined Invoice Month and Payer/Billing Account level. Where available, use Invoice ID to align invoice data with raw billing records.

Account for invoice finalization timing

When reconciling the most recently closed month, understand the possibility that CSPs may make adjustments several days (up to two weeks) into the following month.

### Special considerations

The following are important notes and behaviors to consider when reporting on cost data in Cloudability:

- Rely on raw billing files (e.g., CUR, Cost Export, Cloud Billing Table) as Cloudability’s authoritative cost source. Expect invoices to match raw data in most cases, but be aware that vendors may include charges or credits on invoices that do not appear in raw billing exports.
- Be aware of vendor‑specific exclusions. Note that Azure Cost Management data exclude taxes and billing adjustments/credits. Do not expect these values to appear in Cloudability.
- There can be post-dated or out-of-cycle charges that exist on the invoice but are outside of the current usage month. This can cause confusion due to how Cloudability reports query the time-period based on Usage Date(explained more in the next section).
- AWS CUR and Azure MCA Cost Management Exports are the only billing file types that currently provide an invoice identifier field to Cloudability that can be used for invoice reconciliation using the Invoice ID dimension.
- When provisioning GKE clusters for use in Cloudability, assign unique cluster names. Ensure the gke-cluster label assigned to the cluster matches the provisioned cluster name exactly. Do not use duplicate names, as this may cause the resulting cluster-split costs in reporting to be incorrect.

### How to reconcile in Cloudability reporting

1. Begin by creating a report in Cloudability filtered on the specific Invoice Date and Payer Account ID . Invoice Date is reflected as the first of the month, the format is YYYY-MM-01 which will be formatted and displayed in the UI as <Month> 1st, <Year> . Payer Account ID is the primary payer/billing ID as shown on the invoice, and is what represents the account that is credentialed with Cloudability to ingest billing files. If reconciling with a vendor that supports Invoice ID, like AWS, add that as well if desired to reconcile at this scope. Invoice IDs typically have a many to one relationship with a Payer Account.
1. Using the Date Picker , choose a wide time period starting from at least the 1st of the prior month, and the end date should be as far into the future as available up until the current date. In this example, Jan 2026 is our desired invoice month and we are running the report on the 24th of February. The Date dimension in Cloudability is based on usage date, therefore the Date Picker in Cloudability queries the costs based on usage date range. The purpose of a wide time period is to capture any invoice charges in the usage months that neighbor the invoice month. Note: Cloudability Reporting will query up to the current usage date . So if there are delayed charges far into the future beyond the queryable time frame, Cloudability will not be able to report on them. This applies to the “out of cycle” charges as mentioned in the Special Considerations section of this document.
1. Optionally add the Month (Year) dimension to the report to highlight any usage charges occurring outside the invoice month.
1. Choose Cost (Total) as the report metric, since invoices reflect actual billed “out‑of‑pocket” costs rather than amortized amounts.
1. Finally, run the report and validate the cost shown in the resulting table.

### FAQ

What if my invoice cost does not match?

- PDF attachment or full screenshot of the invoice which displays all pertinent information including Billing Account ID, date of invoice, cost, and invoice ID
- Cloudability URL link for the report that was used for the reconciliation

Can I reconcile to the total cost as seen in a CSP cost management tool (i.e. AWS Cost Explorer) instead?

Generally, yes. However, native cost management tools are not always a direct reflection of what exists in the raw billing files. Reconcile against the invoice instead which is generally supported by the underlying raw billing data.

---
