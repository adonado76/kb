---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "04-Insights-Resource-Inventory"
source_files_count: 6
last_updated: "2026-07-13"
---

# 04-Insights-Resource-Inventory

## Resource Inventory

<!-- sub-header -->
- **breadcrumb:** Insights > Resource Inventory
- **source_path:** SSVCLNQ/product/resource-inventory.html
- **original_file:** insights-resource-inventory.md
- **images:** []

## Resource Inventory

Resource Inventory enables creating a list of cloud resources from multiple accounts with various dimensions and metrics. By unifying billing, utilization, and descriptive meta data you are able to achieve a more comprehensive inventory view for your resources.

### Key Use Cases for Resource Inventory

1. Cost to Utilization Data Mapping Solution: By combining the Resource Inventory with Cloudability's synthetic tags (tag dimensions, account groups and business mappings), you can accurately map resource costs. For example, you can see the exact CPU and Memory utilization of a specific Compute Engine instance belonging to "Team Alpha" and allocate its cost accordingly. This enables the creation of robust show back reports for teams to understand their consumption and informed chargeback models for internal billing.
1. Waste Reduction Challenge: Over-provisioned resources lead to unnecessary cloud spend. Identifying underutilized Compute Engine instances or Managed Disks manually is time-consuming and prone to error. Solution: Leverage the CPU Utilization (Avg), Memory Utilization (Avg), and Memory Used metrics from the inventory. Identify instances with consistently low average CPU or memory usage. For Managed Disks, monitor their size relative to actual data stored to identify opportunities for downsizing.
1. Performance Optimization and Bottleneck Identification Challenge: Under-provisioned resources can lead to performance bottlenecks, impacting application responsiveness and user experience. Identifying the root cause requires detailed utilization data. Solution: Analyze CPU Utilization (Max), Memory Utilization (Max), and Network Utilization (Max). Spikes in these metrics could indicate a need to scale up resources. This data helps you proactively optimize resource allocation to ensure optimal application performance.
1. Proactive Issue Resolution Challenge: Unexpected cost spikes or performance degradation can be difficult to pinpoint without granular resource-level data. Solution: Regularly monitor the utilization metrics provided by the Resource Inventory. Sudden, unexplained increases in CPU Utilization (Min) or Memory Used on an otherwise stable instance could indicate a runaway process, misconfiguration, or even a security incident. By setting up alerts based on these metrics, you can detect anomalies early and take corrective action before they significantly impact costs or operations.
1. Lifecycle Management and Resource Governance Challenge: Tracking the lifecycle of cloud resources, from launch to de-provisioning, can be complex, leading to "zombie" resources that incur costs without providing value. Solution: The "launch date of resources" combined with utilization metrics, are invaluable. Identify resources that have been running for an extended period with persistently low utilization. For instance, a Compute Engine instance with a very old launch date and consistently low CPU Utilization (Avg) and Memory Utilization (Avg) might be a forgotten resource that can be safely terminated. This proactive approach ensures better resource governance and prevents unnecessary spending.

By providing a unified view of your inventory, complete with detailed utilization metrics and critical metadata, Cloudability empowers you to make data-driven decisions, optimize your cloud spend, and enhance the efficiency of your cloud operations.

---

## AWS Resource Inventory

<!-- sub-header -->
- **breadcrumb:** Insights > Resource Inventory > AWS Resource Inventory
- **source_path:** SSVCLNQ/product/aws-resource-inventory.html
- **original_file:** inventory-aws-resource.md
- **images:** []

## AWS Resource Inventory

AWS Resource Inventory feature for Cloudability enables you to produce an authoritative list of AWS cloud resources that existed and were billed during a specific reporting period. You have the flexibility to build this list from resources spanning multiple accounts and choose from different measures (dimensions and metrics) to surface the details relevant to them. This information - available for each cloud resource - unifies billing, utilization, and descriptive meta data to give you a more comprehensive inventory view.

### Getting started

AWS Resource Inventory reporting feature must be enabled for your Cloudability Org. You must reach out to your TAM/CSM/account point of contact from Apptio to get this done. Once enabled, allow 2-3 business days for the data to start appearing in your inventory reports. To get the full inventory data for AWS Lambda, you should enable Lambda Insights in your AWS console.

### Inventory Reporting Measures

- Measures are categorized as either general columns or tag columns. You can include up to 20 columns to an individual report.
- For each AWS service, a specific set of measures are supported.
- You can filter your respective inventory reports using any of the measures available within this feature.

### Clickable KPIs for Quick Filtering

For every service (For example: EC2, EBS), KPIs will be displayed at the top of the report to provide you with key summary information such as Inactive Instances and Untagged Instances . You can click and filter the Inventory report based on these KPIs to drill down to the specific report data you are looking for.

### Inventory Reporting Date Windows

- Choose the period in the date picker to view the inventory data for each service. The maximum allowed range for selection is 31 days. The resource inventory data is back filled to the beginning of the current month and is available on a three-month rolling window.
- Access resource inventory data for the current month along with the previous two months whenever needed.

### Statistical Filtering using the Display filter

From the inventory data generated for a specific service and time period, you can choose to display a subset of that data, whether it is the top x number or the x percentage of resources based on your preferred cost or utilization metric.

For example: Resource Inventory displays 1000 records for EC2 service for a period of seven days. You can further filter this display by choosing to view only top 25% of these resources, based on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total) sorted from highest to the lowest.

### Exporting Reports

Click Export on the report grid to export selected inventory columns with filter(s) applied. However, to export the full inventory data for the selected month and service for all supported columns, click the Export button, to the right of the Filters drop down in the toolbar of the tab.

### Saving Resource Inventory Reports

You can save a report with its date, service and filter selections and share this report with other users in the org by granting them “View Only” or “Edit” permissions. On the top right of the toolbar in Resource Inventory UI, you can see an ellipse with three dots icon clicking on which would open the Report Actions menu with these options.

- Save As Report: Using this option, you can save a copy of your report. This option is handy if someone has shared a report with you with a "View Only" access and you want to make changes to this report by making your own copy of it. Another use case for Save As Report is for Default Report. The Default Report cannot be modified and you would need to select "Save As Report" option to save any changes that you made to the Default Report.
- Save Report: This option is used to save any changes made to the report you created or shared with you with an "Edit" permission
- Share Report: Using this option, you can share your reports with other users in your organization by giving them "View Only" or "Edit" permissions.
- Delete Report: You can delete your report by clicking on Delete Report.
- Saved Report Date Range Handling: Saved reports with unsupported (over 3-month) non-rolling date ranges will load with the date range reset to the default 7 days. A warning message will also be shown to the user that the date range has been reset. This behavior ensures saved reports remain accessible even when their stored date ranges fall outside the supported limit.

- Maximum number of reports that will be displayed in the Saved Reports drop down is 100.
- When a report is shared with a user, no email notifications will be sent.
- Resource Inventory supports a maximum of 3 months' data i.e. month-to-date + last 2 months. So the data would eventually expire in reports when it surpasses this retention period.

### Using Resource Inventory

1. To access AWS Resource Inventory, navigate to Insights > Resource Inventory .
1. Select the service from the Services drop down for which you want to view your resource inventory.
1. Select the date range for which you want to view resource inventory data. You can choose to view up to 31 days of data at the maximum. The data displayed is sorted by Cost (Total) in descending order by default.
1. Click on the KPIs with a blue bar on the left to filter your reports based on it (e.g. Newly Launched ).
1. Click table settings to the top right of the Resource Inventory Details table to configure the measures and tags which you want displayed as columns in the table.
1. Click Filters to sort your inventory report.
1. Select Display above the Resource Inventory Details table. This specifies the top or bottom percentage of rows to display in the table and also sorts the table by your preferred cost or utilization metric in descending order.
1. Click Export to export the columns shown in the table, filtered by your filter settings. To export all inventory data for the selected month and service with supported columns, click the Export button to the right of the filters drop down in the toolbar of the tab.

Resources, like Launch Date, State, and Size are sometimes displayed as Not Available in the Resource Inventory report. This means that Cloudability was not able to fetch data for those specific measures due to one of the following reasons:

- You may not have done advanced credentialing for the account to which the particular resource(s) belong to.
- The lifespan of the resource(s) may have been too short to capture the data for those measures.
- The utilization metrics for these resources may show as '0' (zero) in the report.

The utilization metrics for these resources may show as '0' (zero) in the report.

### Usage Family of resources in Resource Inventory

Resource Inventory uses Resource ID as the unique identifier to display the resources. Unlike Cloudability reports, it does not support the Usage Family dimensions. Even if the same Resource ID is consumed under different Usage Families, Resource Inventory would display the Resource ID only once in the report.

### KPI Definitions

| KPI | Description |
| --- | --- |
| EC2 |
| Total instances | Total number of EC2 instances in your inventory for the selected period. |
| Newly Launched Instances | Number of EC2 instances that were launched in the selected period. |
| Inactive Instances | Number of EC2 instances that are not in "Running" state. |
| Cost (Total) | Cost (Total) for the EC2 instances for the selected period. |
| Untagged Instances | Number of EC2 instances that do not have a tag. |
| EBS |
| Total Resources | Total number of EBS resources in your inventory for the selected period. |
| Total Snapshots | Total number of EBS snapshots in your inventory for the selected period. |
| New Volumes Created | Number of EBS volumes that were created in the selected period. |
| Idle Volumes | Number of EBS volumes that are in "Available" state. |
| Cost (Total) | Cost (Total) for the EBS resources (both volumes and snapshots). |
| Untagged Volumes | Number of EBS volumes that do not have a tag. |
| Unattached Volumes | Number of EBS volumes that are not attached to any EC2 instances. |
| Lambda |
| Total Lambda Functions | Total number of Lambda Functions in your inventory for the selected period. |
| Compute Lambda Functions | Number of Lambda Functions for the selected period that come under the usage family "Instance Usage" |
| Cost (Total) | Cost (Total) for the Lambda Functions for the selected period. |
| Untagged Functions | Number of Lambda Functions that do not have a tag. |
| S3 |
| Total Resources | Total number of S3 buckets in your inventory for the selected period. |
| Idle Buckets | Number of S3 buckets that do not have any objects in them. |
| Untagged Buckets | Number of S3 buckets that do not have a tag |
| Cost (Total) | Cost (Total) for the S3 buckets. |
| RDS |
| Total Resources | Total number of RDS resources in your inventory for the selected period. |
| Total Snapshots | Total number of RDS snapshots in your inventory for the selected period. |
| Untagged Resources | Number of RDS resources that do not have a tag |
| Cost (Total) | Cost (Total) for the RDS resources. |
| Redshift |
| Total Resources | Total number of Redshift resources in your inventory for the selected period. |
| Total Snapshots | Total number of Redshift snapshots in your inventory for the selected period. |
| New Resources Created | Number of Redshift resources that were created in the selected period. |
| Untagged Resources | Number of Redshift resources that do not have a tag. |
| Cost (Total) | Cost (Total) for the Redshift resources. |

---

## Azure Resource Inventory

<!-- sub-header -->
- **breadcrumb:** Insights > Resource Inventory > Azure Resource Inventory
- **source_path:** SSVCLNQ/product/azure-resource-inventory.html
- **original_file:** inventory-azure-resource.md
- **images:** []

## Azure Resource Inventory

Azure Resource Inventory feature for Cloudability enables you to produce an authoritative list of Azure cloud resources that existed and were billed during a specific reporting period. You have the flexibility to build this list from resources spanning multiple accounts and choose from different measures (dimensions and metrics) to surface the details relevant to them. This information - available for each cloud resource - unifies billing, utilization, and descriptive meta data to give you a more comprehensive inventory view.

### Getting started

Azure Resource Inventory reporting feature must be enabled for your Cloudability Org. You must reach out to your TAM/CSM/account point of contact from Apptio to get this done. Once enabled, allow 2-3 business days for the data to start appearing in your inventory reports.

Inventory Reporting Measures

- Measures are categorized as either general columns or tag columns. You can include up to 20 columns to an individual report.
- For each Azure service, a specific set of measures are supported.
- You can filter your respective inventory reports using any of the measures available within this feature.

Clickable KPIs for Quick Filtering

For every service (For example: Compute or Managed Disks), KPIs will be displayed at the top of the report to provide you with key summary information such as Inactive Compute Instances and Untagged Compute Instances . You can click and filter the Inventory report based on these KPIs to drill down to the specific report data you are looking for.

Inventory Reporting Date Windows

You can choose the period in the date picker for which you want to view the inventory data for each service. Maximum allowed range for selection is 31 days. Upon enabling this feature, resource inventory data will be back filled to the beginning of the current month. Over time, inventory data will be available on a three-month rolling window. At any point in time, you will be able to access resource inventory data for the current month along with the previous two months.

Statistical Filtering using the Display Filter

From the inventory data generated for a specific service and time period, you can now choose to display a subset of that data, whether it is the top x number or the x percentage of resources based on your preferred cost or utilization metric.

For example: Resource Inventory displays 1000 records for Compute service for a period of seven days. You can further filter this display by choosing to view only top 25% of these resources, based on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total) sorted from highest to the lowest.

Exporting Reports

Clicking Export on top right of the report table will export all selected inventory columns with any filter(s) applied. However, to export the full inventory data for the selected month and service with all supported columns, click the Export button on the top right of the filters drop down in the toolbar of the tab.

Saving Resource Inventory Reports

You can save a report with its date, service and filter selections and share this report with other users in the org by granting them “View Only” or “Edit” permissions. On the top right of the toolbar in Resource Inventory UI, you can see an ellipse with three dots icon clicking on which would open the Report Actions menu with these options.

- Save As Report: Using this option, you can save a copy of your report. This option is handy if someone has shared a report with you with a "View Only" access and you want to make changes to this report by making your own copy of it. Another use case for Save As Report is for Default Report. The Default Report cannot be modified and you would need to select "Save As Report" option to save any changes that you made to the Default Report.
- Save Report: This option is used to save any changes made to the report you created or shared with you with an "Edit" permission
- Share Report: Using this option, you can share your reports with other users in your organization by giving them "View Only" or "Edit" permissions.
- Delete Report: You can delete your report by clicking on Delete Report.
- Saved Report Date Range Handling: Saved reports with unsupported (over 3-month) non-rolling date ranges will load with the date range reset to the default 7 days. A warning message will also be shown to the user that the date range has been reset. This behavior ensures saved reports remain accessible even when their stored date ranges fall outside the supported limit.

- Maximum number of reports that will be displayed in the Saved Reports drop down is 100.
- When a report is shared with a user, no email notifications will be sent.
- Resource Inventory supports a maximum of 3 months' data i.e. month-to-date + last 2 months. So the data would eventually expire in reports when it surpasses this retention period.

Using Resource Inventory

1. To access Azure Resource Inventory, navigate to Insights> Resource Inventory and click the Azure tab.

1. Select the service from Services dropdown for which you want to view your resource inventory.
1. Select the date range for which you want to view resource inventory data. You can choose to view up to 31 days of data at the maximum. The data displayed will be sorted by Cost (Total) in descending order by default.
1. Click on any of the KPIs with the blue bar on the left to filter your reports based on that specific KPI.
1. Click the table settings button at the top right of resource inventory table to configure the measures and tags that you want displayed as columns in the table.

The selected measures and tags are displayed as columns in the table.

1. Click Filters to apply any filters to your inventory report.
1. Use the Display drop down above the Resource Inventory Details table to specify the top or bottom percentage of rows to display in the table and to sort the table descending by the preferred cost or utilization metric.
1. Click the Export button at the top right of the Resource Inventory Details table to export all the columns showing in the table filtered by your filter settings. To export all the inventory data for the selected month and service with all the supported columns, click Export button, at the right of the Filters drop down in the toolbar of the tab.

Resource Measures showing 'Not Available'

For some resources, you may find that some measures, such as Launch Date , State, and Size among others, show as Not Available in the Resource Inventory report. This means that Cloudability was not able to fetch data for those specific measures due to one of the following reasons:

- You may not have done advanced credentialing for the account to which the particular resource(s) belong.

- The lifespan of the resource(s) may have been too short to capture the data for those measures.

- The utilization metrics for these resources may show as '0' (zero) in the report.

KPI Definitions

| KPI | Description | Azure Compute |
| --- | --- | --- |
| Total Compute Instances | Total number of compute instances in your inventory for the selected period. |
| Inactive Compute Instances | Number of compute instances that are in one of these states: Stopping , Stopped , Deallocated or Deallocating . |
| Cost (Total) | Cost (Total) for the compute instances. |
| Untagged Compute Instances | Number of compute instances that do not have a tag. |
| Managed Disk |
| Total Disks | Total number of Managed Disks in your inventory for the selected period. |
| Idle Disks | Number of Managed Disks that are in "Available" state. |
| Cost (Total) | Cost (Total) for the Managed Disks. |
| Untagged Disks | Number of Managed Disks that do not have a tag. |
| Unattached Disks | Number of Managed Disks that are not attached to any VM. |
| Database |
| Total Databases | Total number of databases in your inventory for the selected period. |
| Untagged Databases | Number of databases that do not have a tag. |
| Cost (Total) | Cost (Total) for the databases. |

---

## GCP Resource Inventory

<!-- sub-header -->
- **breadcrumb:** Insights > Resource Inventory > GCP Resource Inventory
- **source_path:** SSVCLNQ/product/gcp-resource-inventory.html
- **original_file:** inventory-gcp-resource.md
- **images:** []

## GCP Resource Inventory

GCP Resource Inventory feature for Cloudability enables you to produce an authoritative list of GCP cloud resources that existed and were billed during a specific reporting period. You have the flexibility to build this list from resources spanning multiple accounts and choose from different measures (dimensions and metrics) to surface the details relevant to them. This information - available for each cloud resource - unifies billing, utilization, and descriptive meta data to give you a more comprehensive inventory view.

### Getting started

GCP Resource Inventory reporting feature must be enabled for your Cloudability Org. You must reach out to your TAM/CSM/account point of contact from Apptio to get this done. Once enabled, allow 2-3 business days for the data to start appearing in your inventory reports.

Inventory Reporting Measures

- Measures are categorized as dimensions, metrics and tags (tags include Cloudability's tag dimensions, account groups and business mappings). You can include up to 20 columns to an individual report .
- For each GCP service, a specific set of measures are supported.
- You can filter your respective inventory reports using any of the measures available within this feature.

Clickable KPIs for Quick Filtering

For every service, KPIs will be displayed at the top of the report to provide you with key summary information such as Newly Launched Resources and Untagged Instances . You can click and filter the Inventory report based on these KPIs to drill down to the specific report data you are looking for.

Inventory Reporting Date Windows

You can choose the period in the date picker for which you want to view the inventory data for each service. Maximum allowed range for selection is 31 days. Upon enabling this feature, resource inventory data will be back filled to the beginning of the current month. Over time, inventory data will be available on a three-month rolling window. At any point in time, you will be able to access resource inventory data for the current month along with the previous two months.

Statistical Filtering using the Display Filter

From the inventory data generated for a specific service and time period, you can now choose to display a subset of that data, whether it is the top x number or the x percentage of resources based on your preferred cost or utilization metric.

For example: Resource Inventory displays 1000 records for Compute service for a period of seven days. You can further filter this display by choosing to view only top 25% of these resources, based on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total) sorted from highest to the lowest.

Exporting Reports

licking Export on top right of the report table will export all selected inventory columns with any filter(s) applied. However, to export the full inventory data for the selected month and service with all supported columns, click the Export button on the top right of the filters drop down in the toolbar of the tab.

Saving Resource Inventory Reports

You can save a report with its date, service and filter selections and share this report with other users in the org by granting them “View Only” or “Edit” permissions. On the top right of the toolbar in Resource Inventory UI, you can see an ellipse with three dots icon clicking on which would open the Report Actions menu with these options.

- Save As Report: Using this option, you can save a copy of your report. This option is handy if someone has shared a report with you with a "View Only" access and you want to make changes to this report by making your own copy of it. Another use case for Save As Report is for Default Report. The Default Report cannot be modified and you would need to select "Save As Report" option to save any changes that you made to the Default Report.
- Save Report: This option is used to save any changes made to the report you created or shared with you with an "Edit" permission
- Share Report: Using this option, you can share your reports with other users in your organization by giving them "View Only" or "Edit" permissions.
- Delete Report: You can delete your report by clicking on Delete Report.
- Saved Report Date Range Handling: Saved reports with unsupported (over 3-month) non-rolling date ranges will load with the date range reset to the default 7 days. A warning message will also be shown to the user that the date range has been reset. This behavior ensures saved reports remain accessible even when their stored date ranges fall outside the supported limit.

- Maximum number of reports that will be displayed in the Saved Reports drop down is 100.
- When a report is shared with a user, no email notifications will be sent.
- Resource Inventory supports a maximum of 3 months' data i.e. month-to-date + last 2 months. So the data would eventually expire in reports when it surpasses this retention period.

Using Resource Inventory

1. To access GCP Resource Inventory, navigate to Insights> Resource Inventory and click the GCP tab.

1. Select the service from Services dropdown for which you want to view your resource inventory.
1. Select the date range for which you want to view resource inventory data. You can choose to view up to 31 days of data at the maximum. The data displayed will sorted by Cost (Total) in descending order by default.
1. Click on any of the KPIs with the blue bar on the left to filter your reports based on that specific KPI.
1. Click the table settings button at the top right of resource inventory table to configure the measures and tags that you want displayed as columns in the table.

The selected measures and tags are displayed as columns in the table.

1. Click Filters to apply any filters to your inventory report.
1. Use the Display drop down above the Resource Inventory Details table to specify the top or bottom percentage of rows to display in the table and to sort the table descending by the preferred cost or utilization metric.
1. Click the Export button at the top right of the Resource Inventory Details table to export all the columns showing in the table filtered by your filter settings. To export all the inventory data for the selected month and service with all the supported columns, click Export button, at the right of the Filters drop down in the toolbar of the tab.

Resource Measures showing 'Not Available'

For some resources, you may find that some measures, such as Launch Date , State, and Size among others, show as Not Available in the Resource Inventory report. This means that Cloudability was not able to fetch data for those specific measures due to one of the following reasons:

- You may not have done advanced credentialing for the account to which the particular resource(s) belong.
- The lifespan of the resource(s) may have been too short to capture the data for those measures.
- The utilization metrics for these resources may show as '0' (zero) in the report.

| GCP Compute |
| --- |
| Total Resources | Total number of resources in your inventory for the selected period . |
| Total Instances | Total number of compute instances excluding snapshots . |
| Newly Launched Resources | Number of resources that were launched in the selected period. |
| Cost (Total) | Cost (Total) for the Instances . |
| GCP Persistent Disk |
| Total Volumes | Total number of volumes in your inventory for the selected period. |
| Newly Launched Volumes | Number of volumes that were launched in the selected period. |
| Cost (Total) | Cost (Total) for all the volumes. |
| Untagged Volumes | Number of volumes that do not have at least a single tag. |
| Unattached Volumes | Number of volumes that are not attached to any compute instance. |

---

## OCI Resource Inventory

<!-- sub-header -->
- **breadcrumb:** Insights > Resource Inventory > OCI Resource Inventory
- **source_path:** SSVCLNQ/product/oci-resource-inventory.html
- **original_file:** inventory-oci-resource.md
- **images:** []

## OCI Resource Inventory

OCI Resource Inventory feature for Cloudability enables you to produce an authoritative list of OCI cloud resources that existed and were billed during a specific reporting period. You have the flexibility to build this list from resources spanning multiple accounts and choose from different measures (dimensions and metrics) to surface the details relevant to them. At present, this information is only available for Virtual Machine resource - unifies billing, utilization, and descriptive meta data to give you a more comprehensive inventory view.

### Getting started

OCI Resource Inventory reporting feature must be enabled for your Cloudability Org. You must reach out to your TAM/CSM/account point of contact from IBM Cloudability to get this done. Once enabled, allow 2-3 business days for the data to start appearing in your inventory reports.

Inventory Reporting Measures

- Measures are categorized as dimensions, metrics and tags (tags include Cloudability's tag dimensions, account groups and business mappings). You can include up to 20 columns to an individual report.
- For OCI Virtual Machine service, a specific set of measures are supported.
- You can filter your respective inventory reports using any of the measures available within this feature.

Clickable KPIs for Quick Filtering

For every service, KPIs will be displayed at the top of the report to provide you with key summary information such as Total Resources and Untagged Instances . You can click and filter the Inventory report based on these KPIs to drill down to the specific report data you are looking for.

Inventory Reporting Date Windows

You can choose the period in the date picker for which you want to view the inventory data for each service. Maximum allowed range for selection is 31 days. Upon enabling this feature, resource inventory data will be back filled to the beginning of the current month. Over time, inventory data will be available on a three-month rolling window. At any point in time, you will be able to access resource inventory data for the current month along with the previous two months.

Statistical Filtering using the Display Filter

From the inventory data generated for a specific service and time period, you can now choose to display a subset of that data, whether it is the top x number or the x percentage of resources based on your preferred cost or utilization metric.

For example: Resource Inventory displays 1000 records for Compute service for a period of seven days. You can further filter this display by choosing to view only top 25% of these resources, based on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total) sorted from highest to the lowest.

Exporting Reports

Clicking Export on top right of the report table will export all selected inventory columns with any filter(s) applied. However, to export the full inventory data for the selected month and service with all supported columns, click the Export button on the top right of the filters drop down in the toolbar of the tab.

Saving Resource Inventory Reports

You can save a report with its date, service and filter selections and share this report with other users in the org by granting them “View Only” or “Edit” permissions. On the top right of the toolbar in Resource Inventory UI, you can see an ellipse with three dots icon clicking on which would open the Report Actions menu with these options.

- Save As Report: Using this option, you can save a copy of your report. This option is handy if someone has shared a report with you with a "View Only" access and you want to make changes to this report by making your own copy of it. Another use case for Save As Report is for Default Report. The Default Report cannot be modified and you would need to select "Save As Report" option to save any changes that you made to the Default Report.
- Save Report: This option is used to save any changes made to the report you created or shared with you with an "Edit" permission
- Share Report: Using this option, you can share your reports with other users in your organization by giving them "View Only" or "Edit" permissions.
- Delete Report: You can delete your report by clicking on Delete Report.
- Saved Report Date Range Handling: Saved reports with unsupported (over 3-month) non-rolling date ranges will load with the date range reset to the default 7 days. A warning message will also be shown to the user that the date range has been reset. This behavior ensures saved reports remain accessible even when their stored date ranges fall outside the supported limit.

- Maximum number of reports that will be displayed in the Saved Reports drop down is 100.
- When a report is shared with a user, no email notifications will be sent.
- Resource Inventory supports a maximum of 3 months' data i.e. month-to-date + last 2 months. So the data would eventually expire in reports when it surpasses this retention period.

Using Resource Inventory

1. To access OCI Resource Inventory, navigate to Insights> Resource Inventory and click the OCI tab.

1. Select the service from Services dropdown (at present only Virtual Machine) for which you want to view your resource inventory.
1. Select the date range for which you want to view resource inventory data. You can choose to view up to 31 days of data at the maximum. The data displayed will sorted by Cost (Total) in descending order by default.
1. Click on any of the KPIs with the blue bar on the left to filter your reports based on that specific KPI.
1. Click the table settings button at the top right of resource inventory table to configure the measures and tags that you want displayed as columns in the table.

The selected measures and tags are displayed as columns in the table.

1. Click Filters to apply any filters to your inventory report.
1. Use the Display drop down above the Resource Inventory Details table to specify the top or bottom percentage of rows to display in the table and to sort the table descending by the preferred cost or utilization metric.
1. Click the Export button at the top right of the Resource Inventory Details table to export all the columns showing in the table filtered by your filter settings. To export all the inventory data for the selected month and service with all the supported columns, click Export button, at the right of the Filters drop down in the toolbar of the tab.

Resource Measures showing 'Not Available'

For some resources, you may find that some measures, such as Launch Date , State, and Size among others, show as Not Available in the Resource Inventory report. This means that Cloudability was not able to fetch data for those specific measures due to one of the following reasons:

- You may not have done advanced credentialing for the account to which the particular resource(s) belong.
- The lifespan of the resource(s) may have been too short to capture the data for those measures.
- The utilization metrics for these resources may show as '0' (zero) in the report.

| OCI Compute |
| --- |
| Total Resources | Total number of VM (including snapshots/backups) for the selected period. |
| Total Instances | Total number of VM instances (excluding snapshots/backups) for the selected period. |
| Inactive VM Instances | Number of VM instances that are in one of these states - “terminating”, “stopping”, “stopped” or “terminated” |
| Cost (Total) | Total cost calculated by the unblended rate |
| Total Snapshots | Total number of VM snapshots (backups) for the selected period. |
| Untagged VM Instances | Number of instances that do not have a tags. |

---

## Resource Inventory FAQs

<!-- sub-header -->
- **breadcrumb:** Insights > Resource Inventory > Resource Inventory FAQs
- **source_path:** SSVCLNQ/product/resource-inventory-faqs.html
- **original_file:** inventory-resource-faqs.md
- **images:** []

## Resource Inventory FAQs

### Why can't I select the most recent 3 days in the Resource Inventory Date Range picker?

In Resource Inventory, we do not allow to select recent 3 days in the date range because some measures may take up to 72 hours to reflect in the inventory report and the data completeness is not guaranteed.

You will see a message in the date picker showing the available date range, with a reminder that the most recent 3 days are excluded.

### Why do the numbers in my saved report change over time?

There could be couple of reasons by numbers look different:

- If you ran a saved report where the date has crossed 90 days look back, it’ll automatically reset the date to 7 days. This is to ensure that report loads successfully. In this case, you’ll also see a flash warning message.
- If your report had ‘Rolling Date’ turned on and criteria was last 90 days, then numbers can change everyday.

### Why some resources show the state as 'Not Available'

Resource Inventory may display the state as “Not Available” in the following scenarios:

- Missing Permissions – If advanced credentialing is not configured, Resource Inventory will get the resource details from cost data which will not have all metadata, including the resource state.
- Short lived Resources – Resource Inventory collects data at defined intervals. If a resource is created and terminated between two collection cycles, its state and utilization details may not be captured and hence state will be absent.
- Snapshots – State information is not available for snapshot resources.
- Data transfer resources – Certain resources (for example, NAT Gateway data transfer) do not have an associated state, and will appear as “Not Available”.
- Azure terminated resources – In Azure, once a resource is terminated, even if its not a short lived resource, its state information is no longer available and is shown as “Not Available".

---
