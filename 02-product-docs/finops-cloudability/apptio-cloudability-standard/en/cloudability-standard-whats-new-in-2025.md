---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cloudability Standard: What's new in 2025"
breadcrumb:
  - "What's new in Cloudability"
  - "Cloudability Standard: What's new in 2025"
source_path: "SSVCLNQ/release-notes-standard/whats-new-2025.html"
images:
  - "03-media/apptio-cloudability-standard/threshold-based_alerting4.jpg"
  - "03-media/apptio-cloudability-standard/wp_json1.jpg"
  - "03-media/apptio-cloudability-standard/wp_json2.jpg"
  - "03-media/apptio-cloudability-standard/wp_json3.jpg"
  - "03-media/apptio-cloudability-standard/oci-credentialing-namespace.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cloudability Standard: What's new in 2025

## Enhancements to User Management UI and Default View - December 19, 2025

This release introduces usability enhancements to User Management and Default View configuration , improving visibility and consistency for both admins and users.

- Updated User Management UI : The user edit experience has moved from a left-side panel to a new right-side panel under Users & Groups → Users . The new panel now: Displays all view types, including Hierarchical Views (HVs) and Views shared via User Groups Supports search and filtering by Selected , Unselected , or All views
- Hierarchical Views as Default Views : HVs can now be selected as default views: Admins can assign an HV as a user’s default from User Management Users can set an HV as their default view from Manage Profile → Preferences Only HVs the user has access to appear in the list; and only the highest level node which user has access to, can be set a default..
- Improved behavior when Views Are Deleted or Permissions Change If a default view (including an HV) is deleted, the user’s default will automatically revert to the Org-level default view. If no org-level default exists, the default view will be set to blank. Admins will now see a warning message when deleting views or changing permissions that may impact user defaults.

## Anomaly Alerts for Multiple Users - December 19, 2025

This release adds support for sharing anomaly alerts. Users can now include recipients directly on an alert, making it easy to notify others without requiring individual alert setup.

In addition, a new Alert Sharing tab is now available on the Alert Configuration page, providing a centralized view of all alert subscriptions.

.

## Vendor Credentials - Bulk Verify for Azure, OCI and IBM - December 19, 2025

This release adds support for bulk verify action in Vendor credentials for Azure, OCI and IBM which helps in easy onboarding of CSP accounts. With this release Bulk Actions functionality will be available to all customers having the below options.

- AWS - Bulk Save, Bulk Update, Bulk Verify
- Azure - Bulk Verify
- GCP - Bulk Save, Bulk Verify
- OCI - Bulk Verify
- IBM - Bulk Verify

## Enhanced Forecasting Beta – December 9, 2025

Try out our new Enhanced Forecast Page (Beta) that delivers more accurate, transparent, and flexible cloud spend forecasting. This new forecasting experience provides:

- Smarter forecasts powered by our new Intelligent Forecasting engine, which evaluates multiple models simultaneously and automatically selects the best fit.
- Choose your own spend drivers (up to three dimensions) to break down forecasts using the metrics that matter to you.
- Full forecast detail with grouping, filtering, sorting, and drill-down for deeper analysis.
- Greater transparency with model details, accuracy scoring, and inline visualizations for every line-item.
- More control with options to exclude unusual historical periods, view all model results and change default selection

During the initial rollout, this new page appears alongside the existing Forecast page under the Plan menu in the left navigation panel. At General Availability it will replace the current page.

## AWS - Support for CUR 2.0 Parquet format – December 9, 2025

This release adds support for AWS CUR 2.0 in parquet format which will help customers to configure either of the AWS CUR 2.0 file and compression formats.

• Text/csv – gzip

• Parquet - parquet

## Multi Cloud AI Services Dashboard – December 8, 2025

Cloudability announces the release of the Multi Cloud AI Services Dashboard, a comprehensive solution for monitoring AI and machine learning costs across AWS, Azure, and Google Cloud Platform. This new dashboard provides FinOps teams with insights into generative AI spending, enabling data-driven decisions to control costs while scaling AI initiatives.

Getting Started

The Multi Cloud AI Services Dashboard is available to all IBM Cloudability customers with connected AWS, Azure, or GCP accounts. To access the dashboard:

1. Navigate to Home > My Dashboard in the Cloudability console
1. Select Multi Cloud | AI Services Dashboard from your dashboard list
1. Use the date range selector to customize your analysis period
1. Scroll through the dashboard sections to explore cost details by service and provider

To learn more, contact your IBM Cloudability account team or Technical Account Manager.

## Vendor Credentials - Preventing data loss if user clicks outside of side panel – November 25, 2025

This release adds a modal to the vendor credentials page if the user clicks outside the side pane while filling in the credentials information.

Before this release, if the user clicks outside the side panel of Vendor credentials screen, then the screen used to go away and the data filled in the form was lost requiring the user to refill the information again.

## Cloud Sustainability - Embodied Emissions – November 14, 2025

Today we have launched inclusion of Embodied Emissions as part of Carbon Emissions reporting. This enhancement provides a more comprehensive representation of total carbon impact across your public cloud usage.

Users can now view the Carbon Emissions including both Operational and Embodied Emissions.

Before this release, users who wanted to measure their Carbon Emission could only access Operational Emissions.

With the inclusion of Embodied Emission, the “Estimated Carbon Emission” metric now reflects the total Carbon Emission which is the sum of Operational and Embodied Emissions.

## Cost Sharing for Reports and Dashboards – November 7, 2025

With this release, Cost Sharing is now available in Cloudability Reports and Dashboard Widgets. You can now visualize your cost data with allocated costs applied with a complete view of both direct and shared costs in your reports and dashboards.

- Toggle Cost Sharing per Report or Widget : Enable or disable Cost Sharing on native Cloudability reports and widgets to see how allocated costs affect your data.
- Visual indicators throughout the interface : Business dimensions with allocation rules now display allocation icons in dimension selectors, making it easy to identify which dimensions are affected by your Cost Sharing rules at a glance.
- Intelligent validation and error handling : The editor automatically manages dimension and metric compatibility.
- Seamless integration across features : Cost Sharing works consistently across Reports and Dashboards.

- Complete Cost Visibility : See the full picture of your costs including both direct expenses and costs allocated from shared resources. Flexible Analysis : Toggle between allocated and non-allocated views to understand the impact of your cost distribution rules. Prevented Errors : Automatic validation ensures your reports and widgets always use compatible combinations of dimensions, metrics, and filters. Consistent Experience : Cost Sharing works the same way across Reports and Dashboards, making it easy to build and share insights.

For more information, visit Cost Sharing for Reports and Dashboards .

## Optimization Hub in Cloudability: Centralized Insights for Commitment and Resource Optimization - November 7, 2025

Cloudability has added new functionality in the Optimization section to help users get a centralized view across their commitments and resource optimization initiatives. This dashboards show both forward looking optimization opportunities as well as backwards looking realized savings and impact of these efforts.

For complete visibility, users need access to cost data, as well as permissions to view Commitment, Rightsizing, and Rightsizing ROI data.

## Save and Share Reports in Cloudability Resource Inventory – October 31, 2025

Previously, resource inventory data can only be viewed in the UI and at best exported in CSV format – once user navigates away from the Resource Inventory module the queried data and filters would get reset. With this release, we support the capability to save a specific report with its date, service and filter selections and share this report with other users in the org by granting them “View Only” or “Edit” permissions. We also support "rolling" date functionality for the saved reports. The ability to save and share resource inventory reports would empower the creation of robust show back reports for teams to understand their consumption and informed chargeback models for internal billing.

## Option to exclude resources from recommendations and display of full region names in Cloudability Workload Planning - October 30, 2025

With this release, we have done 2 enhancements:

1. Option for admin users to specify those resource types that should not appear in the WLP recommendations for their org. This can be done using either of these 2 options: by adding the keyword so that the recommendations would skip those resource types that contain the keyword. Eg: giving the value "xlarge" would exclude all those resources that has "xlarge" in their names. by adding asterix (*) along with the keyword so that the recommendations would skip those resource types that starts with that keyword. Eg: giving the value "t4*" would exclude all those resources that starts with "t4".
1. Previously WLP showed only the region codes (eg: us-east-1). Now we show the entire region name along with their respective region codes (in parenthesis). Eg: us-east-1 will now be shown as US East N. Virginia (us-east-1). The regions are also sorted in the alphabetical order while selecting under the Common Information section

## Rightsizing ROI: Ticket Deletion and Filters – October 24, 2025

Rightsizing ROI : Allow ticket deletion and date filtering

Cloudability’s rightsizing ROI feature has been enhanced with new functionality to improve usability:

Savings Visualization : A new chart has been added to the Rightsizing ROI page which displays the 30 days savings amount in the month which it was implemented/closed. This helps users understand the impact of actions taken throughout various periods of time.

Ticket Deletion : Now Rightsizing ROI users can delete existing tickets that are no longer relevant. Users can eliminate noise for recommendations tickets that no longer apply or users want to delete and create new tickets based on updated recommendations.

Date Filtering : Users can now filter by date ranges (Created or Closed date) in the uI to focus their analysis or savings reporting on specific windows of time

Filtering and ticket deletion functionality is supported in the Cloudability UI as well as in the Rightsizing ROI API.

## Hierarchical Account Selection for GCP Commitment Recommendations – October 16, 2025

Today, we delivered an incremental feature to support our customers with multiple GCP Billing Accounts. The account picker on the GCP recommendations page is now multiselect and hierarchal. As a result, recommendations for different Billing Accounts can all be shown on a single page. All accounts is now the default selection and the Billing Account has been added to the table.

Now explicitly, the account selection on Recs is a usage picker. The recommendation is driven off of whatever spend is under the accounts selected.

For more information, visit the commitment management help documentation.

## Export reports in user-defined locale format – October 16, 2025

Today, Cloudability Reports introduced an enhancement allowing users to export the Report data in a CSV format that is consistent with their environment's selected locale format, using either a dot "." or a comma "," as a decimal separator.Locale settings can be modified on the “Currency” tab under the "Manage Profile” settings by the account administrator.

## Improved Price Transparency and Simplified Object Storage Configuration in Cloudability Workload Planning – October 14, 2025

1. We’re introducing a new calculator icon beside each pricing recommendation in Workload Planning. Clicking the icon now displays the exact formula used to calculate the pricing, helping you clearly understand the cost breakdown. This enhancement addresses previous customer feedback around reconciling price differences between Workload Planning and native cloud pricing calculators.
1. Additionally, we’ve removed the resource type selection for the Object Storage service. This selection was redundant since all configuration options for Object Storage are already displayed in the Recommendations screen. This update simplifies the experience while maintaining full visibility into cost optimization opportunities.

## FOCUS 1.1 Support in Cloudability – October 13, 2025

Starting today, customers can easily ingest any dataset in Cloudability that complies with the FOCUS v1.1 specification, in addition to FOCUS v1.0 , and gain cost visibility into the ingested spend.

There is no change to the credentialing process for the FOCUS 1.1 format and it follows the same process as FOCUS 1.0.

## Commitment Support for AWS OpenSearch Reserved Instances – October 10, 2025

Today, we delivered support for AWS OpenSearch Reserved Instances. The eighth AWS commitment type supported, OpenSearch commitments provide a discount on on-demand in exchange for a one or three year commitment to hourly usage. This commitment type is categorized as a resource-based commitment, and as such, requires selection specific usage parameters: Instance Type, Payment Option, and Region. This commitment behaves similarly to the other non-compute AWS commitment types. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

## Azure Cost Management Exports: Gzip Compression support – October 9, 2025

- Export format : CSV
- Compression : None or Gzip

This would help reduce the file size of Azure exports.

## Cost Sharing Configuration Enhancement - Automatically Allocate to New Business Dimension Values – October 2, 2025

This release introduces an improvement to how cost sharing rules handle new business dimension values in Cloudability.

You can configure your cost sharing rules and corresponding buckets as an include or exclude statement. When selecting ‘include’, you are explicitly including the business dimension values you would like to allocate to. When you select ‘exclude’, you will allocate to all business dimension values (including new business dimension values) by default, unless you choose to explicitly exclude them.

The new Exclude helps eliminate the manual work of updating each cost sharing rule whenever you add new values to your business dimensions.

## Cloudability Containers: IBM FinOps Agent – October 1, 2025

This release introduces the IBM FinOps Agent. The IBM FinOps Agent consolidates and streamlines metrics collection while introducing new capabilities in security, resiliency, and installation experience.

IBM FinOps Agent is designed to replace the legacy Metrics Agent. It will also serve as the data foundation for future feature releases.

New Features:

- Helm-based installation: Aligns with Kubernetes best practices to simplify deployment and upgrades.
- Self-managed API keys: Integrates with Frontdoor API keys, letting you create, rotate, and manage credentials to meet your security requirements.
- Improved resiliency: Disaster recovery for uploads: Uses persistent volumes to preserve collected data during restarts or service issues. Short-lived pod capture: More accurately attributes costs to transient workloads.
- Future-ready architecture: Provides the foundation for future innovations in container insight

Visit Provision your container agent to learn more.

## Commitment Support for Azure Database for PostgreSQL – September 30th, 2025

Today, we delivered support for Azure Database for PostgreSQL. The tenth Azure commitment type supported, Azure Database for PostgreSQL commitments provide a discount on compute in exchange for a one or three year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Deployment Option, Instance, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

## Commitment Support for Azure Blob Storage Reserved Capacity – September 29th, 2025

Today, we delivered support for Azure Blob Storage Reserved Capacity. The ninth Azure commitment type supported, Azure Blob Storage Reserved Capacity commitments provide a discount on capacity for block blobs and for Azure Data Lake Storage data in exchange for a one or three year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Access Tier, Redundancy, Size, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

## Usability Enhancements – Views, Users and Groups – September 29, 2025

This release provides multiple usability enhancements to Views, Users and Groups feature:

- Duplicate/Clone a View - As a View Admin, you often need to create multiple views that share similar filters and permissions. Manually recreating each view can be time-consuming and repetitive. View Admins can now use ‘Duplicate’ option to duplicate/clone views with one click—copying filters, permissions, and settings instantly. Just rename and adjust as needed. This saves time and reduces errors when creating similar views. For more information, see Duplicate a View .
- Show Default View Usage - Before deleting or restricting access to a view, Admins can now gain visibility into who is actively using it as their default. New UI option ‘Show Default Usage’ lets admins see users who have set a view as their default - whether shared directly or via groups. This will help view admins make informed decisions before deleting or restricting views. For more information, see Show Default Usage .
- Enhanced CSV Export for Views - CSV exports now include Default View Users, Groups Shared With, Owner, and Description fields. Default View Users list helps admin identify the users who are using it as a default view. These additions improve visibility and collaboration among View Admins.
- Duplicate View Name Validation - View names are now validated as you type during creation. If a name already exists, you’ll see an error and the Save button is disabled. This prevents the panel from closing and ensures you enter a unique name without losing your work.
- Edit Multiple in View Assignment UI - This fix on View’s assignment UI restores visibility of users and groups for ‘Edit Multiple’ feature. A new warning clarifies that changes apply to all selected views - preventing accidental bulk edits.
- Public APIs for User & Entra ID Groups - User Groups and Entra ID Groups now have public APIs. This enables easier integration and automation of group-related workflows. For more information, see API documentation .
- Email Visibility and Email Search in User Management - User management UI (under Settings > Users & Groups) now shows email addresses and supports email-based search. This helps admins quickly identify users, especially when names are similar. For more information, see Manage Users .

## Pivot Tables in Dashboards – September 24, 2025

Cloudability Dashboards introduces pivot table functionality. This improvement allows users to use Dimension values as columns, making it easier to analyze the metric breakdown by any dimension.

Pivot tables provide a powerful way to summarize, analyze and explore your data by using any dimension’s values as the table column. Users can easily aggregate data by category, date or any other dimension.

These tables are enabled by default for all existing Cloudability Dashboard tables. Additional control functionality, such as enabling/disabling pivots and configuring a default pivot value, will be added soon.

## Integration with Jira Cloud and ServiceNow – September 24, 2025

With this release, we introduce support for integrating Jira Cloud and ServiceNow with Anomaly Detection . This enables users to quickly create and track anomaly investigation tickets, with automatic bi-directional status updates, streamlining workflows and accelerating incident resolution.

## Support for AWS Lambda in Cloudability Resource Inventory – September 19, 2025

With this release, we introduce support for AWS Lambda service in Resource Inventory which would help customers to build an authoritative list of their AWS lambda resources. They can combine cost, utilization and other key resource level insights for their Lambda resources like Function Memory Size, Function Last Modified, Average Number of Invocations etc. that would help them take optimization actions more proactively.

## Bulk Actions on Vendor Credentialing AWS/GCP – September 18, 2025

Cloudability vendor credentials introduces bulk actions for AWS and GCP. This helps in easy onboarding of AWS and GCP accounts as users can quickly Save, Update or Verify accounts.

AWS Documentation - AWS Credentialing using Bulk Actions

GCP Documentation - GCP Credentialing using Bulk Actions

## Usability Enhancements in Cloudability Resource Inventory – September 10, 2025

This release includes 2 usability enhancements

- Enhanced Statistical Filtering - Previously, the Display Top/Bottom filters in Resource Inventory always applied to the full report, even if users had other global filters in place. With this release, the Top/Bottom selection now applies directly to the filtered dataset, ensuring users see only the most relevant resources. For example, if user has filtered a report down to 70 records from 100 (using global filters) and then selected Top 50%, they will now see the top 35 from those 70—not from the original 100.
- New KPI for Azure - we added a new KPI called Total Instances in Azure compute service that allows users to quickly filter those compute instances coming under the usage family of instance usage from other usage families like Data Transfer, Licenses etc.

## Cloudability Governance - Public Preview – September 10, 2025

Cloudability launches Governance Public Preview, a new capability that delivers proactive cost insights and policy enforcement directly in the engineering workflow. Starting today, teams can ensure that infrastructure changes are both cost-efficient and compliant with organizational policies before they are deployed.

Cloudability Governance is now available for DevOps engineers , Platform Admins , and FinOps teams who manage AWS resources and use Terraform — whether through Terraform Community , HCP Terraform or Terraform Enterprise — for their infrastructure as code solution. This feature is designed for teams that host their code repositories on GitHub.com , including GitHub Enterprise Cloud .

Previously, FinOps practices were often introduced too late in the development lifecycle, leading to misalignment between Finance and Engineering. This delay forced costly rework, as teams relied on manual reviews or post-deployment audits to catch cost inefficiencies and policy violations — resulting in overspending, compliance risks, and unexpected remediation tasks for engineers.

Cloudability Governance (Public Preview)

Description

Cloudability Governance integrates with GitHub and Terraform to bring FinOps policy enforcement and cost visibility into the CI/CD pipeline. Key capabilities include:

- Pre-deployment Cost Estimation : Real-time AWS cost estimates, including custom pricing and EA discounts, directly in GitHub and Terraform workflows
- Get Cost Optimized Resource Selection : Recommendations for lower-cost EC2 and RDS alternatives with similar configurations
- Policy Enforcement at IaC Level : Enforce mandatory tags, block legacy resources, and set budget thresholds
- Compliance Monitoring : Centralized dashboard to track adherence to FinOps policies
- PR Management : Identify and review non-compliant pull requests with built-in approval workflows
- Run Task Integration with HCP Terraform : Seamlessly integrate Cloudability Governance as a Run Task in HCP Terraform workspaces. This allows policy checks to be automatically triggered during the plan phase of a Terraform run, enabling advisory or mandatory enforcement before infrastructure is provisioned. This feature shifts cloud cost management from reactive to proactive—helping teams prevent overspending and policy violations before infrastructure is deployed.

For more information, see Governance - Getting Started

## Deselect all dimensions in Dashboard – September 4, 2025

Cloudability Dashboards introduces an improvement that allows users to select a single Dimension from the Chart’s legend. They can focus on a single Dimensions easily, without having to discard other Dimensions from the legend individually.

## Support for OCI Managed Databases in Workload Planning – August 28, 2025

The Workload Planning users can create workload estimates for OCI Managed Database. Previously, Managed Databases service was supported for all cloud vendors except OCI. With this release, we are supporting MySQL and PostgreSQL which are the Managed Database services available for OCI today.

## Adjust Negative Values in Dashboards Charts – August 27, 2025

This release introduces an improvement that allows users to automatically scale their charts Y-axis to adjust for negative values. Previously, all charts' axes started at 0 and viewing negative values required manually configuring the static 'start scale' option. This option is enabled by default for new charts and users can still opt-out of the functionality by deselecting the 'Start scale from lowest value' checkbox. Both existing and previously configured charts will not change their behavior.

## Copy and Paste Comma-Separated List of Filters in Dashboards and Reports – August 27, 2025

This release introduces an improvement allowing users to copy and paste a comma-separated list of filters in Cloudability Dashboards and Reports.

- Copy the list of filters' values by using Ctrl+C in the values field.
- Paste a comma-separated list into the value field, using Ctrl+V, that will be automatically separated into individual values.
- Values containing the comma "," as part of the value are escaped as follows: "single\,value".

## User Groups and Entra ID Group Usability Enhancements – August 25, 2025

This release introduces more usability improvements to the User Groups and Entra ID Groups features:

- Delete confirmation for User/Entra ID Groups now displays the number of users in the group.
- Group names which are limited to 63 characters, now provides real-time validation and improved error messages.
- Sorting is enabled on all columns in the User and Entra ID Groups lists, with default sorting by Created Date (newest first)
- Default scope and hint text added to the Entra ID sync modal for better usability.
- Minor UI changes on the Users screen.

For more information about User Groups and Entra ID Groups, see Manage Users and User Groups

## Cloudability Containers: Introducing Pre & Post Visualization Filter – August 14, 2025

This release introduces Pre and Post Visualization Filters, enabling precision control over data filter and display across Cloudability container dashboards and widgets.

- Pre-Visualization Filters are applied before data aggregation, similar to filters presently used in Cloudability.
- Post-Visualization Filters are applied after data aggregation, allowing refinement and focus on displayed results without altering aggregated values.

The new filters are available in Dashboard Table View as well as the following Custom Widgets:

- Custom Time Series
- Custom Top/Bottom
- Custom Allocated vs Idle

Custom KPI widgets support Pre-Visualization filters only.

Additional enhancements :

- Dynamic input handling to adjust input types automatically based on selected metrics.
- Validation rules to prevents incompatible filter/ metric combinations.
- New and enhanced user interface for easier navigation.
- Capability of filters to use the AND operator to combine multiple conditions.

For more information on Cloudability containers, see Containers Insights: Dashboard and Widget Guide .

## Cloudability Containers: Introducing Metrics Agent Observability tool – August 14, 2025

This release introduces the Agent Observability Tool, providing you real-time visibility into the health and status of Cloudability metrics agents across all your Kubernetes clusters. The data is represented in a table with the following fields as columns:

- Cluster List – Displays all clusters where a Cloudability metrics agent is installed.
- Agent Status – Shows whether your agent is Active or Inactive. Status is set to Inactive if Last Seen value is greater than 12 hours for the cluster.
- Agent Version – Shows the installed version of the metrics agent so you can ensure you’re running the latest release.
- Cluster Version – Displays the Kubernetes/ Openshift version in use for each cluster.
- Last Seen – Indicates the last time Cloudability received data from the metrics agent.
- Cluster Type – Identifies the type of cluster (e.g., EKS, ROSA).
- Vendor – Shows the cloud service provider associated with the cluster (e.g., AWS).
- Filter Agent Status Filter – Filters the list by Active, Inactive, or All agents to focus on clusters requiring attention. Vendor Filter – Filter clusters running on specific cloud providers for targeted monitoring.

For more information, see Agent Observatory Tool .

## Enhancements to Users & Groups feature – August 13, 2025

This release introduces two improvements to the recently launched User Groups and Entra ID Groups features:

- Permission-Based Access : Previously limited to the 'Cloudability Admin' role, access to User Groups and Entra ID Groups is now aligned with existing permissions. This ensures that admins who previously had access to the User Management feature will continue to have access to Users & Groups without needing an additional role.
- Delete Entra ID Groups : You can now delete Entra ID Groups in Cloudability. This update fulfills a post-GA commitment by delivering the promised support for Entra ID Group deletion.

## FinOps Foundation FOCUS Validator in the Other Data Sources (FOCUS)– August 7, 2025

This release adds the FinOps Foundation FOCUS validator link in the credentialing screen for Other data sources (FOCUS) within Cloudability.

This would help validate the FOCUS formatted file and check for any errors before uploading the file into shared storage for data ingress.

## Supporting Kubernetes Service in Workload Planning – August 5, 2025

Workload Planning users can create workload estimates for Kubernetes service across different cloud vendors. Like Virtual Machines and Databases, you can do it for AWS, Azure, GCP and OCI. Select Kubernetes from the Service Type dropdown and provide the number of clusters to generate different pricing options. Optionally, define your specific node configuration to get the combined pricing recommendations for both clusters and VMs.

## Cloudability Containers Insights: Change in cost allocation strategy for Azure clusters – August 4, 2025

Cloudability introduces grouping of metrics and dimensions in the widget edit mode for easy navigation. Admins can expand and collapse the lists of measures based on the data source. This feature is available in both Dashboards and Reports.

This release enhances the cost allocation methodology for Azure Kubernetes clusters for Cloudability Container Insights. Costs are now allocated at the node level enabling PVC (Persistent Volume Claim) allocation for the Azure CSI-Managed storage.

The following enhancements have been made to enhance cost distribution across workloads:

- Node-level cost allocation: Costs are now accurately allocated based on the actual node a pod runs on, factoring in node type, uptime, and usage patterns.
- PVC cost allocation: PVC costs provisioned via Azure’s CSI driver are now directly attributed to workloads consuming them.
- Miscellaneous costs: Azure-native cluster overheads such as public IPs and load balancers are now categorized distinctly under "Miscellaneous" to improve visibility.
- Improved container-level accuracy: Cost allocation now reflects true workload resource usage instead of averaged values across all nodes.

- Receive better visibility into actual workload costs.
- Optimize node types and schedule for cost efficiency.
- Segregate overheads for application and infrastructure.

## Grouping of Metrics and Dimensions in Widget Edit – July 30, 2025

Cloudability introduces grouping of metrics and dimensions in the widget edit mode for easy navigation. Admins can expand and collapse the lists of measures based on the data source. This feature is available in both Dashboards and Reports.

## Cloud Spend Summary Email Enhancements – July 30, 2025

The following enhancements have been made to spend summary email content:

- Added the Cloudability environment name in the email
- Added the last updated date for the month end estimate
- Reduced the delivery time window for emails from 10 to 3 hours

## Rightsizing ROI: Fix to Realized Savings Calculation – July 25, 2025

This release fixes the issue with display of normalized realized savings value in Cloudability Rightsizing ROI.

Rightsizing ROI tickets show realized savings normalized to a 30-day period. Previously, for some manually created tickets with terminated resources, the realized savings value was only calculated for a 10-day period.

All tickets will reflect a 30-day calculation period resulting in an increase in value for your historic realized savings.

For more information, see Rightsizing ROI End Points .

## Supporting Email Alerts for Vendor Credentials Status – July 24, 2025

This release introduces email alerts for the status of accounts under Vendor Credentials in Cloudability.

- Opt-in alerts: Admins can subscribe for daily, weekly, or monthly alerts. Check whether your accounts are fully credentialed, or are incomplete or have errors.
- Actionable insights: Each email includes direct links to Cloudability with pre-applied vendor and account filters, making it easy to act where needed.

## Adding New Banners for Vendor Credentials Actions – July 24, 2025

This release adds two banners on the Vendor Credentials page which summarizes the action needed on various accounts in Cloudability. These banners, which act as quick filters, highlight the number of invalid and incomplete accounts where action is needed.

## Usability Enhancements in Workload Planning – July 16, 2025

- Provide list of all the supported resource types for bulk import
- Auto fill input parameters in Attached Storage as per the VM configuration entered
- Categorization of compute and database resource types within the resource type dropdown
- Support for email notifications when a workload has been shared

For more information, see Get Recommendations for Workload Planning

## Cloudability Premium: Disabling Turbonomic integration for customers – July 15, 2025

This release disables Turbonomic as a data source in Vendor Credentials for Cloudability Premium Customers. You can now select any period for daily automatic updates on the dashboard.

Cloudability Premium customers have unified credentialing between Cloudability and Turbonomic. They will continue to view these metrics in Turbonomic by switching over via their Frontdoor environment. For Cloudability Standard and Essentials customers, Turbonomic is still available to add as a data source in Cloudability.

For more information, see Turbonomic .

## Cloudability Dashboards: Custom rolling date changes – July 9, 2025

This release adds another option to Cloudability dashboards for configuring the rolling date ranges. You can now select any period for daily automatic updates on the dashboard.

## Cloudability Vendor Credentials: Deprecating Azure EA reporting APIs support – July 9, 2025

This release deprecates support for APIs in Cloudability vendor credentials for Microsoft Azure.

Going forward, use the cost management APIs or Azure exports for adding Azure EA accounts into Cloudability.

For more information, see Connecting with Azure EA – Cost Details API .

## User Group and Entra ID Group Support in Cloudability – July 8, 2025

This release includes support for user groups and Microsoft Entra ID Groups in Cloudability. Admins can now create user groups manually or import them from Entra ID. This helps you efficiently assign users Views based on teams, roles, or business units.

Enhancements:

- Manual user group creation: Create and manage custom user groups in Cloudability and add users to them. Once created, you can work with these groups in View assignment.
- Microsoft Entra ID Group integration : Credential your Microsoft Entra ID and import Entra ID groups to Cloudability using the custom sync criteria.

For more information, see Manage Users and User Groups and Connect Microsoft Entra ID

## Cloudability Containers: Configuration for setting up proxy on GetUploadURL– July 7, 2025

This release introduces new configuration options in the Cloudability metrics agent. This provides more flexibility to manage proxy settings for specific outbound calls by the agent.

The Cloudability metrics agent makes two outbound calls:

- The first call generates an URL.</li><li>The second call uploads the data to the S3 bucket using the URL.
- The new configuration flag CLOUDABILITY_USE_PROXY_FOR_GETTING_UPLOAD_URL_ONLY for the cloudability metrics agent when set to true applies the proxy to the first call only.

For more information, see Kubernetes Cluster Provisioning

## Cloudability Containers 1.0 deprecation – July 7, 2025

This release deprecates Container Insights 1.0. You will now be redirected to Container Insights 2.0.

Going forward, use the cost management APIs or Azure exports for adding Azure EA accounts into Cloudability.

For more information, see Cloudability Container Insights 2.0. .

## Change date ranges on Cloudability dashboards – July 1, 2025

This release includes updates to Cloudability dashboards letting you change the date range for all widgets in a report.

The global date range selector is available on all reports by default.

## Cloudability Metrics Agent 2.13.0 – Secret Management and Template Updates – July 1, 2025

This release updates Metrics Agent version 2.13.0 with the capability for CLOUDABILITY_API_KEY to align with Kubernetes best practices for secret management. This enhances the security of credentials used by the agent.

Enhancements included:

- Volume-mounted secret management : The CLOUDABILITY_API_KEY is now stored as a volume in the Metrics Agent pod replacing the previous method of setting it directly as an environment variable.
- The UI and helm provisioning support : This change is reflected in the provisioning workflow within the UI and for Helm installs from version 2.13.0 onwards. For Helm installs, decode the base64 key first. For detailed setup instructions, see https://cloudability.github.io/metrics-agent/ .
- Provisioning endpoint update : The following updates are made for the provisioning endpoint for all customers irrespective of the Metrics Agent version. API key automatically moved to Kubernetes Secret. Base64 used to encode the API key data ensuring seamless execution of kubectl apply -f <template> during provisioning.
- Configurable file path : You can now define where to store the API key using the CLOUDABILITY_API_KEY_FILEPATH environment variable for custom mount paths.

The Cloudability Metrics Agent will continue supporting the CLOUDABILITY_API_KEY as an environment variable for backward compatibility, it will advise you to transition to volume-mounted secrets.

For more information, see Kubernetes Cluster Provisioning .

## Cloudability Hierarchical Data & Views – June 30, 2025

This release adds hierarchy support for Business Mappings and Views to manage cost rollups in Cloudability.

- A business mapping for each layer with rollup logic
- A corresponding set of views nested by mapping

Enhancements:

Create hierarchical business mappings with cost accuracy

- Automate business mappings to support cost rollups
- Enable multi-level reporting with business dimensions

Streamline creation and maintenance of rollup views

- Automatically generate hierarchical views from hierarchical business mappings
- Manage data and views from a single control point
- Simplify user sharing and access management with View Access inheritance

- CFP Integration
- Multiple levels of cost ownership in plans Support for up to 5 cost ownership dimensions Automatically roll up costs by budget hierarchy
- Use views to filter plans Apply hierarchical views to filter plans Control access and visibility based on rollup levels

For more information, see Organize Views using Hierarchical Views .

## Support for Kubernetes v1.33 & OpenShift 4.18 – June 30, 2025

This release includes support for Kubernetes version 1.33 & OpenShift 4.18 for Cloudability container agent. This update allows you to maintain full container cost visibility for Kubernetes v1.33 on EKS, GKE, AKS, and OKE environments and Open Shift 4.18.

For more information, see Kubernetes Cluster Provisioning .

## Views Usability Enhancements – June 30, 2025

We launched the following key usability enhancements to Views:

- Display of owner names alongside each View for transparency, accountability and better maintenance
- Addition of a description field for each View to add contextual information about its purpose and usage for better management of outdated and redundant Views

## Shared Costs in Reporting API – June 27, 2025

This release introduces Shared Costs in Cloudability’s Reporting API. With newly added dimensions like Cost Type and Allocation Source, you can now access data around allocated costs more efficiently

For more information, see Cost Reporting End Point .

## Support for GCP Resource Inventory – June 26, 2025

This release introduces support for GCP Resource Inventory. This feature lets you report your cost, utilization, and resource level metadata for Compute and Persistent disk services in a single pane of glass view.

You can enable the Resource Inventory feature from the respective Active Admin portal depending on your geographic location. Within 3-4 business days of its enablement, you will receive complete inventory data into Cloudability.

For more information on this feature, See GCP Resource Inventory .

## Removing Label Filter Dropdown from Container Dashboard – June 25, 2025

The Label dropdown filter has been removed from the Container Cost Allocation page. The existing Label filters are automatically saved under Add Filter. Navigate to Add Filter > Dimension > Label to add same filters by Label Key and Value.

## Anomaly Detection Alert for Initial Surge​ – June 25, 2025

This release includes improvements to the anomaly detection algorithm. These improvements ensure prompt customer alerts for first-time surge spends in any service. It also includes coverage for reactivated spend anomalies.

For more information on this feature, See Anomaly Detection .

## Support for Google BigQuery in Workload Planning​ – June 25, 2025

Workload Planning users can now create workload estimates for Google BigQuery service. Select Google BigQuery in the Service Type dropdown, provide your service requirements specific to your workload, and generate different pricing options for BigQuery.

## Cloudability Dashboards Table Totals – June 17, 2025

We have added an extra row for Cloudability dashboards that includes the sum of all visible table rows to all table widgets. This behavior is enabled by default and applies to all tables. For columns containing numbers or currency, the extra row will show a sum of all visible columns. For columns containing percentages, the extra row will reevaluate the percentage calculation for the entire data set.

## Cloud Sustainability Metrics GA – June 16, 2025

We have launched multi-cloud cloud sustainability metrics in Cloudability. Cloudability customers can quickly and easily view these metrics to get insights into their public cloud carbon emissions which had limited access earlier.

The following sustainability metrics can now be accessed from Cloudability reports and dashboards:

- Estimated Carbon Emissions (MTCO2e) – Captures the estimated carbon emissions in metric tons of carbon dioxide equivalents.
- Power Consumed (kWh) – Captures the Power consumed in kilo watt hours.

We have configured a default dashboard within Cloudability to get started under All Dashboards titled Sample Dashboard - Cloud Sustainability .

For using the cloud sustainability metrics, follow the steps below:

1. Navigate to Cloudability Home.
1. Click New Report / Add Widget .
1. Under Cloudability metrics section scroll to the Sustainability category.
1. Select the metrics.

## Adding support for GCP Tags – May 28, 2025

We have launched support for GCP tags within Cloudability.

Earlier, Cloudability supported GCP labels. With this release Cloudability supports both GCP Labels and Tags for visualizing cost throughout Cloudability.

With this release Cloudability will start ingesting GCP Tags fetched along with GCP billing data available to be configured in Cloudability’s Tags and Label page. Once configured they would be treated as another Tag Dimension and can be used like current Tags, labels, or even as part of Business mappings within Cloudability.

GCP Tags are displayed in the below format:

Key = cldy:gcp:tag:<tagkey>

## Containers: Allow "Top 10" widgets to support different limits – May 27, 2025

Users can now choose from a wider range of sorting options when adding a custom top/ bottom widget in the Container Cost Allocation dashboard. In addition to the existing 10, the widget now supports the option of top/ bottom widgets from 25 to up to 50 providing deeper flexibility and visibility into cost-driving resources. This enhancement enables you to tailor the insights to your scale and analysis requirements.

## Enhanced UI/UX in Workload Planning - May 27, 2025

1. Common information section, adding a new workload with a single glass pane view for each CSP
1. The Add Resource slide out, accommodating more input fields when provided specific resource requirements from a CSP
1. Added help info in the UI to guide users navigate through the feature
1. Simplified selection of regions by restricting it to Service Providers section in Common Information only
1. The Resource Type dropdown in Add Resource section with detailed and descriptive information. Such as the resource's full configuration ( g5.12xlarge - 48 CPUs, 192 GB RAM, 3800 GB Local Storage ) instead of just its name ( g5.12xlarge ).

## Cloudability: Enhancement to Sustainability Metrics Calculation and Expanded GPU support for Azure and OCI Compute – May 15, 2025

We have launched a couple of enhancements to Cloud Sustainability Metrics.

We have improved the calculation methodology for sustainability metrics in IBM Cloudability. As a result, customers will notice an increase in metric values going forward. These changes are due to a fix applied to the underlying calculations and will not be applied to historical months.

Additionally, we have also expanded the GPU metric support. While support already existed for AWS and GCP, this release enhances and adds support for Azure and Oracle as well.

## Cloudability Premium : Vendor Credentials Update to ON/ OFF under Automate Actions – May 14, 2025

We have launched updates to the ON/ OFF Status within Automate Actions in the Vendor Credentials page in Cloudability Premium.

- OFF was displayed if Optimization was set as Read Only .
- ON was displayed if Optimization was set as Optimize Resources .

With this release the ON/ OFF will function as follows:

- For AWS and GCP if the Automated credentialing is selected Automate Actions : ON/ OFF will follow the selection based on the parent (AWS Master Payer/ GCP Billing) account If Parent Account is ON , all the child (AWS linked accounts/ GCP projects) accounts would be ON . If Parent Account is OFF , all the child accounts would be OFF . Child accounts cannot be changed Individually when opted for Automated Credentialing.
- For AWS and GCP if the Automated credentialing is not selected Both Parent and child accounts can have different ON/ OFF status under Automate Actions . The ON/ OFF status can be changed individually without any dependency between Parent and Child.
- For Azure the status is only reflected on the subscriptions while credentialing.

## Cloudability Cost Sharing - Allocation Source in ApptioBI – May 13, 2025

Cloudability announces lineage for reporting on shared costs in ApptioBI. We have introduced a new dimension called Allocation Source in ApptioBI, enhancing visibility into shared costs configured in Cost Sharing.

Earlier, users could see only summarized shared costs, which made tracing origins challenging. The new Allocation Source dimension, available within the Cost and Usage (Allocated) projection, provides clarity by identifying the specific sources contributing to shared costs. Users can now easily contextualize shared cost data within their ApptioBI reports.

Key Features

- Trace shared costs back to their original sources clearly
- Improve understanding and transparency of cost sharing for better business insights

Limitations

Allocation Source is not supported for widgets that simultaneously include two or more business dimensions with active cost sharing. Attempting this configuration will result in an error.

Future Enhancements

Integration of Allocation Source into Reports. We are working on Dashboards and it is expected to be available in an upcoming release.

## Cloudability Premium: Vendor Credentials: Adding and reclassifying Turbonomic permissions – May 12, 2025

Today we have launched updates to the permissions required by Cloudability Premium (Cloudability and Turbonomics) to operate seamlessly with each other.

Earlier, a few permissions in AWS, Azure and GCP were either missing or needed to be reclassified in the vendor credential flows during the download of AWS, Azure and GCP scripts. This release has updated these permissions in the scripts for Cloudability Premium Vendor Credentials flows.

## Cloudability : Support for newer versions of IBM Cloud Cost files – April 30, 2025

Today we have launched updates to the ingestion of newer version of IBM Cloud cost files which allows customer to continue viewing the spend on IBM Cloud within Cloudability.

Recently IBM Cloud has upgraded the versions and formats of the cost files, the newer version being:

- Account Summary level CSV – v1.3
- Instance level CSV – v1.4

Earlier, The older version of IBM cloud cost files as supported till date will continue as usual making this change reversible.

There is no change for the credentialing steps or permissions required for IBM cloud. There are no new dimensions or metric additions with this release as well.

## Business Metrics GA – April 22, 2025

We are announcing the official release of Business Metrics with a new management user interface in Cloudability. Previously available only through our API, Business Metrics can now be created and managed directly through the UI, making it easier to create custom metrics for your business needs.

Key Features

- New User Interface: Create and manage Business Metrics directly from the UI in a dedicated tab next to Business Mappings
- Intuitive Metric Creation: Define custom metrics using a user-friendly interface without needing API knowledge
- Custom Statement Builder: Use a handy auto-complete to build formulas (Value Expression) and leverage sophisticated conditional matching (Match Expression)
- Seamless Integration: Use your Business Metrics across Cloudability's reporting features and dashboards

- Contextualize Cloud Spend: Connect cloud costs to business-specific KPIs that matter to your organization
- Unit Economics: Calculate cost per customer, transaction, or user to understand your cloud economics better
- Calculate Savings: Create formulas to calculate types of savings or other measurements

Getting Started

Business Metrics can now be accessed from a tab next to Business Mappings in the UI. You can create up to five Business Metrics per account.

API Support

For users who prefer to manage rules programmatically, our comprehensive API for Business Metrics remains fully supported with documentation available through the Business Mappings End Point. For more information, refer to our documentation portal or contact your Customer Success Manager.

## Cross Region Recommendations in Workload Planning – April 21, 2025

With this release, you can select multiple preferred regions in both Common Information and Resource Type sections in, with the recommendations being shown for the resource in different regions.

Previously, the recommendations in Workload Planning were restricted only to the specific region selected by the user either in Common Information (if the user hasn't defined the exact resource type) or the specific selected region while defining the exact resource type.

## New Standard Role - Cloudability Billing Admin – April 21, 2025

Today, we introduced a new standalone role titled Cloudability Billing admin for assigning billing admin privileges in Cloudability.

Earlier to assign someone with the billing admin permission in an org, an admin was required to create a custom role with the permission named " OrgCurrencyFeatureAccess ". Going ahead, an admin would just need to assign the role called " Cloudability Billing Admin " to provide a user with the billing admin privileges. This would be a standard role available to all customer orgs across all Cloudability SKUs.

## Cost Sharing for Business Metrics – April 4, 2025

Customers can now allocated shared costs across all of their Business Metrics when using Cost Sharing.

Earlier, only supported cost sharing rules across the default cost metrics that supported. With this release, you can allocate across any currency Business Metric (except non-currency Business Metrics) that exists in your environment for more accurate allocation of shared costs in different contexts. This is available for all customers and can be seen in the Explorer page of cost sharing and ApptioBI upon selecting a metric to report on.

## Import and Export of Cost Allocation Rules – April 4, 2025

Today, we introduced import and export functionality for our cost allocation rules. Now, you can upload your cost allocation rules without having to configure them in the user interface or do this programmatically through the API.

We support the import of CSV file types for those customers who want to leverage bulk allocation rule generation. The template of the CSV can be found in the Help Center documentation .

How this feature can help you

For those who want to edit and/or add on to rules, you can now export the list of rules you currently have in a business dimension, which will provide you the list of rules that currently exist in the format needed.

In addition to import/ export for cost allocation rules, we have also released export functionality for the data that lives in the Explorer page, making it easier to export the direct and shared costs for a given set of cost allocation rules.

## Prompt for Outdated Pricing Data in Workload Planning – March 27, 2025

With this release, users will see a notification banner for workloads which are six months or older. Use Regenerate button on the banner to regenerate recommendations for those workloads with up-to-date pricing.

## Improved Navigation for Anomaly Email Notifications - March 26, 2025

Today, we introduced improvements to the Anomaly Email Notification experience, designed to simplify navigation and provide clearer insights for users.

Previously, clicking on the "View Anomaly" link in email notifications redirected users to a general anomaly detection page displaying all anomalies instead of the specific one referenced in the email. Additionally, anomalies sometimes disappeared or showed incorrect details after updated cost files were processed adding to the confusion.

With this release, both challenges are addressed to ensure a smoother and more intuitive anomaly review process.

- Direct Navigation with "View Anomaly" Link: Users are now redirected straight to the specific anomaly mentioned in the email, with its details page open for immediate review.
- Updated Cost Tooltip: If an anomaly's cost changes due to updated cost files, a tooltip will display the revised anomaly cost for better clarity.
- Disappearing Anomaly Notification: If an anomaly disappears after updated cost files are processed, a pop-up message will notify users that the anomaly no longer exists.

## Container Cost Allocation now supports Kubernetes Version 1.32 - March 19, 2025

Container Cost Allocation now supports Kubernetes Version 1.32 - March 19, 2025Today, we announce the support of Container Cost Allocation on Kubernetes version 1.32 across all providers. This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.32.

Container Cost Allocation now supports Kubernetes Version 1.32 - March 19, 2025Today, we announce the support of Container Cost Allocation on Kubernetes version 1.32 across all providers. This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.32.

## Validations on Shared View Access - March 18, 2025

In this release, we added an additional validation when Views Authors want to reduce the permissions of Shared View to Private or want to remove users’ access.

Earlier, Cloudability allowed View Authors to change the permission of shared views to Private or remove users from View access without any restrictions. As a result, the users who had previously set Shared View as Default View continued to receive alerts for that View even after the permissions were changed to Private or they were removed from the access. This occurred only when Shared View was set as Default View .

Going forward, before the View authors reduce the permission of a Shared View , they will be presented with list of users who have set the Shared View as Default View . Otherwise, the View Author would be able to change the view permission to 'Private' or able to remove user from View access without any restriction.

Change Default View to Organization's Default View for Impacted Users:

Since Cloudability allowed this earlier, users who still have Private Views as Default View continue to receive email alerts. We will fix the Default View for those users from the backend and set their Default View to the organization's Default View. This will ensure that the users will not have a "missing" or inaccessible Default View .

Additionally, impacted users can log in to Cloudability and change their Default View from the organization's Default View to another View they have access to. To set your default view:

1. Click your Profile icon and select Manage Profile
1. From your Profile page, select Preferences tab
1. Select a view from the Default Account View

## Bulk Import via Excel File for Workload Planning - March 6, 2025

Currently, Workload Planning provides support for bulk import using JSON file. With this release, will support excel file import, making it easy for excel users. Like JSON bulk import feature, you can first download the excel template and then input all your resource information as per the instructions provided in the template file. Uploading this excel file back would create all the resources as per the information provided.

## AWS and Azure Commitment Recommendations Enhanced for Accessibility - March 4, 2025

Today, Commitments released accessible AWS and Azure commitment recommendations pages. The release, while primarily aesthetic, moves the header options from the drawer to a simple menu dropdown.

## Enhanced Filtering on Anomaly Detection Page - February 26, 2025

Today, we introduced new filtering capabilities to the Anomaly Detection feature, making it easier to monitor, analyze, and act on cost abnormalities efficiently.

Anomaly detection enables organizations to identify unusual or unexpected behavior in their cost spending. It provides a cloud-agnostic, comprehensive analysis across all services to detect anomalies in cost data, helping mitigate sudden billing shocks by sending alerts and enabling users to take action.

Previously, you could only filter by Views or sort columns. Now, you can instantly narrow down results to the relevant services or accounts, and filter anomalies based on specific cost thresholds to focus on the most significant issues.

These new filters will provide:

- Expanded filtering: Filter anomalies by Account Name, Service, Usage Family, Total Cost, and Unusual Spend for a more granular view
- Threshold-based filtering: Set specific thresholds for Cost and Unusual Spend to quickly identify high-impact anomalies
- Multi-filter support: Combine multiple filters to refine results and analyze cost variations with precision

## Resource Inventory Column Support for Account Groups - February 21, 2025

With this release, resource inventory users can add account groups as a column in the UI for their inventory reports. This additional detail can be helpful when analyzing resources and categorizing them in ways relevant to the business.

## Threshold-Based Alerting - Container Insights UI - February 17, 2025

This release introduces threshold-based alerting capability in Container Insights UI, enabling enterprises to proactively monitor and manage container costs across their Kubernetes environment. This feature addresses the challenge of manually monitoring spending changes across multitude of clusters and namespaces, making it easier for organizations to maintain control over their container costs.

- Eliminate manual monitoring with automated alerts for cost and utilization thresholds
- Save time by receiving immediate notifications when metrics exceed defined limits
- Enhance cost control across large scale container deployments
- Enable proactive cost optimization with timely notifications
- Improve visibility into container spending trends

This new alerting capability streamlines container cost management by providing automated monitoring and notification systems, helping organizations maintain better control over their container spending without the need for constant manual oversight.

Here are the feature details:

- Set and manage custom thresholds for cost and utilization metrics directly from Container Insights 2.0 Dashboard widgets
- Configure email notifications for threshold breaches, with support for up to 100 alerts per organization
- Simple alert management where all users can configure alerts for themselves, while users with Cloudability Admin privilege can also assign alerts to other users
- Email notification support, with plans to expand to PagerDuty notification channels in the future

![threshold based alerts screenshot](../images/threshold-based_alerting4.jpg)

For detailed instructions on configuring alerts and understanding the alert management interface, refer to Container Insights: Threshold-based Alerting Configuration Guide .

## Auto Populate Vendor and Region for Storage while creating a Virtual Machine resource in Workload Planning - February 14, 2025

Today, we released an enhancement to Auto Populate Vendor and Region for Storage (and make them non editable) while creating a Virtual Machine resource in Workload Planning.

Earlier, while adding a Virtual Machine resource, both Vendor and Region options used to appear for the attached Storage resource. This is not logical because the Vendor and Region for the attached Storage should be the same as the Virtual Machine. With this release we will Auto Populate Vendor and Region for Storage (and make them non editable) while creating a Virtual Machine resource in Workload Planning

## Dynamic Data Transfer Cost for Container Cost Insights - February 10, 2025

Today, we released an enhancement to Container Cost allocation which includes dynamic data transfer costs in its allocation methodology.

How this feature can help you

With this release, Container Insights and the analytics tool will dynamically allocate accurate data transfer costs for cloud vendors that provide separated billing line items for data transfer.

Specifically, we will:

- Evaluate each cloud provider's billing data.
- Allocate network costs for vendors who support data transfer billing line items (EKS, AKS, GKE).
- Distribute network costs to individual Kubernetes cost groupings (Cluster, Namespace, Workloads, Containers, etc.).

This means we will no longer use the default 5% allocation of the cost of instances to network.

For vendors that do not provide separate billing line items for data transfer, we will continue to allocate 5% of the cost of instances to networking. This is due to the lack of specific network billing data tied to instance IDs, making it impossible to accurately allocate costs to the correct nodes or pods.

This enhancement will apply the new logic from the date of release. For customers who require historical data to reflect this change, connect with your account team or support. We will accommodate requests to backfill historical data up to February 1, 2025, to align with the new allocation methodology.

## Enhanced Container Insights with GCP Resource-Level Billing - February 10, 2025

Today, we announced the enhancement of our Container Insights feature to support GCP resource-level billing within Cloudability. This update marks a significant step forward in providing more granular cost visibility for our GCP customers.

Its key benefits are:

As part of this release, we are introducing a new column on the Container Insights page called the Miscellaneous Cost column. This column will reflect cluster-specific costs and will initially be available for GCP, with plans to expand support to other cloud service providers (CSPs) in the near future. These costs encompass additional expenses associated with containerized applications that extend beyond nodes, volumes, and data transfer. They include various services and resources necessary for cluster operations, providing a comprehensive view of all costs related to running containerized applications.

We do not plan to support GCP’s native GKE Cost Allocation at this moment, considering our advanced capabilities.

## Automating GCP SKU Updates and Enhanced Classification Within Reporting Dimensions - February 3, 2025

Today, we launched an update where we transitioned the process of updating the GCP SKU list from manual to automated. GCP updates the SKU list regularly and this enhancement automates the fetching of the latest SKU list in Cloudability which improves SKU classification.

Before this release, we were updating the GCP SKU list manually. This enhancement eliminates the potential for human error, significantly reducing SKU update cadence and ensuring data accuracy and consistency for GCP reporting.

Now, GCP customers can view the latest values across various dimensions in reporting while using GCP as a vendor.

With this release, we’ll also trigger a data reprocess process for all GCP customers so that their SKUs reflect the latest updates.

With this release and running the reprocess, the overall cost for a GCP customer would remain the same. However, there could be reclassification of some values within the dimensions/ reporting which might affect reports or forecasts if there are filters applied on reports.

## Cost Sharing Availability in Cloudability - January 30, 2025

Today, we announce the release of Cost Sharing, a powerful new feature that brings automated, granular cost allocation capabilities to your cloud financial management workflow.

Key Features

Flexible Allocation Rules

- Configure multiple allocation strategies including even split, fixed weighting, proportional distribution, and telemetry-based allocation
- Apply multiple allocation rules within the same business dimension
- Share costs across teams, departments, business units, and other dimensions

Enhanced Cost Visibility

- New Explorer interface provides visual confirmation of allocation rules
- Track both direct and shared costs through dedicated reporting
- Access post-allocated values directly in cost analytics
- Visualize cost distribution patterns across your organization

- New Cloudability Cost and Usage(Allocated) projection in Apptio BI
- Integrated view filtering respects organizational hierarchies
- Support for showback and chargeback reporting
- Visualize cost distribution patterns across your organization

Automate the Last Mile : Finally close the gap on unallocated spend by automatically distributing shared infrastructure costs

Reduce Manual Effort : Replace error-prone spreadsheets with automated, rule-based allocation

Improve Accuracy : Create consistent, repeatable allocation rules that scale with your organization

Enable Accountability : Give teams visibility into their complete cost profile, including shared resources

Getting Started

The Cost Sharing feature is now available to all customers. Follow the steps below:

1. Navigate to the Cost Sharing tab in the Organize section for Cloudability.
1. Create your first allocation rule using our guided setup.
1. Use the Explorer to visualize your allocations.
1. Generate reports using the new Allocated projection.
1. For detailed documentation and best practices, visit our Help Center.

## Workload Planning – Resource Requirements Import - January 24, 2025

Today, we introduced Workload Planning – Resource Requirements Import. This feature enables you to upload multiple resources and requirements through a JSON file for a given workload. With this, you can download a JSON template or the list of the existing resources and import them to help you enter and update requirements efficiently.

How this feature can help you

Previously, Workload Planning users could only add resources to their workloads manually, which slowed the workload creation process. With this new functionality, users can now upload multiple requirements at once and leverage Workload Planning API, which should be shared soon in Help Center.

While Cloudability currently supports JSON format for this functionality, we plan to support additional formats in the future based on the customer feedback.

To import resources, follow the steps below.

1. Create a workload.
1. Select Add Resources .
1. Select Import to download a template, or the list of the existing resources in JSON format.
1. Upload the JSON file after making the necessary changes. The imported file will overwrite the current workload resources.

If the import is successful, your resources will be updated. In case of error(s), an error report will be available for download. You will need to update your file based on the report before importing resources again.

Once the resources are uploaded, you can view your recommendations and workload summary in the next step.

## Ability to Add Custom Namespace While Credentialing OCI - January 20, 2025

Today, we launched updates to OCI vendor credentials which allow customers to add a custom namespace while credentialing OCI in Cloudability. Previously it used to be defaulted to the Oracle suggested namespace as ‘Bling’. This update is applicable for both new and existing customers using OCI on Cloudability.

Steps for adding the custom namespace in OCI for new customers

1. In Cloudability , navigate to Settings > Vendor Credentials .
1. Select Add Datasource button > OCI .
1. The new custom namespace field is enabled to fill in.
1. Complete the steps as mentioned in Connect Oracle Cloud .

Steps for adding the custom namespace in OCI for existing customers

1. In Cloudability , navigate to Settings > Vendor Credentials .
1. Select the existing datasource > OCI .
1. Select the credential entry you want to edit and click Edit .
1. The new custom namespace field is enabled to update.
1. Update the field as required and complete the other steps as mentioned in Connect Oracle Cloud .

## ATUM Mapping Dimensions - January 17, 2025

Today, Cloudability launched five ATUM dimensions in Reporting. These dimensions extend the TBM Taxonomy into Cloudability , enabling customers to understand cloud spend through this standardized categorization.

Five new ATUM dimensions launched are:

1. ATUM Tower : Represents a high-level IT view of your organization’s technology functions, providing a broad cost categorization. Examples values include Network, Platform, End User and Application.
1. ATUM Sub-Tower : Offers a more detailed categorization under each tower, for example breaking Platform down into Middleware and Database.
1. ATUM Service Type : Represents a high-level business view of your cloud spend. This is the top-level categorization into services with values such as Platform Services, Delivery Services and End User Services.
1. ATUM Service Category : Offers a more detailed categorization under each service type, for example breaking Delivery Services down into Operations, Security and Compliance, and Support.
1. ATUM Service Name : This is the most detailed categorization related to services, for example breaking the Operations service category down into Event Management, IT Service Management, and Deployment and Administration.

The new ATUM dimensions, aligned with the TBM taxonomy, provide more detailed cost categorization, allowing organizations to understand their technology spending at multiple levels of granularity.

These dimensions are seamlessly integrated into Cloudability Reporting and dashboards for all customers.

## Workload Planning – Azure Savings Plan Support – January 7, 2025

Today, we are providing Workload Planning users with cost estimates for Azure compute resources with the Savings Plan commitment option.

Earlier, Workload Planning only supported Azure Reservations as the default commitment type for new workloads. There is now an option to select Azure Savings Plan or Azure Reservations with one-year or three-year term and get cost estimates based on their associated savings.
