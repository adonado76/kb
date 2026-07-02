---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "GCP Resource Inventory"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Resource Inventory"
source_path: "product/gcp-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Resource Inventory

GCP Resource Inventory feature for Cloudability enables you to produce an authoritative list of
GCP cloud resources that existed and were billed during a specific reporting period. You have the
flexibility to build this list from resources spanning multiple accounts and choose from different
measures (dimensions and metrics) to surface the details relevant to them. This information -
available for each cloud resource - unifies billing, utilization, and descriptive meta data to give
you a more comprehensive inventory view.

## Getting started

GCP Resource Inventory reporting feature must be enabled for your Cloudability Org. You must
reach out to your TAM/CSM/account point of contact from Apptio to get this done. Once enabled, allow
2-3 business days for the data to start appearing in your inventory reports.

Inventory Reporting Measures

- Measures are categorized as dimensions, metrics and tags (tags include Cloudability's tag
  dimensions, account groups and business mappings). You can include up to 20 columns to an individual
  report .
- For each GCP service, a specific set of measures are supported.
- You can filter your respective inventory reports using any of the measures available within
  this feature.

Clickable KPIs for Quick Filtering

For every service, KPIs will be displayed at the top of the report to provide you with key
summary information such as Newly Launched Resources and Untagged Instances . You can
click and filter the Inventory report based on these KPIs to drill down to the specific report data
you are looking for.

Inventory Reporting Date Windows

You can choose the period in the date picker for which you want to view the inventory data for
each service. Maximum allowed range for selection is 31 days. Upon enabling this feature, resource
inventory data will be back filled to the beginning of the current month. Over time, inventory data
will be available on a three-month rolling window. At any point in time, you will be able to access
resource inventory data for the current month along with the previous two months.

Statistical Filtering using the Display Filter

From the inventory data generated for a specific service and time period, you can now choose to
display a subset of that data, whether it is the top x number or the x percentage of resources based
on your preferred cost or utilization metric.

For example: Resource Inventory displays 1000 records for Compute service for a period of seven
days. You can further filter this display by choosing to view only top 25% of these resources, based
on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total)
sorted from highest to the lowest.

Exporting Reports

licking  Export  on top right of the report table will export all selected inventory
columns with any filter(s) applied. However, to export the full inventory data for the selected
month and service with all supported columns, click the Export  button on the top right of
the filters drop down in the toolbar of the tab.

Saving Resource Inventory Reports

You can save a report with its date, service and filter selections
and share this report with other users in the org by granting them “View Only” or “Edit” permissions. On the top right of the toolbar in
Resource Inventory UI, you can see an ellipse with three dots icon clicking on which would open the Report Actions menu with these options.

- **Save As Report:**  Using this option, you can save a copy of your report. This option is handy if someone has shared a report with
  you with a "View Only" access and you want to make changes to this report by making your own copy of it. Another use case for Save As Report is for
  Default Report. The Default Report cannot be modified and you would need to select "Save As Report" option to save any changes that you made to the
  Default Report.
- **Save Report:**  This option is used to save any changes made to the report you created or shared with you with an "Edit" permission
- **Share Report:**  Using this option, you can share your reports with other users in your organization by giving them "View Only" or "Edit"
  permissions.
- **Delete Report:**  You can delete your report by clicking on Delete Report.
- **Saved Report Date Range Handling:** Saved reports with unsupported (over 3-month)
  non-rolling date ranges will load with the date range reset to the default 7 days. A warning message
  will also be shown to the user that the date range has been reset. This behavior ensures saved
  reports remain accessible even when their stored date ranges fall outside the supported limit.

Note:

- Maximum number of reports that will be displayed in the Saved Reports drop down is 100.
- When a report is shared with a user, no email notifications will be sent.
- Resource Inventory supports a maximum of 3 months' data i.e. month-to-date + last 2 months. So the data would eventually
  expire in reports when it surpasses this retention period.

Using Resource Inventory

1. To access GCP Resource Inventory, navigate to  Insights> Resource Inventory
    and click the GCP  tab.

1. Select the service from  Services  dropdown for which you want to view your resource
   inventory.
2. Select the date range for which you want to view resource inventory data. You can choose to view
   up to 31 days of data at the maximum. The data displayed will sorted by Cost (Total)
    in descending order by default.
3. Click on any of the KPIs with the blue bar on the left to filter your reports based on that
   specific KPI.
4. Click the table settings button at the top right of resource inventory table to configure the
   measures and tags that you want displayed as columns in the table.

The selected measures and tags are displayed as columns in the table.

1. Click  Filters  to apply any filters to your inventory report.
2. Use the  Display  drop down above the Resource Inventory Details table to
   specify the top or bottom percentage of rows to display in the table and to sort the table
   descending by the preferred cost or utilization metric.
3. Click the Export  button at the top right of the Resource Inventory
   Details table to export all the columns showing in the table filtered by your filter settings. To
   export all the inventory data for the selected month and service with all the supported columns,
   click  Export  button, at the right of the Filters drop down in the toolbar
   of the tab.

Resource Measures showing 'Not Available'

For some resources, you may find that some measures, such as  Launch Date  ,  State,
 and  Size  among others, show as  Not Available  in the  Resource Inventory
 report. This means that Cloudability was not able to fetch
data for those specific measures due to one of the following reasons:

- You may not have done advanced credentialing for the account to which the particular
  resource(s) belong.
- The lifespan of the resource(s) may have been too short to capture the data for those measures.
- The utilization metrics for these resources may show as '0' (zero) in the report.

| GCP Compute | |
| --- | --- |
| Total Resources | Total number of resources in your inventory for the selected period . |
| Total Instances | Total number of compute instances excluding snapshots . |
| Newly Launched Resources | Number of resources that were launched in the selected period. |
| Cost (Total) | Cost (Total) for the Instances . |
| GCP Persistent Disk | |
| Total Volumes | Total number of volumes in your inventory for the selected period. |
| Newly Launched Volumes | Number of volumes that were launched in the selected period. |
| Cost (Total) | Cost (Total) for all the volumes. |
| Untagged Volumes | Number of volumes that do not have at least a single tag. |
| Unattached Volumes | Number of volumes that are not attached to any compute instance. |

**Parent topic:** [Resource Inventory](../product/resource-inventory.html)
