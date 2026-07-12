---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Create or Edit a Widget in a Dashboard"
breadcrumb:
  - "Working with dashboards and reports"
  - "Cloudability Dashboards"
  - "View and configure Dashboards"
  - "Create or Edit a Widget in a Dashboard"
source_path: "SSVCLNQ/product/create-or-edit-a-widget-in-a-dashboard.html"
images:
  - "03-media/apptio-cloudability-standard/create-widget.png"
  - "03-media/apptio-cloudability-standard/widget-range.png"
  - "03-media/apptio-cloudability-standard/date-picker.png"
  - "03-media/apptio-cloudability-standard/dimension-picker.png"
  - "03-media/apptio-cloudability-standard/filters.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Create or Edit a Widget in a Dashboard

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
