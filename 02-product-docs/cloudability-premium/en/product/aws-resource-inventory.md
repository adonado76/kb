---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "AWS Resource Inventory"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Resource Inventory"
source_path: "product/aws-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Resource Inventory

AWS Resource Inventory feature for Cloudability enables you to produce an authoritative list of
AWS cloud resources that existed and were billed during a specific reporting period. You have the
flexibility to build this list from resources spanning multiple accounts and choose from different
measures (dimensions and metrics) to surface the details relevant to them. This information -
available for each cloud resource - unifies billing, utilization, and descriptive meta data to give
you a more comprehensive inventory view.

## Getting started

AWS Resource Inventory reporting feature must be enabled for your Cloudability Org. You must
reach out to your TAM/CSM/account point of contact from Apptio to get this done. Once enabled, allow
2-3 business days for the data to start appearing in your inventory reports. To get the full inventory data for AWS Lambda, you
should enable **Lambda Insights** in your AWS console.

## Inventory Reporting Measures

- Measures are categorized as either general columns or tag columns. You can include up to 20
  columns to an individual report.
- For each AWS service, a specific set of measures are supported.
- You can filter your respective inventory reports using any of the measures available within this
  feature.

## Clickable KPIs for Quick Filtering

For every service (For example: EC2, EBS), KPIs will be displayed at the top of the report to
provide you with key summary information such as  Inactive Instances
and  Untagged Instances . You can click and filter the Inventory report based
on these KPIs to drill down to the specific report data you are looking for.

## Inventory Reporting Date Windows

- Choose the period in the date picker to view the inventory data for each service.

  The maximum
  allowed range for selection is 31 days.

  The resource inventory data is back filled to the
  beginning of the current month and is available on a three-month rolling window.
- Access resource inventory data for the current month along with the previous two months whenever
  needed.

## Statistical Filtering using the Display filter

From the inventory data generated for a specific service and time period, you can choose to
display a subset of that data, whether it is the top x number or the x percentage of resources based
on your preferred cost or utilization metric.

For example: Resource Inventory displays 1000 records for EC2 service for a period of seven
days. You can further filter this display by choosing to view only top 25% of these resources, based
on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total)
sorted from highest to the lowest.

## Exporting Reports

Click  Export  on the report grid to export selected inventory columns
with filter(s) applied. However, to export the full inventory data for the selected month and
service for all supported columns, click the Export  button, to the right of
the Filters drop down in the toolbar of the tab.

## Saving Resource Inventory Reports

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

## Using Resource Inventory

1. To access AWS Resource Inventory, navigate to  Insights > Resource Inventory
   .
2. Select the service from the  Services  drop down for which you want to
   view your resource inventory.
3. Select the date range for which you want to view resource inventory data. You can choose to view
   up to 31 days of data at the maximum. The data displayed is sorted by Cost (Total)
    in descending order by default.
4. Click on the KPIs with a blue bar on the left to filter your reports based on it (e.g.
   Newly Launched).
5. Click table settings to the top right of the Resource Inventory Details table to
   configure the measures and tags which you want displayed as columns in the table.
6. Click Filters  to sort your inventory report.
7. Select  Display  above the Resource Inventory Details table. This
   specifies the top or bottom percentage of rows to display in the table and also sorts the table by
   your preferred cost or utilization metric in descending order.
8. Click Export to export the columns shown in the table, filtered by your
   filter settings. To export all inventory data for the selected month and service with supported
   columns, click the Export button to the right of the filters drop down in the
   toolbar of the tab.

Note:

Resources, like Launch Date, State, and
Size  are sometimes displayed as  Not Available  in the
 Resource Inventory  report. This means that Cloudability was not able to
fetch data for those specific measures due to one of the following reasons:

- You may not have done advanced credentialing for the account to which the particular resource(s)
  belong to.
- The lifespan of the resource(s) may have been too short to capture the data for those
  measures.
- The utilization metrics for these resources may show as '0' (zero) in the report.

Note:

The utilization metrics for these resources may show as '0' (zero) in the report.

## Usage Family of resources in Resource Inventory

Resource Inventory uses Resource ID as the unique identifier to display the resources. Unlike
Cloudability reports, it does not support the Usage Family dimensions. Even if the same Resource ID
is consumed under different Usage Families, Resource Inventory would display the Resource ID only
once in the report.

## KPI Definitions

| KPI | Description |
| --- | --- |
| EC2 | |
| Total instances | Total number of EC2 instances in your inventory for the selected period. |
| Newly Launched Instances | Number of EC2 instances that were launched in the selected period. |
| Inactive Instances | Number of EC2 instances that are not in "Running" state. |
| Cost (Total) | Cost (Total) for the EC2 instances for the selected period. |
| Untagged Instances | Number of EC2 instances that do not have a tag. |
| EBS | |
| Total Resources | Total number of EBS resources in your inventory for the selected period. |
| Total Snapshots | Total number of EBS snapshots in your inventory for the selected period. |
| New Volumes Created | Number of EBS volumes that were created in the selected period. |
| Idle Volumes | Number of EBS volumes that are in "Available" state. |
| Cost (Total) | Cost (Total) for the EBS resources (both volumes and snapshots). |
| Untagged Volumes | Number of EBS volumes that do not have a tag. |
| Unattached Volumes | Number of EBS volumes that are not attached to any EC2 instances. |
| Lambda | |
| Total Lambda Functions | Total number of Lambda Functions in your inventory for the selected period. |
| Compute Lambda Functions | Number of Lambda Functions for the selected period that come under the usage family "Instance Usage" |
| Cost (Total) | Cost (Total) for the Lambda Functions for the selected period. |
| Untagged Functions | Number of Lambda Functions that do not have a tag. |
| S3 | |
| Total Resources | Total number of S3 buckets in your inventory for the selected period. |
| Idle Buckets | Number of S3 buckets that do not have any objects in them. |
| Untagged Buckets | Number of S3 buckets that do not have a tag |
| Cost (Total) | Cost (Total) for the S3 buckets. |
| RDS | |
| Total Resources | Total number of RDS resources in your inventory for the selected period. |
| Total Snapshots | Total number of RDS snapshots in your inventory for the selected period. |
| Untagged Resources | Number of RDS resources that do not have a tag |
| Cost (Total) | Cost (Total) for the RDS resources. |
| Redshift | |
| Total Resources | Total number of Redshift resources in your inventory for the selected period. |
| Total Snapshots | Total number of Redshift snapshots in your inventory for the selected period. |
| New Resources Created | Number of Redshift resources that were created in the selected period. |
| Untagged Resources | Number of Redshift resources that do not have a tag. |
| Cost (Total) | Cost (Total) for the Redshift resources. |

**Parent topic:** [Resource Inventory](../product/resource-inventory.html)
