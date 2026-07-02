---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Create or Edit a Report"
breadcrumb:
  - "Cloudability Premium"
  - "Working with dashboards and reports"
  - "Cloudability Reports"
source_path: "product/create-or-edit-a-report.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Create or Edit a Report

New Reports can be created by clicking the "New Report" button on the Reports List page. Existing
Reports can be edited by accessing the Report and clicking the blue "Edit Report" button. "Edit"
permissions are required a modify an existing Report.

When creating a Report, several configuration options are available:

- Report Name - provide a descriptive name for a Report so that it can be easily accessed
  later.
- Date Range - configure the date range that will be used to populate the Report.
- Category - select a category to which a Report will be assigned. Category can later be used to
  sort Reports and assign them to certain groups. A new Category can also be created by clicking the
  "Add Category" button.
- Shared Cost - this checkbox enables the Cost Sharing rules to be applied to generate the
  Report.

Dimensions & Metrics

In this section, users can select the Data Source to query the data. Currently there are two Data
Sources available: Cost Data or Utilization Data.

Users can select which Dimensions and Metrics from a given Data Source to visualize in the
Report.

When selecting multiple Metrics, the relevant KPI numbers are displayed on the top of the Report.
Users can click one of the KPI numbers to focus on a given Metric in the Report Chart below. All
selected Metrics are included in the raw data export.

When selecting multiple Dimensions, the Table on the bottom of the Report will be broken down by
each Dimension and a separate row will be displayed for each unique combination of Dimension values.
This selection is also considered for exporting raw Report data.

Next, users can decide how to sort the data in the Table on the bottom of the Report. Any
Dimension or Metric can be used for sorting in descending or ascending order.

Finally, users can configure a set of Filters that will be used to narrow down the data set
visible to users. Any Measure (either Metric or Dimension) can be used to include or exclude data
from the Report.

[WARNING]

When using "equals" or "not equals" match condition, the following inputs are treated
equivalently:

"One-time", "one-time charge", "one-time-charge", "one\_time charge", "one\_time\_charge"

"Recurring Charge", "recurring-charge", "recurring", "recurring\_charge"

- **[Subscribe to a Report](../product/subscribe-to-a-report.html)**
- **[Share a Report](../product/share-a-report.html)**
- **[Export a Report](../product/export-a-report.html)**
- **[Copy a Report to a Dashboard](../product/copy-a-report-to-a-dashboard.html)**

**Parent topic:** [Cloudability Reports](../product/cloudability-reports.html)
