---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cloudability : What's new in 2023"
breadcrumb:
  - "What's new in Cloudability"
  - "Cloudability : What's new in 2023"
source_path: "SSVCLNQ/release-notes/whats-new-2023.html"
images:
  - "03-media/apptio-cloudability-standard/automated_credential.jpg"
  - "03-media/apptio-cloudability-standard/container-metrics-openshift_1.jpg"
  - "03-media/apptio-cloudability-standard/kubernetes_1.28_versions.jpg"
  - "03-media/apptio-cloudability-standard/oci2.jpg"
  - "03-media/apptio-cloudability-standard/rn-rightsizing-oci-vms.jpg"
  - "03-media/apptio-cloudability-standard/release_notes_screeenshot.jpg"
  - "03-media/apptio-cloudability-standard/anomaly_detection_threshold_new.jpg"
  - "03-media/apptio-cloudability-standard/cldy-res-inv-sorting.jpg"
  - "03-media/apptio-cloudability-standard/oci_rn.jpg"
  - "03-media/apptio-cloudability-standard/cost_visibility_usage_metrics_2.jpg"
  - "03-media/apptio-cloudability-standard/cldy-bi-8.jpg"
  - "03-media/apptio-cloudability-standard/gpu_support_container_insights.jpg"
  - "03-media/apptio-cloudability-standard/mig-help-image-2.jpg"
  - "03-media/apptio-cloudability-standard/ebs-new.jpg"
  - "03-media/apptio-cloudability-standard/kubernetes.jpg"
  - "03-media/apptio-cloudability-standard/rosa1.jpg"
  - "03-media/apptio-cloudability-standard/cldy-idle-cost.jpg"
  - "03-media/apptio-cloudability-standard/cost-management.jpg"
  - "03-media/apptio-cloudability-standard/greentick.jpg"
  - "03-media/apptio-cloudability-standard/azure-enabled.jpg"
  - "03-media/apptio-cloudability-standard/azure-not-enabked.jpg"
  - "03-media/apptio-cloudability-standard/kubernetes-label.jpg"
  - "03-media/apptio-cloudability-standard/usagefamilyremapping.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cloudability : What's new in 2023

## Resource Inventory Support for Views Created with Account Groups - December 28, 2023

With this release, AWS and Azure Resource Inventory would support Views that are created using Account Groups in Cloudability. You can now filter the Resource Inventory data based on the Views that are created using any combination of Tag Dimensions , Account Groups , and Vendor filters.

How this feature can help you

Previously, Resource Inventory would show a "Restricted view" page if you switch to a View that is created using Account Groups .

## Enhanced Logic for Azure Compute in Resource Inventory - December 28, 2023

This release enhances our existing logic to display the Azure Compute resources in Azure Resource Inventory in Cloudability. As a result, you can expect to see a reduction in the number of resources under Compute service and an increase in the number of resources under the Managed Disk services in Azure Resource Inventory.

How this feature can help you

Previously, our logic to display resources under the Compute service factored for snapshot resources and this resulted in a higher resource count being shown than expected for your Azure compute resources. Our new logic is such that the snapshots will be accounted in the Managed Disk service instead of the Compute service. This way, you can expect to see a reduction in the number of resources under Compute service and an increase in the number of resources under the Managed Disk services in Azure Resource Inventory.

## GCP Detailed Billing - December 20, 2023

GCP had introduced detailed billing across many services which enables you to view granular cost data at a resource level as compared to standard billing which used to provide the cost data at SKU level.

More information about the release

To set up GCP Detailed billing, you will need to:

1. Select “ Settings ” menu item from the Cloudability primary navigation menu and then from the expanded sub-menu select “ Vendor Credential s”.
1. On the Credentials page, select the navigation tab for GCP to start the process of adding GCP credentials into Cloudability.
1. Select GCP Detailed Billing option from the drop down list.
1. Add the GCP detailed billing table id .
1. Indicate the GCP GCS bucket .
1. Add the GCP detailed billing date (start year and month).
1. Download the template, run in GCP console.
1. Once completed click on Verify Credentials . A green tick indicates that the credentialing is successful.

GCP resource level costs will be available in Cloudability under Reports and Dashboards by selecting the resource id column.

## AWS Automated Credentialing of Linked Accounts - December 19, 2023

With this release, you can quickly credential your AWS-linked accounts. Cloudability now leverages AWS organizations which allows you to group the linked accounts under the organizations, and execute the cloud formation template (CFT) at an organization level. This reduces the number of executions of the AWS CFT.

How to enable automated credentialing

1. Add your linked accounts under AWS organization in the AWS console.
1. On Cloudability , while credentialing the AWS Master Payer accounts, enable the Automated credentialing of linked accounts checkbox.
1. 
1. Generate the CFT template which should be executed in the AWS console.
1. Add credential for any of your linked accounts under the AWS organization, then save and download the template, and execute for the selected linked account in the AWS console.
1. On individual linked accounts, select Edit > Download > Verify credentials to complete the credentialing of the linked accounts.

## GCP Automated Credentialing of GCP Projects- December 19, 2023

This release enables you to quickly credential the GCP projects within Cloudability.

How this feature can help you

Cloudability now enables GCP organizations to group your GCP projects and execute the shell script at an organizational level reducing the number of executions of the script. Earlier it was required to download the shell script and execute it individually on every GCP project for your organization.

## Introducing Cloudability in EU Region - December 19, 2023

How this feature can help you

This release addresses the unique needs of our EU-based clients, ensuring their data remains within the EU boundaries. By localizing our services, we aim to empower organizations to bolster their compliance efforts and align with the regulations regarding cloud cost management data.

More information about the release

The launch of hosting Cloudability in the EU region holds great significance for our customers operating within this region. It provides a reliable and compliant cloud cost management solution that prioritizes data residency, enhances data privacy, and aligns with data protection regulations.

No additional setup or installation is required for customers who are directly onboarding to Cloudability in the EU. The plan to migrate existing customers will be shared early next year.

## Indicating AWS Region for AWS Service Control Policy - December 19, 2023

As an AWS user, this release allows you to indicate the AWS Service control policy region while credentialing your AWS accounts in Cloudability. It enables Cloudability to go and check the permissions on the mentioned region.

How this feature can help you

Earlier we were checking for permissions for AWS accounts only in the us-east-1 region. If SCP was enabled on your end for a specific region (other than us-east-1), you would receive an " Access Denied " error while going for a verification check for your AWS accounts. This release has handled the above situation and enables Cloudability to check the permissions on the mentioned region.

## Support for AWS Account Tags and Azure Subscription Tags - December 18, 2023

With this release, customers can now retrieve their AWS account-level and Azure subscription tags from their cloud accounts into Cloudability. This feature will help customers create tag dimensions for better cost allocation, and chargeback along with tracking their cloud spend.

More information about this release

For easy identification of account-level tags, we have appended the below-mentioned prefixes for account tags in AWS and Azure respectively:

Prefix for AWS: cldy:aws:accountleveltag:

Prefix for Azure: cldy:azure:subscriptionleveltag:

The account tags will appear while creating a tag dimension in the Organize > Tags & Labels screen.

- or the existing AWS customers in Cloudability , a new permission named Organizations: ListTagsForResource will be granted to the Cloudability IAM role that is added in their AWS cloud. This permission is required to get account-level tags from the AWS Organizations.
- For new AWS customers, the above-mentioned permission will be added to Cloudability credentialing template, so no configuration changes are required.
- For the existing and new Azure customers in Cloudability, no configurational changes are required, and the subscription-level tags will start appearing in Organize > Tags & Labels module.

## Cloudability Container Metrics Agent Supporting OpenShift Versions 4.13, 4.14 - December 14, 2023

How this feature can help you

This feature enables detailed insights for the container resource utilization and the associated costs for clusters using the ROSA variant operating on these versions of OpenShift.

You can now easily download and deploy our metrics agent via the standard provisioning workflow.

## Rightsizing ROI - ServiceNow Integration - December 13, 2023

How this feature can help you

This functionality provides the ability to generate ServiceNow request and /or incident tickets containing rightsizing recommendations automatically within your very own ServiceNow instance. This feature closely resembles the current Rightsizing ROI functionality that can integrate with the Jira Cloud.

By integrating Cloudability and ServiceNow, you can now collaborate quickly and efficiently around cloud resources and rightsizing recommendations. This automated ticketing system augments a more efficient rightsizing cadence to promote cloud optimization through normal service processes. You will also have easier accessibility to the records of the details of the recommendations within Cloudability as well as your ServiceNow platform along with actions (if any) taken on the recommendations. You can now automatically calculate and display the realized savings from resulting actions via the Rightsizing ROI page in Cloudability.

More information about the release

You can start by entering your ServiceNow vendor credentials by going to the Cloudability primary navigation menu and navigating to Settings > Vendor Credentials > ServiceNow . You can then set up a Rightsizing ROI policy by navigating to Settings > Rightsizing Policies and defining a policy to start automatically capturing rightsizing recommendations based on the criteria you have defined. This ROI policy criteria is then used to determine which rightsizing recommendations will automatically have tickets created within your ServiceNow instance.

Alternatively, rightsizing recommendations can be captured manually by navigating to the Rightsizing page under Optimize > Rightsizing and manually creating a ServiceNow request (or incident) for an individual recommendation from the menu at the right side of the recommendations table. To view the captured Rightsizing recommendations in Cloudability , navigate to Optimize > Rightsizing ROI .

## Cloudability Rightsizing - Page Level Filtering Options - December 12, 2023

How this feature can help you

This functionality is the first step towards providing Rightsizing filtering options at page-level that filter both the top recommendations as well the additional recommendation options provided in the details pane. There are new 2 options as part of this release:

1. The " Top Multi-Architecture " option which is available on Compute Rightsizing pages. This option filters the details pane recommendation options by showing at least 1 rightsizing recommendations for each CPU architecture - If there are cost savings available for the CPU architecture. The recommendations in the details pane still display in order of greatest cost savings.
1. The " Count Reduction Only " option available on Compute Group Rightsizing pages (currently ASG, MIG). This option filters all recommendations by showing the ones only which reduce the number of instances in the group.

More information about the release

This release benefits by providing you more options for which rightsizing recommendations can be filtered in order to meet your use cases and enhance usability. Additionally, having page-level filtering options that can filter both the top recommendations provided on the page as well as the additional recommendation options provided in the details pane allows more comprehensive filtering possibilities when you require this level of granularity to take appropriate cost saving actions.

From the Cloudability primary navigation menu, under the Optimize menu item select the option for Rightsizing . The " Top Multi-Architecture " option is available on the Compute Rightsizing page for each vendor (for example, AWS’s compute rightsizing page is EC2). The " Count Reduction Only " option is available on the Compute Group Rightsizing page for each vendor (for example, AWS’s compute group rightsizing page is EC2 ASG). Both options will be located near the top of their respective pages next to the current “Filters” that are already provided.

The " Top Multi-Architecture " option will require the “ Allow cross-architecture recommendations ” setting to be globally enabled on the Rightsizing Preferences page located under the Settings menu item as a prerequisite. Changes to these global preferences can take up to 24 hours to take effect.

## Cloudability Mixed Instance Type Recommendations in Rightsizing for AWS ASGs - December 7, 2023

This release provides new Cloudability rightsizing recommendations for mixed instance type for AWS EC2 Auto Scaling Groups (ASGs).

How this feature can help you

Cloudability Rightsizing now provides recommendations for mixed instance type AWS EC2 ASGs. Rightsizing recommendations were previously available only for single instance type ASGs. Like single instance type ASG recommendations, these new recommendations provide cost saving actions to implement on the group itself, which will then automatically apply to resources created by that group.

More information about the release

With added support for rightsizing recommendations for mixed instance type ASGs, you will now have access to additional recommendations for AWS Auto Scaling Groups for cost saving opportunities by identifying resources that can be resized to better match their underlying workloads.

## Cloudability Enhancement: Service Name Mapping Update for AWS Elastic Container Registry - November 22, 2023

This release fixes a bug to ensure that the AWS Elastic Container Registry is correctly mapped to the appropriate service name. With this update, AWS Elastic Container Registry will now be accurately mapped to AWS ECR. This change takes effect today.

If you need this update to be applied to your historical data, reach out to our support team or your account representative to request a reprocess.

## Container Cost Allocation now Supports Kubernetes 1.28 Versions - November 21, 2023

This release announces Container Cost Allocation support for Kubernetes version 1.28 across all providers. This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.28.

Customers can now easily download and deploy our metrics agent via the standard provisioning workflow.

## Oracle Container Engine for Kubernetes: Cost Management and Optimization - November 20, 2023

Users can now seamlessly map and manage all their Kubernetes (K8s) clusters across OCI, AWS, Azure, and GCP, as we are extending support to OKE.

- Container Cost Allocation: Explore and visualize costs for all OKE clusters, categorized by Namespaces and Labels.
- Enhanced Reporting: Cluster Name, Namespace, and Label dimensions are available in core reporting, including reports, dashboards, and TrueCost Explorer.
- Business Mapping & Views: Allocate and categorize containerized costs in tandem with regular cloud costs.
- Rightsizing Recommendations: Optimize resource utilization and cost efficiency by receiving recommendations to align request and limit values with the actual workload requirements, reducing waste and expenses.

For GPU instances, the primary cost factor is GPU and OCI doesn't provide any cost per CPU and Memory. Therefore, we are allocating container costs at GPU level for GPU clusters but there is 0 cost allocation for CPU and Memory.

## Cost Management and Optimization for Oracle Kubernetes Engine - November 20, 2023

This release introduces official Cloudability support for Oracle Kubernetes Engine (OKE). This release achieves feature parity for OCI, empowering users to granularly allocate costs by Namespaces and Labels, facilitating precise cost tracking so that they can be charged back to the business.

Users can now seamlessly map and manage all their Kubernetes (K8s) clusters across OCI, AWS, Azure, and GCP, as we are extending support to OKE.

Key highlights of this release include:

- Container Cost Allocation: Explore and visualize costs for all OKE clusters, categorized by Namespaces and Labels.
- Enhanced Reporting: Cluster Name, Namespace, and Label dimensions are available in core reporting, including reports, dashboards, and TrueCost Explorer.
- Business Mapping & Views: Allocate and categorize containerized costs in tandem with regular cloud costs.
- Rightsizing Recommendations: Optimize resource utilization and cost efficiency by receiving recommendations to align request and limit values with the actual workload requirements, reducing waste and expenses.

For GPU instances, the primary cost factor is GPU and OCI doesn't provide any cost per CPU and Memory. Therefore, we are allocating container costs at GPU level for GPU clusters but there is 0 cost allocation for CPU and Memory.

## Rightsizing Recommendations for OCI Virtual Machines - November 20, 2023

This release supports Cloudability Rightsizing for Oracle Virtual Machines (VMs). This new feature brings attention to over-provisioned and idle resources to provide cost saving opportunities, identifying OCI resources that can be resized to better match customers' underlying workloads and allowing them to track actions in Rightsizing ROI.

![rightsizing recommendations sceenshot ](../images/rn-rightsizing-oci-vms.jpg)

How this feature can help you

- Receiving actionable recommendations for several types of Virtual Machines: Legacy, flex, burstable, bare metal and instance pools.
- Receiving detailed cost savings analysis factoring in CPU, Network, Memory for both 10-day and 30-day time lines.
- Visualizing possible savings across OCI, AWS, Azure, GCP Cloud usage in Rightsizing Explorer.

More information about the release

To receive these recommendations, you need to go through the advanced credentialing process for your child tenancies so that Cloudability can pull the utilization data required for rightsizing. Once the advanced credentials are verified, it may take up to 48 hours for recommendations to appear in Cloudability. The recommendations will be shown on the Rightsizing page under the new “ OCI ” vendor tab.

## Azure Resource Inventory Reporting - November 15, 2023

How this feature can help you

As an Azure user, you have the flexibility to build this list from resources spanning multiple accounts and choose from different measures (dimensions and metrics) to surface the details relevant to them. This information available for each cloud resource unifies billing, utilization and descriptive meta data to provide you with a more comprehensive inventory view.

Azure Resource Inventory reporting feature must be explicitly enabled for your Cloudability Org. You must reach out to your TAM/CSM/account point of contact from Apptio to get this done. By default, only Admin or Cloudability Admin roles will be able to access this feature. However, inventory access can also be granted to any custom role by assigning the custom role with AWSResourceInventoryFullAccess permissions.

More information about the release

You can view month-to-date inventory data for each service. Upon enabling this feature, resource inventory data will be back filled to the beginning of the current month. Over time, inventory data will be available on a three-month rolling window. That is at any point in time, you will be able to access resource inventory data for the current month along with the previous two months. You have the option to export the reports in CSV format. These exports include all the columns supported for the particular service (i.e., there is no 20 column limit).

## Self-service Data Reprocess (Beta) - November 15, 2023

How this feature can help you

Typically, when you modify your business strategy, there is a need to adjust Business Mappings, Account Groups, and Tags & Labels in Cloudability with a retrospective refresh of historical data. This is where a data reprocess comes into the picture. If you are a Cloudability customer you might only need reprocessing within Cloudability , however if you use Costing & Planning as well, your actions involve exporting data to Costing & Planning too.

The existing daily reprocess job is mostly focused on reprocessing the current month data. To reprocess the historical data, the current process requires you need to raise a support ticket. This manual process is both support dependent and time-consuming, and is something we are looking at eliminating with this release.

The feature is not enabled by default as needs to be explicitly enabled before you can see the feature in Cloudability. Reach out to your TAM/CSM to get this enabled.

More information about the release

The feature can be accessed by navigating to Organize > Data Reprocess in Cloudability or Cloud Data Ingestion (CDI).

The feature has the following limitations in terms of the number of requests that can be submitted in a month.

- Only Cloudability users with an "Admin" role and Cloud Data Ingestion (CDI) users with a "Cloud Data Ingestion" role will be able to access the feature.
- Customers will have a pre-defined number of Month-units/month.
- Customers will have a pre-defined lookback period of 12 months.
- Two reprocess requests cannot be submitted at the same time, if they have overlapping periods.

If you use only Cloudability : This is a two-step process where you can select the Period and submit the job. You can also monitor the status of the job in the Job Status tab. For detailed steps, refer to Data Reprocess for Cloudability users .

## Out-of-the-box Apptio BI Reports for Cloudability TotalCost - November 9, 2023

New Apptio BI Reports

This release includes the following new out-of-the-box Apptio BI Reports. These reports leverage data from the Cloudability TotalCost data source. You can find these reports on the Reports page.

Cost Visibility

| Description | This Apptio BI report provides visibility of spend data across your main cloud data sources, specifically AWS, Azure, GCP, and OCI, where applicable. |
| --- | --- |
| Use cases | This report solves the following use cases: Understand the total cost of the main cloud services within your organization. Specific insight into spend across cloud services across all main cloud providers. |
| Personas | This report is primarily aimed for use by the Cloud Center of Excellence and FinOps practitioners, as well as engineers who want full visibility into their organizations’ spend. |
| Questions answered | The report answers the following questions: What is my AWS, Azure, GCP, and OCI spend, where applicable? What am I spending on the main services (For example: AWS S3) the cloud vendors provide? |

TotalCost Spend - Invoice View

| Description | This Apptio BI report provides visibility of invoice cloud costs before being allocated to consumers. This report will showcase what spend is direct, shared, and how you are trending to your budget across all cloud providers. |
| --- | --- |
| Use cases | This report solves the following use cases: Understand your cloud spend before it has been allocated across your organization to consuming entities. Analyze spend by direct and shared costs. Track budget variance of your cloud spend. |
| Personas | This report is primarily aimed for use by the Cloud Center of Excellence and FinOps practitioners, as well as engineers who want full visibility into their organizations’ spend. |
| Questions answered | The report answers the following questions: What am I spending on monthly basis across my cloud vendors? How am I tracking relative to plan across my cloud spend? What is my budget variance? How much of my spend is direct vs shared costs? |

TotalCost Spend - Consumer View

| Description | This Apptio BI report provides visibility of how cloud data has been allocated across your organization to consuming entities (For example: Business Units, Products, etc.). |
| --- | --- |
| Use cases | This report solves the following use cases: Visualize your shared costs across products, services, and vendors. Understand immaterial spend that has been captured and categorized by Cloudability TotalCost. |
| Personas | This report is primarily aimed for use by the Cloud Center of Excellence and FinOps practitioners, as well as engineers who want full visibility into their organizations’ spend. |
| Questions answered | The report answers the following questions: What are the top five services that consume the most spend? How has my cost per vendor trended over the past year? What are the top drivers of shared costs? |

## Support for more Datadog regions - October 20, 2023

New regions supported

The following are the newly supported Datadog regions:

- ap1.datadoghq.com
- us3.datadoghq.com
- us5.datadoghq.com

Support for the existing Datadog regions remains intact, and Cloudability users using these do not require any updates at their ends.

- datadoghq.com
- datadoghq.eu

The process of credentialing Datadog into Cloudability remains the same, with the only addition being be the new regions which you can choose from the dropdown list. For more information on connecting Datadog in Cloudability , see Connect Datadog to Cloudability .

## Cloudability Reservation Portfolio and RI Planner support for Azure Cache for Redis and Synapse Analytics - October 19, 2023

How this feature can help you

Azure Cache for Redis and Synapse Analytics customers optimizing their spend through reservations (both Redis and Synapse Analytics), and pre-purchase plans (Synapse Analytics) can now view and manage their reservations in the Reservation Portfolio. Cloudability expands the services that Reservation Portfolio supports on the Azure Cloud in response to the growing number of customers who utilize Azure. By incorporating Azure Redis and Synapse Analytics, Cloudability provides these customers with additional benefits in terms of realizing the value of purchasing reservations on the Azure Cloud.

More information about the release

Reservations for Azure Cache for Redis and Synapse Analytics dedicated to SQL pools function similarly to Azure Compute, SQL, and Cosmos DB reservations. They are maintained regularly, and are billed hourly.

Pre-purchase plans for Azure Synapse Analytics function similarly to Databricks. These reservations are interchangeable credits that can be used across the duration of the reservation. Unlike most of the reservations, they are not maintained regularly. Our KPIs and table headers have been adjusted to properly reflect the information around the pre-purchase plan credits, and SCUs. Similar to Databricks, we've added a third chart to the details panel to help understand the burn-down on a given commitment.

Support for the Reserved Instance Planner for Azure Synapse Analytics pre-purchase plans is not available at this time.

If not already completed, you need to ensure that the necessary Azure credentials, and permissions have been enabled to provide Cloudability with access to your data.

MCA customers: Configure the billing account reader by role following the instructions here .

## Utilization Reporting enhancements for AWS EBS and GPU - October 18, 2023

These newly introduced metrics are as follows:

- Burst Balance - Provides information about the percentage of I/O credits (for gp2) or throughput credits (for st1 and sc1) remaining in the burst bucket. Used with General Purpose SSD (gp2), Throughput Optimized HDD (st1), and Cold HDD (sc1) volumes only.
- Volume Consumed Read Write Ops - The total amount of read and write operations (normalized to 256K capacity units) consumed in a specified period of time. Used with Provisioned IOPS SSD volumes only.
- Volume Throughput Percentage - The percentage of I/O operations per second (IOPS) delivered of the total IOPS provisioned for an Amazon EBS volume. Used with Provisioned IOPS SSD volumes only. This metric is not supported with Multi-Attach enabled volumes
- GPU Utilization - Percentage of time over a sample period where one or more kernels on the GPU was running.
- GPU Memory Utilization - Percentage of time over a sample period where memory was being written or read. For successful results with GPU metrics, make sure you have configured minimal GPU metrics as a prerequisite.

How this feature can help you

This release enhances the support for AWS utilization metrics in Cloudability and enables customers to get insights into AWS EBS and GPU utilization metrics.

## Support for Turbonomic integration with Cloudability - October 17, 2023

How this feature can help you

For current (and future) customers of both Cloudability and Turbonomic , there is optimization-related functionality & data that exist in one product but not the other. Previously there was no Out-of-the-Box integration between Cloudability and Turbonomic and therefore customers of both products would need to go to each product separately in order to utilize the functionality contained in each one. This feature will initiate the process of enhancing Cloudability allowing customers of both products to have additional Turbonomic functionality & data displayed directly in Cloudability itself.

More information about the release

In order to set up Turbonomic credentialling, select “ Settings ” menu item from the Cloudability primary navigation menu and then from the expanded sub-menu select “ Vendor Credentials ”. On the Credentials page, select the navigation tab for Turbonomic to start the process of hooking Turbonomic account credentials into Cloudability. Once the Cloudability/Turbonomic integration is set up, navigate to the new Turbonomic page by selecting " Optimize " menu item from the Cloudability primary navigation menu item and then from the expanded sub-menu select “ Turbonomic ”. The new functionality & data will be displayed starting with the Necessary Investments & Potential Savings Cloud charts and accompanying values from Turbonomic .

## Expanding Support for Cloudability Cost (List) metric to all Azure services - October 13, 2023

This release introduces a significant enhancement to Cloudability with a more comprehensive and consistent cost metric for cloud expenditures.

Our "Cost (List)" metric is now expanding its support to cover all Azure service in addition to its existing support for Azure Compute and Azure Database.

How this feature can help you

"Cost (List)", is a Cloudability cost metric providing consistent and "unadulterated" view of cloud costs by excluding the benefits of reservations, Spot instances, and custom pricing. In a cloud landscape where various types of discounts and commitments continually influence the rates paid for cloud usage, having an "unadultered" cost metric in invaluable. Doing so allows you to influence discounts or commitment coverage for consistency in cloud pricing. This not only helps with financial planning but is also effective in measuring the impact of your efficiency initiatives.

More information about the release

For this release, the changes focus on providing forward-looking insights. If you are interested in accessing historical data, please reach out to your account team or the TAM to have a backfill done.

## Support for Cost (Adjusted Amortized) metric in Cloudability AWS Resource Inventory - October 4, 2023

This release introduces the support for Cost (Adjusted Amortized) metric in AWS Resource Inventory feature.

You will find this metric as one of the default columns on AWS Resource Inventory report grid.

## Anomaly Detection Enhancement: Support to configure Email/ PagerDuty alerts on Percentage threshold - September 28, 2023

This release introduces a new capability in Anomaly detection feature that allows you to configure alerts based on the percentage threshold. This enhancement complements our existing alerting system which is based on absolute values, and provides you with more flexibility and precision in managing your alerts.

How this feature can help you

With this update, you can now configure alerts to trigger based on percentage thresholds in addition to the existing absolute value alerts. This means that you have the option to set up alerts based on a specific percentage change from a baseline or absolute values, depending on your monitoring needs. Both the combination or either of them (Percentage threshold, Absolute value) will be supported for a particular view. This flexibility allows you to tailor your alerting strategy to match your specific use cases and requirements.

Please be aware that this new percentage threshold alerting capability is not retroactive. To take advantage of this feature, you will need to set up new configurations for percentage thresholds if they are required for your monitoring. Existing alert configurations based on absolute values will continue to function as before.

![anomaly detction screenshot ](../images/anomaly_detection_threshold_new.jpg)

## Improved Kubernetes label handling in Cloudability Container Insights - September 28, 2023

How this feature can help you

Currently, when container-associated metadata including namespace labels, service labels, deployment labels, and node labels shares the same label key but features different label values, these values are merged together. To enhance this, we are introducing a change to our pipeline. This change will ensure that only the most relevant label value is displayed, eliminating label concatenation.

In scenarios where container-associated metadata possesses label keys with conflicting label values, our system will prioritize the most relevant label value. The determination of relevance is based on the granularity of the resource. Here is the order of relevance (from highest to lowest):

1. Pod
1. 1st-level pod owner (e.g., ReplicaSets, Daemonsets, Jobs)
1. 2nd-level pod owner (e.g., Deployments)
1. Kubernetes Service
1. Namespace
1. Node

Following the release of this change to production, users will no longer encounter concatenated values under the Labels tab on the Container Insights page for data received after the release date. Additionally, users may notice higher cost allocations for label values that were previously artificially lowered due to cost being assigned to concatenated values.

- Historical data containing concatenated label values will remain unaltered.
- GKE clusters may still display concatenated label values in Reporting.

While we aim to eliminate concatenated label values, there are rare scenarios where concatenation will still occur. This includes cases where a pod is associated with two or more different Kubernetes services, and these services have conflicting label values with no other more relevant object to take precedence.

If you have any questions or require further information, please do not hesitate to contact your account team or support.

## Sorting capability in Cloudability Resource Inventory - September 25, 2023

This release introduces the much more convenient manual sorting options to the Cloudability Resource Inventory feature released in July 2023. Back then, the feature only had the default auto sorting option by Cost (Total) descending and with this release, users can sort their inventory data based on any of the desired columns (dimensions or metrics) displayed on the inventory report grid.

Users can now select any of the column headers displayed on the inventory report grid in order to sort the inventory data in alphabetical order (for text-based columns) or ascending/descending order (for number-based columns). The option is indicated by the customary arrow icon, as shown below:

See Resource Inventory for more information on the original feature.

## Cloudability for OCI – Cost Management - September 14, 2023

How this feature can help you

This release enables OCI customers to:

- Automatically allocate all OCI costs back to the business based on their specific rules, leveraging Cloudability business dimensions
- Analyze their OCI spend and improve team ownership by leveraging resource-level analytics, interactive multi-cloud dashboards and personalized views
- Drive financial accountability by setting up OCI budgets and event notifications

If you are already an OCI customer, you can start your cost management journey by adding credentials for your tenancy following the instructions for Connect Oracle Cloud .

By default, Cloudability will ingest the current month of OCI data after your credentials are validated. If you would like additional months of data ingested, please reach out to the Apptio team who will be happy to assist you.

For those looking for programmatic access for managing their OCI credentials please check out our public API documentation .

## Cloudability Compute Instance Type/ Family Exclusion Filtering in Rightsizing Preferences - August 30, 2023

How this feature can help you

Previously, Cloudability only provided instance type/ family filtering for compute rightsizing recommendations at the page level and only for the top recommendations given, with no way to filter globally or on an individual recommendation basis. This release provides a new global setting for you within Rightsizing Preferences to exclude compute recommendations containing specific instance types/ families based on exclusion values as entered.

More information about the release

Instance-related filtering and/ or exclusion already exists locally on the compute rightsizing pages using the Instance Family (New) & Instance Type (New) filters. However, these only filter recommendations that have a top recommendation with these values. This new global Rightsizing Preferences functionality provides you a mechanism to exclude all compute recommendations that meet the criteria (values) entered by you regardless of the recommendation being a top recommendation or one of the many recommendation options contained in the rightsizing details pane. There are intentional limitations that are by design on which recommendations are applicable to this exclusion mechanism– recommendations of “terminate” and “no action” will not be bound by the exclusion list as a change to the instance type/family is not actually being recommended.

From the Cloudability primary navigation menu, under the Settings menu item select the option for Rightsizing Preferences. Under Compute (VM) Preferences, there is an option to “Exclude recommendations where the recommended instance type contains the following values”. Under this option, there will be text boxes where you can enter additional values which will then exclude any compute recommendations where the instance type/ family contains these values.

## Analyze the cost contribution for each resource type in Container Insights - August 18, 2023

This release introduces the ability to track costs associated with each resource type, such as CPU and memory within Container Insights of Cloudability.

How this feature can help you

With this feature release, you are able to view comprehensive cost insights for a range of usage metrics including Memory, CPU, GPU, Filesystem, Persistent Volume (PV), Network RX, and Network TX.

More information about the release

The key features of this enhancement are :

- Cost Tracking: We understand the importance of managing expenses, so we've integrated cost tracking for a variety of usage metrics directly within the Container Insights page. This enables you to make informed decisions about resource allocation and optimization.
- Flexible Cost Metrics: This feature will support both the Utilized and Fairshare Cost metric for each of the Usage metrics (e.g: CPU Utilized Cost, CPU Fairshare Cost), offering you the flexibility to tailor the cost analysis to your preferences.
- Comprehensive Metric Coverage: The metrics covered under this enhancement include CPU, Memory, GPU, Filesystem, Persistent Volume (PV), Network RX, and Network TX. This comprehensive coverage empowers you to gain deep insights into the cost implications of each aspect of your containerized environment.
- Historical Cost Analysis: Starting from August 18 2023, historical cost data will be accessible for all supported metrics. This enables you to track cost trends over time and make well-informed decisions about resource utilization.
- Public Endpoints Support: In this release, you will also be able to access these enriched metrics through our public endpoints, ensuring seamless integration with existing workflows for Cloudability API.

You can manually select/ deselect additional cost columns as below.

For any questions or assistance, please reach out to your account team or support.

## Comments enhancement for Rightsizing and Rightsizing ROI in Cloudability - August 14, 2023

This release provides enhancements added for the Rightsizing /Rightsizing ROI Comments functionality.

How this feature can help you

This functionality adds an indicator on the “Comments” icon when comments have been added and exist for a recommendation. Additionally, comments that exist for any specific recommendation shown on either the Rightsizing page or the Rightsizing ROI page will be merged and any comments made on either page going forward will appear on both pages.

More information about the release

Up until this release, there was no indicator shown when a comment was made on a Rightsizing recommendation. In order to see whether any comments had been made, you had to actually click on the comments icon and open up the comments modal. This release introduces an indicator on the comments icon in the table whenever any comments are available.

Previously, any comments made on a specific resource were stored separately when made on the Rightsizing page vs. the Rightsizing ROI page. To help avoid confusion, existing comments for specific resources will be merged from both the pages to create a singular “Comments” archive. Going forward, whenever a comment is added on either page it will appear on both pages and be part of one singular archive of comments for that specific resource.

The comments indicator will appear on the comments icon of a resource in any Rightsizing table where comments exist. This includes the Rightsizing and Rightsizing ROI pages as well as any applicable sub-pages.

## Apptio BI available in Cloudability (BETA) - August 9, 2023

You can access all your Apptio BI reports, including reports based on common FinOps use cases, innovative features, and analyze all data sources directly within Cloudability.

This release is now available to Cloudability customers.. If you want to integrate Apptio BI into your Cloudability application, reach out to your dedicated account team for further assistance and guidance.

## Cloudability - Introducing Three New Cloudability Dimensions- August 4, 2023

How this feature can help you

These dimensions provide enhanced insights and granularity into your Azure spending. These Azure-specific dimensions are:

1. Azure Reservation Order Name : This dimension allows you to track and analyze costs associated with different Azure Reservation Order names. It also helps in gaining a deeper understanding of how various reservation orders impact your overall spending and thereby, optimize your reservations accordingly.
1. Part Number : The Part Number dimension provides detailed visibility into costs based on the specific Azure part numbers associated with your resources. By using this dimension, you can better allocate costs and make informed decisions about resource utilization.
1. Reservation Name : With the Reservation Name dimension, you can now analyze and manage costs related to different Azure reservations. It also helps gaining insights into how reservations are utilized across various resources and thereby, take proactive steps to optimize your reservation utilization.

These new dimensions are specific to Azure cost data and will be available exclusively for Azure resources. They are part of our ongoing efforts to provide comprehensive, Azure-focused cost management capabilities.

## GPU support for Container Cost Insights- July 31, 2023

How this feature can help you

This release introduces a new metric "GPU" in the usage table of the Container Insights page. With this addition, you can easily view the number of GPUs allocated at the cluster, namespace, and label level. The costs allocated to namespace and label values now consider an updated set of weightings accounting for the relative price of GPUs on each node. Since different VMs use varying hardware, the cost of a GPU is therefore tied to each VM family and the specific GPU type utilized by that family.

More information about the release

To provide a better understanding of these changes, let us illustrate a comparison of how costs were previously distributed versus how they are allocated after this update.

|  | Node CPU | Node CPU Weight | Node Memory | Node Memory Weight | Node GPUs | Node GPUs Weight |
| --- | --- | --- | --- | --- | --- | --- |
| Previous | 8 | 25% | 40 GB | 75% | 2 | 0% |
| Current | 8 | 12.5% | 40 GB | 37.5 | 2 | 50% |

With the updated weightings the GPU has been determined to contribute 50% of the VM cost with memory reduced to 37.5% and CPU to 12.5%. The example below shows how this impacts the cost allocation to three hypothetical workloads that are consuming such a VM.

| Workload Planning | CPU Utilization | Memory Utilization | GPU Utilization | Previous Cost Allocation | Updated Cost Allocation |
| --- | --- | --- | --- | --- | --- |
| A | 2 crores | 16 GB | 1 | 36.25% | 43.125% |
| B | 2 crores | 8 GB | 1 | 21.25% | 35.625% |
| C | 4 crores | 16 GB | 0 | 42.5% | 21.25% |

As evident from the above example, the updated model now reflects the true cost of GPU utilization, resulting in more accurate and fair cost allocation across different workloads. Workloads A and B show an increase in price, reflecting their utilization of the relatively expensive GPU resource. This improvement provides you with greater visibility into your resource costs and enable better cost management.

This release supports GPU-backed workloads running in AWS and GCP. Specifically, the use case addressed in this release is fully reserved GPUs (support for Nvidia's MIG implementation is not part of this release ). We are actively working on adding full support for GPU-backed VMs running on Azure. Currently for Azure VMs the usage metric is surfaced for GPU consumption, but the cost weightings have not been updated. This update is reflected from August 1st, 2023 without any impact on historical usage and cost.

## Rightsizing support for GCP Managed Instance Groups - July 25, 2023

Previously, Rightsizing recommendations were provided for each individual resource only, even if the machine was generated by and used solely within a single ‘cluster’ such as a GCP Managed Instance Group. With this release, Cloudability Rightsizing provides recommendations for GCP GCE MIGs. Customers can take actions to implement on the group itself, which will then automatically apply to resources created by that group.

How this feature can help you

GCP customers that use MIGs can now automatically see specific recommended actions for savings at the group configuration level as opposed to only at the individual resource level.

The savings of the group will potentially be much larger than each resource within the group. Additionally, resources that are a part of managed instance groups are configured as a group, so providing recommendations at the group level and at the individual virtual machine level is optimal since these groups are configured as a whole entity.

More information about the release

GCE MIG is available under the GCP tab under Rightsizing . GCP MIG data and rightsizing recommendations are automatically displayed if the customer uses GCP MIGs.

This user experience is similar to Apptio’s existing rightsizing functionality for individual GCE resources. The main table shows all groups with spend in the time specified. Groups are sorted by cost savings by default. Customers can start at the top of the list to see the groups with the highest potential savings.

Recommendations for MIG resources will not be duplicated under multiple services (such as both GCE and GCE MIG). If a resource is part of a managed instance group, it will no longer appear under the standard GCP GCE rightsizing recommendations. It will only appear under the MIG rightsizing recommendations. Only On-Demand resources will be included in these recommendations.

## GPU Utilization support for GCP compute Rightsizing - July 25, 202

For modern workloads such as machine learning, customers are finding cloud virtual machines with not only CPUs, but also GPUs increasingly useful. With this release, GCP customers that have their data ingested by Apptio via GCP or Datadog will also be able to have their GPU data included to receive enhanced rightsizing recommendations.

It will now be possible for GCP customers with compute instances with GPUs to get savings recommendations based on GPU metrics ingested by Apptio, as well as instance type recommendations based on these metrics for instance types with GPUs. These metrics supply a new dimension for the Cloudability recommendations engine to provide additional savings for our customers. Previously, GPU data was not taken into consideration when providing GCP compute rightsizing recommendations.

More information about the release

Rightsizing recommendations for GCE instances with GPUs will automatically be displayed if properly set up and available. There will be a small additions to the “details” view of the recommendation for instances with GPUs as there will now be extra charts for both GPU (%) and GPU memory utilization.

1. Each VM must have GPUs attached .
1. Each VM must have a GPU driver installed .
1. Each VM must have Python 3.6 or newer installed.
1. Each VM must have the packages required for creation of Python virtual environments installed. N1 machine type support will not be part of this release.

## Change in the sender email address for Cloudability users - July 20, 2023

arlier Cloudability users subscribed to emails would receive emails from no-reply-support@apptio.com . From this release onwards, they would now be receiving emails from no-reply@apptio.com due to recent upgrades to our email service. Cloudability customers would simply need to add this new email address to their trusted list, if required.

## Cloudability Reservation Portfolio Support for Azure Databricks - July 20, 2023

How this feature can help you

Azure Databricks customers optimizing their spend through pre-purchase plans can now view and manage their reservations in the Reservation Portfolio. Cloudability expands the services that Reservation Portfolio supports on the Azure Cloud in response to the growing number of customers who utilize Azure. By incorporating Azure Databricks, Cloudability provides these customers with additional value in terms of realizing the value of purchasing reservations on the Azure Cloud.

More information about this release

Due to the difference in how these reservations are applied to usage, our KPI's and table headers have been adjusted to properly reflect the information around the pre-purchase plan credits, DBCUs. Additionally, we've added a third chat on the details panel to help understand the burn-down on a given commitment.

Note: No support for the Reserved Instance Planner is available at this time.

If not already completed, customers need to ensure that the necessary Azure credentials and permissions have been enabled to provide Cloudability with access to their data.

MCA customers: Configure the billing account reader by role by following the instructions here .

EA customers: Regenerate and rerun the script at the EA level by following the instructions here .

## Ticket assignee email notification supported - July 17, 2023

Earlier, Rightsizing ROI was only available with a Jira Cloud integration. After native Rightsizing ROI functionality was released last year, email notifications for ticket assignees were not available since this mechanism was handled via Jira. A separate native mechanism is being added to notify ticket assignees who are part of the native integration when a ticket is assigned to review and/or process.

How this feature can help you

This functionality allows Cloudability users to attach an email address to native Rightsizing ROI ticket assignees so that those assignees can be notified via email when they get assigned a Rightsizing ROI ticket. Available email addresses will be selected from existing Frontdoor users.

More information about this release

The functionality is available when assigning native ROI tickets. On the Rightsizing ROI page, the user can select the details button of a tracked rightsizing ROI recommendation and then select an assignee with an email address which allows for corresponding email notifications. In addition to this, the functionality is available when the user hovers over the details of the recommendation to be tracked in Rightsizing ROI and selects Create Cloudability Issue .

## AWS Resource Inventory - July 7, 2023

How this feature can help you

This feature available for each cloud resource unifies billing, utilization, and descriptive meta data and provides a comprehensive inventory view for the first time within Cloudability reporting for non-EC2 resources.

More information about the release

As part of this release, the AWS Resource Inventory feature has to be enabled for a Cloudability organization from the Active Admin console. By default, only Admin or Cloudability Admin roles will be able to access this feature. However, it can also be granted to any custom role by assigning the permission titled AWSResourceInventoryFullAccess to it.

The supported AWS for this feature include EC2, EBS, S3, RDS, and Redshift.

After the Resource Inventory feature is enabled from the Active Admin, it may take upto 2-3 business days for the data to start appearing in the inventory reports.

Inventory Report Measures

- Measures refer to dimensions, metrics or tags pulled from the billing data. You can include up to 20 such columns for an individual report.
- Each AWS service support a specific set of dimensions and metrics.
- You are able to filter the inventory reports using any of the measures available within the feature.
- Inventory data is sorted by Cost (Total) in descending order (By default).

For each service (eg: EC2, EBS etc.), KPIs are displayed at the top providing you with key summary information like new or idle resources for the current month.

Inventory Reporting Date Windows

Upon enabling this feature, resource inventory data will be back filled to the beginning of the current month. The Inventory data is usually available for three months including the current and earlier two months.

You can export the reports in CSV format including any number of columns relevant to a particular service without any restrictions.

## Container Cost Allocation – Improved CPU/Memory weighting for Namespace & Label allocation - July 3, 2023

This release improves how costs are allocated to individual Namespaces and Labels, better matching how the underlying Virtual Machines are charged by the cloud vendors.

Enhancements to Container Cost Allocation

With this release, Cloudability has improved how costs are allocated to individual Namespace and Label values to better match how the underlying Virtual Machines are charged by the cloud vendors. The process of splitting and allocating the cost of each VM involves apportioning the total cost across the constituent resources (CPU, Memory, Network, etc.) and then assigning the cost to each Namespace and Label based on how much of these resources they consumed. Memory and CPU combined make up the largest component (85%) of VM costs.

Until now, Cloudability used a standard ratio to split this component regardless of VM type (skewing costs toward memory). With this release, Cloudability has made the ratio dependent on machine type – compute-optimized machines will have the ratio skewed towards CPU relative to memory-optimized machines. This has been achieved by putting prices on CPU (core hours) and memory (GB hours) based on analysis of different VM categories and how these two resource types impact VM prices. The net result is a more accurate representation of how each Namespace and Label is contributing to costs.

More information about this release

This release does not impact cluster level cost allocation. For more information, join the conversation on the Apptio Community .

## Container - Cost Allocation for EBS supported- July 3, 2023

How this feature can help you

Earlier, Filesystem was the combination of ephemeral and persistent storage for various Kubernetes constructs, including Cluster, Namespace, labels, and Services. With these updates, Doing this allows us to provide state-of-the-art cost allocations of one of the most significant cost drivers (EBS) to your EKS clusters.

These enhancements aim to offer a more detailed and holistic view of resource utilization and cost allocation within containerized environments, allowing for better optimization and management of cloud expenses. In this release, we will specifically support EBS (AWS) resources.

As part of these changes, Cloudability introduces an additional dimension called Persistent Volume as a column on the insights page. This new dimension will accurately represent the allocations related to Filesystems.

With these updates, all ephemeral storage will be categorized under the existing Filesystem metric, while Persistent Volume usage will be reflected under the new Persistent Volume metric.

You may also notice cost allocations change around namespaces, services, and labels, especially around workloads that use a very large or a very small amount of Filesystem.

To clarify the distinction in EKS clusters:

| Filesystem | Persistent Volumes |
| --- | --- |
| Resource Typically backed by an EBS root volume Occasionally backed by EC2 Instance Store on older instance types | Resource Supported EBS volume (both CSI and in-tree versions) Common AWS services not yet supported Amazon EFS Amazon FSx |
| Typical use cases Logs Scratch or tmp directories Filesystem bound to the lifecycle of your workloads | Typical use cases Storage that needs to be persisted across pod lifecycles Statefulsets |

For this release

- The Persistent Volume dimension supports only EBS (AWS) services. Consequently, for all other services and cloud vendors, the value reflected in this dimension is denoted as Not available.
- These updates provide a more granular view of Filesystem allocations and allow for better analysis and cost optimization within containerized environments.
- Alongside introducing the new Persistent Volume metric for usage analysis, we are also revamping the user interface (UI) by leveraging AG grid.
- As part of this UI enhancement, users will have the flexibility to customize the columns displayed on the insights page. They will be able to choose the specific columns they want to see, allowing them to personalize the view based on their preferences and requirements. This feature will provide users with greater control over the displayed information and streamline their analysis process.

![container cost allocation screenshot](../images/ebs-new.jpg)

- Any resources (volumes or nodes) that cost less than $0.01/hr won't be reflected in total cluster costs.
- he details panel remains unchanged, except for the addition of insights related to the newly introduced Persistent Volume dimension.

## RI Portfolio and Planner support for Azure Cosmos DB - June 22, 2023

How this feature can help you

Customers can view the savings and benefits of the proposed RI purchase, and filter the recommendations based on look back period, region, scope, terms, and accounts. The Reservation Portfolio will provide Cloudability customers with their current reservation portfolio for Azure Cosmos DB instances to go along with the other services we currently provide support for.

Cloudability expands the services that Reservation Portfolio and Reserved Instance Planner support on the Azure Cloud in response to the growing number of customers who utilize Azure. By incorporating Azure Cosmos DB, Cloudability provides these customers with additional value in terms of realizing the value of purchasing reservations on the Azure Cloud. Also, the addition of Azure Cosmos DB support provides customers with actionable insights and recommendations that improve their business outcomes, all from a single pane of glass.

More information about the release

As part of this release, the Planner/Recommendation feature will now be located under the Optimize > Reserved Instance Planner menu item while the Portfolio feature will continue to be located under the Insights > Reservation Portfolio menu Item.

If not already completed, customers need to ensure that the necessary Azure credentials and permissions have been enabled to provide Cloudability with access to their data.

## Support for Kubernetes 1.26 and 1.27 Versions - June 15, 2023

How this feature can help you

This capability will enable customers to gain visibility into their container resource usages, and the cost for their clusters running on both those Kubernetes versions.

Customers should now be able to download and deploy our metrics agent using the regular provisioning workflow.

Our metrics agent has not been tested with Azure Kubernetes Service (AKS) and Google Kubernetes Engine (GKE) for 1.27 version. After Azure and GCP officially announce the support for 1.27 version, we will validate our metrics agent and update our release notes.

## Support for Red Hat OpenShift clusters on AWS (ROSA) - June 7, 2023

By incorporating ROSA into the Cloudability ecosystem, users can now effectively track and allocate costs associated with their OpenShift clusters, bringing them in line with the capabilities already available for EKS, GKE, and AKS users.

This will allow Cloudability customers leveraging ROSA to access detailed cost allocation information specifically tailored to their OpenShift container resources.

Support for OpenShift cluster versions 4.10, 4.11 and 4.12 is included in this release.

How this feature can help you

With this release, users can easily identify and select their preferred OpenShift cluster version when provisioning resources. This enhancement provides users with greater flexibility and enables them to leverage the specific features and improvements offered by different OpenShift versions.

More information about this release

Follow these steps to view and choose OpenShift cluster versions during the provisioning process:

1. Go to the Cloudability platform and navigate to the Insights section.
1. Select Container and then select Provision Cluster . You will notice that instead of the Kubernetes Version option, there is now a Cluster Version option.
1. Select Cluster Version to proceed.
1. In the drop-down menu that appears, you will not only see the existing Kubernetes versions but also the available OpenShift versions.
1. Choose the desired OpenShift version from the dropdown menu.

## Azure Savings Plan Portfolio and Recommendations supported - May 31, 2023

Previously, savings plan recommendations were provided only for AWS in Cloudability. Azure savings plans provide an additional option to reduce costs for customers with consistent compute spend by committing to a fixed hourly spend on compute services for one-year or three-year terms.

How this feature can help you

Azure customers can now view their Savings Plan inventory as well as receive purchase recommendations within the Cloudability platform. Customers can view an inventory of their current Azure Savings Plans along with summary KPIs for the total quantity and hourly commit of their Savings Plans. Customers can also view Azure Savings Plan purchase recommendations as well as summary KPI totals for all the recommendations given including the total number of recommended purchases, the total upfront fees, the estimated net savings, and the estimated savings rate.

More information about this release

From the Cloudability primary navigation menu,

- Under Insights , select Savings Plans and then select the Azure tab to access your savings plan portfolio.
- Under Optimize , select Reserved Instance Planner and then select the Azure SP tab to access your savings plan recommendations.

- For all vendors, Savings Plan portfolios will now be under the Insights menu and Savings Plan recommendations will be under the Optimize menu.
- If not already completed, customers need to ensure that the necessary Azure credentials and permissions have been enabled to provide Cloudability with access to their Savings Plan data.
- MCA customers: Configure the billing account reader by role by following the instructions here .
- EA customers: Regenerate and rerun the script at the EA level by following the instructions here .

## Resource termination recognition supported in Rightsizing ROI – May 31, 2023

In this release, resource termination is recognized when calculating realized savings in Rightsizing ROI.

How this feature can help you

This functionality allows Cloudability users to utilize Rightsizing ROI functionality for calculating the realized savings of actioned recommendations when the action is termination of the resource. Once a rightsizing recommendation has been added via Rightsizing ROI and the resource has been terminated, the realized savings from the termination will be calculated and displayed both for the individual resource as well as added to the rolled-up total of all realized savings.

This is in addition to the support already provided for realized savings calculations when a resource is rightsized. Support will be provided for all services currently supported by Rightsizing ROI.

More information about this release

From the Cloudability primary navigation menu,

- Under the Optimize menu, select Rightsizing ROI .
- Whenever the resource was terminated, a Realized Savings amount appears at the bottom of the list of tracked rightsizing recommendations.
- Note: The Realized Savings amount will also be added to the realized savings total displayed at the top of the page.

## Idle cost distribution available for containers in Cloudability core analytics - May 19, 2023

It’s inevitable that containerized infrastructure runs a certain amount of overhead capacity that is not used by underlying workloads. This “idle” usage has an associated cost (for the backing VMs and volumes) that needs to be accounted for. We have introduced the ability to distribute these idle container costs within Cloudability core analytics (reports and dashboards). While this is a capability that already exists in the dedicated Container Cost Allocation feature, adding it to core analytics can help users streamline chargeback processes and enables more flexible cost reporting. This distribution is done in the context of the Kubernetes constructs namespace and label.

This support is implemented through the introduction of a new metric category “Containers”, which makes available six new metrics. These metrics enable users to view separately the utilized, idle and fairshare costs either with a cash or amortized basis. For customers with custom pricing enabled these will all be represented as “adjusted” metrics.

![idle cost distribution cldy screenshot](../images/cldy-idle-cost.jpg)

How this feature can help you

The Container Cost Allocation feature evaluates resource utilization on each node and marries this to the billing data to calculate the cost of each cluster and to associate a direct, “utilized cost”, to K8s namespace and label values (this has been available within core reporting by using the namespace or a label dimension). With this enhancement you can also report on the idle cost via the new metric, which is allocated to the namespace and label values proportionally based on their direct cost contribution of each node. The Fairshare Cost is simply the Utilized Cost and Idle Cost combined - you could think of it as the total cost.

More information about this release

Some considerations and reporting ideas to keep in mind with these new metrics:

- For non-container costs these new metrics will all return as $0. To filter to container only data try a filter such as “Cluster Name not equals (not set)”
- Use these metrics with different dimensions to easily visualize utilized vs idle. For example, list out by Cluster Name or resource ID.
- For the first time you can use cash and amortized cost basis together for detailed container cost reporting.

With this release, the new metrics introduced will reflect cost data from 1st May 2023. To update additional historical data, reach out to your account team or support for the reprocess to be completed.

## Prompt when rendering 500 or more data points in Cloudability charts - May 18, 2023

Previously, Cloudability users ran into page performance issues when they tried to render 500 or more data points in their chart visualizations. Inarguably, 500 or more data points in a single chart do not serve its purpose due to poor readability, the rendering of the same often slowed down the entire Dashboards page for our users.

How this feature can help you

Cloudability will now display a prompt when users try to render 500 or more data points in their charts, which will prevent them from running into page performance issues. At the time of chart creation, users may not be aware that they’re trying to render visualization for a high cardinality measure like Resource ID but a prompt like this would help them flag the potential risks ahead if they decide to proceed with their action. This prompt will be displayed on all the charts where the limit is exceeded and upon each time the Dashboards page is loaded in Cloudability.

More information about this release

The prompt will have two CTAs:

- Edit Query - Allows to go back to edit window and reduce the data points (to below 500).
- Graph Anyway – Users can proceed to render with the chosen number of data points.

## GPU Utilization support for AWS ASG Rightsizing - May 11, 2023

How this feature can help you

More information about this release

1. From the Cloudability primary navigation menu, Select Optimize > Rightsizing
1. Select the AWS tab, and then select AWS ASG . Rightsizing recommendations for auto scaling groups with GPUs will automatically be displayed once properly set up and available. The "details" view of the recommendation for auto scaling groups utilizing GPUs will now include additional charts for GPU (%) and GPU memory utilization, just as in the AWS EC2 rightsizing recommendations. No additional setup is required for customers who already have AWS Auto Scaling Group rightsizing recommendations and GPU utilization ingestion set up with Cloudability.

## “Max” values added to Rightsizing API and CSV export - April 18, 2023

This release announces the launch of “Throughput Max” and “IOPS Max” values to both the Rightsizing API endpoint(s) and the Rightsizing CSV export(s) for each corresponding vendor’s disk service that is supported in Rightsizing.

More information about this release

The values in the API endpoint are designated as “iopsMax” and “throughputMax”. The values in the exported CSV will contain the column names “IOPS Max” and “Throughput Max”.

## Launch of Cloudability GCP Committed Use Discount Recommendations - April 6, 2023

Cloudability now offers recommendations for GCP CUDs using its own custom engine and new analysis interface. With this new interface, customers can perform what-if analysis, and can have more control over the recommendation generated, allowing them to adjust the recommendations based on their future usage, business strategy, and factor in their risk.

How this feature can help you

Firstly, customers can filter their usage for analysis, which allows them to include or exclude usage for a more accurate analysis that represents their future usage. If a workload was running during the analysis period but should not be covered – such as a testing or development workload, then it can be removed from the analysis. Also, if a workload is being decommissioned or you are going to replace a particular type of usage such as an operating system or database software, then you can exclude that usage from the analysis. In this way, your business strategy will be aligned with more accurate recommendations for future usage.

Customers can add up to 10 Cloudability dimensions to their analysis for filtering. These dimensions can be any of the configured Tags & Labels , Account Groups , or Business Mappings .

## Support for Azure Cost Management APIs - March 30, 2023

This release brings in the support for the Azure Cost Management APIs in Cloudability Credentials. Azure EA customers are now able to use these APIs for getting both the Actual cost and Amortized cost using the Cost Management APIs.

Steps to credential Azure using the new Cost management APIs:

Steps for a new customer:

1. Go to the Cloudability credentialing page and select Azure .
1. Select EA as the Azure account type.
1. Enter the Azure Enrollment ID and Subscription ID .
1. Enter NA in all other fields.
1. Select Generate Setup Script and install the PowerShell script. This power shell script will have a new role called as Enrollment reader which is used to access the Cost Management API.
1. Once done, verify the credentials on the Cloudability UI.

1. If Enrollment reader role access is already available, then enter NA in API Access Key and verify credentials.
1. If Enrollment reader role access is unavailable, then follow the steps as for a new customer.

Nothing needs to be done. In case of billing exports via blob, Cloudability will continue fetching the billing files from there.

## Allow Memory/GPU reducing recommendations without metrics - March 29, 2023

Memory/GPU recommendation settings in Rightsizing Preferences

Cloudability users with global settings can turn on/off recommendations that would result in a reduction in capacity of specific components (memory and GPU) even if metrics for these components are unavailable to Cloudability.

For each of these settings, if the setting is enabled, then the customer receives recommendations that could potentially provide extra savings by reducing the capacity of the component but without taking the current metrics of the component into consideration if the metrics are unavailable to Cloudability.

For each of these settings, if the setting is disabled and the metrics of the component are unavailable to Cloudability , then recommendations will be limited to equivalent capacity or greater (with the GPU setting only applying to GPU-based instances and utilizing instance family).

How this feature can help you

These recommendations help customers to save money by reducing the capacity of particular components, even if those recommendations do not consider the current metrics of those components. As an example, a customer’s familiarity with the resource would allow the customer to know that reducing the component’s capacity would not affect the workload.

More information about this release

1. From the Cloudability primary navigation menu, select Settings > Rightsizing Preferences .
1. Under Compute (VM) Preferences , select Capacity Reduction section.
1. Within Capacity Reduction section, see Allow memory-reducing recommendations without memory utilization metrics and Allow GPU-reducing recommendations without GPU utilization metrics . These options are unchecked by default.

## Azure Custom Role Credentials UI Upgrade - March 15, 2023

This release showcases the Azure custom role permissions in Cloudability Credentials UI in a user-friendly way. Customers would be able to view if they have Azure custom role enabled or not under credentials details. There can be a couple scenarios on roles which are outlined below.

1. Cloudability Customers with Azure reader role and No Custom role will continue to view the Azure reader role as a green tick ( ) and the custom permissions will not be shown. Management: Reader Subscription: ReadSubscription
1. Cloudability Customers with Custom role enabled will only see the custom permissions and will not see the Azure reader role.

- In order to have only Azure custom role, customers should remove the Azure reader role and then enable the custom role.
- This is applicable to the subscription accounts and not on the billing account.

## Separation of Azure Resource Group Tags - March 2, 2023

This release adds the capability for Cloudability to differentiate between Azure Resource Group tags from Azure Resource tags so that customers can distinctly identify and manage them.

Separation of Resource Level tags and Resource Group tags

Previously, Cloudability made no distinction between a Resource Group tag and a Resource tag, both were merged and treated as Resource tags. Customers can now better track and manage their Resource Groups by creating a new business dimension for them, applying specific rules/business mappings to them etc.

Cloudability will now change the format of the tags as follows:

"cldy:Azure:ResourceGroupTag:<TagKey>" for tags generated from Resource Group level

"cldy:Azure:ResourceTag:<TagKey>" for tags generated from Resource level

This feature is not backward compatible. Resource Group tags that were discovered and treated as Resource tags in Cloudability prior to this release would remain as is.

## Container Cost Allocation – Improved CPU/Memory weighting for Namespace & Label allocation - March 1, 2023

This release improves how costs are allocated to individual Namespaces and Labels, better matching how the underlying Virtual Machines are charged by the cloud vendors.

Enhancements to Container Cost Allocation

With this release, Cloudability has improved how costs are allocated to individual Namespace and Label values to better match how the underlying Virtual Machines are charged by the cloud vendors. The process of splitting and allocating the cost of each VM involves apportioning the total cost across the constituent resources (CPU, Memory, Network, etc.) and then assigning the cost to each Namespace and Label based on how much of these resources they consumed. Memory and CPU combined make up the largest component (85%) of VM costs.

Until now, Cloudability used a standard ratio to split this component regardless of VM type (skewing costs toward memory). With this release, Cloudability has made the ratio dependent on machine type – compute-optimized machines will have the ratio skewed towards CPU relative to memory-optimized machines. This has been achieved by putting prices on CPU (core hours) and memory (GB hours) based on analysis of different VM categories and how these two resource types impact VM prices. The net result is a more accurate representation of how each Namespace and Label is contributing to costs.

More information about this release

This release does not impact cluster level cost allocation. For more information, join the conversation on the Apptio Community .

## Container Cost Allocation - Display mapped Kubernetes labels only - January 26, 2023

This release includes enhancements to display only mapped Kubernetes labels on the Container Cost Allocation page.

Enhancements to display only mapped Kubernetes labels

To improve usability and performance, the Container Cost Allocation page will now display only those label keys that have been explicitly mapped on the Tag & Label Mapping page. The Container Cost Allocation page will no longer display all historical labels.

If the Kubernetes label keys are already mapped in your Cloudability environment, then you do not need to make any changes. To add more Kubernetes labels, you can ask your Cloudability administrator to map the specific label keys on the Tags & Mapping page. Be aware that if the Kubernetes label keys are not mapped in your environment, then the Label Key dropdown will not list any keys.

Although the label keys will appear on the Container Cost Allocation page immediately after mapping, it will take 24–48 hours for the values to populate. There is no impact on Namespaces, Services, or visibility of Kubernetes constructs within Cloudability dashboard and reports associated with this release.

## Unit of Measure enhancements to Data transfer, GB Hours, and GB Months metrics - January 18, 2023

This release includes changes to standardize the unit of measurement for usage metrics in Cloudability.

Standardized unit of measurement for usage metrics

The usage metrics will now be displayed in gibibytes (GiB) instead of gigabytes (GB) in Cloudability , which will eliminate confusion and make it easier to understand data without the need to deal with multiple units.

The standardization of unit of measurement affects the following metrics.

| Current Value | New Value |
| --- | --- |
| Data Transfer (gb) | Data Transfer (GiB) |
| GB Hours | GiB Hours |
| GB Months | GiB Months |

Effects on Rightsizing

On the Rightsizing page, all the measurements will be displayed in GiB and the labels will show GiB. Note that the following metrics are already represented in GiB:

RDS memory size

GCP compute memory size

Azure SQL memory size

S3 bucket size

## Support for Kubernetes 1.25 - Container Cost Allocation - January 17, 2023

This release enables the Container Metrics agent to run and collect usage information from clusters running on Kubernetes 1.25 in Azure Kubernetes Service (AKS) environment.

Support for Container Cost Allocation on Kubernetes 1.25 in AKS

Cloudability now supports Container Cost Allocation on Kubernetes 1.25 in AKS environments. This capability will enable you to gain visibility into container resource usage and cost of clusters running on Kubernetes 1.25.

You can download and deploy the Container Metrics agent using the regular provisioning workflow. You can select Kubernetes 1.25 from the Kubernetes Version picker on the Add Cluster Data page.

The Container Metrics agent has not been tested with clusters running Kubernetes 1.25 in the Amazon Elastic Kubernetes Service (EKS) and Google Kubernetes Engine (GKE) environments. This will be done after AWS and GCP officially announce support for Kubernetes 1.25.

## Usage Family enhancements - January 17, 2023

This release includes enhancements to the Usage Family dimension in Cloudability to offer improved mapping quality and higher coverage for cost line items.

Enhancements to the Usage Family dimension

We have made enhancements to the Usage Family dimension. These changes will reflect on your cost line items starting January 1st, 2023. If you have a requirement to reflect these changes beyond the default date, reach out to your account team or support to reprocess the data.

The enhancements offer the following benefits.

Higher coverage for cost line items

Coverage is defined as the percentage of cost classified out of the total. Almost 99% of cost will now be classified into the appropriate Usage Family values, thereby reducing the unmapped cost (that is, Other ).

Improved mapping quality

To offer improved assignment of cost line items, some existing Usage Family values have been remapped.

The following example gives an overview of the remapped values.

New Usage Family values

This release introduces two Usage Family values:.

Security: The examples are given below:

AWS: Amazon GuardDuty , EUW2-PaidKubernetesAuditLogsAnalyzed , $ per Month for Policy-WAF, Amazon Inspector UGE1-agent-assessments , Security Checks for PaidComplianceCheck , $ per endpoint hour for AWS Network Firewall

Azure: Advanced Threat Protection:Azure Database for PostgreSQL/SQL , Azure Defender::Microsoft Defender for Containers , Microsoft Defender for IoT - Managed Devices - Standard

GCP: Clusters with Binary Authorization enabled , Cloud IDS

Load Balancer: The previous Load Balancer Usage was very granular. This value now includes some changes.
