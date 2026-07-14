---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "12-Whats-new-in-Cloudability"
source_files_count: 4
last_updated: "2026-07-13"
---

# 12-Whats-new-in-Cloudability

## Cloudability : What's new in 2023

<!-- sub-header -->
- **breadcrumb:** What's new in Cloudability > Cloudability : What's new in 2023
- **source_path:** SSVCLNQ/release-notes/whats-new-2023.html
- **original_file:** cloudability-whats-new-in-2023.md
- **images:**
  - 03-media/apptio-cloudability-standard/automated_credential.jpg
  - 03-media/apptio-cloudability-standard/container-metrics-openshift_1.jpg
  - 03-media/apptio-cloudability-standard/kubernetes_1.28_versions.jpg
  - 03-media/apptio-cloudability-standard/oci2.jpg
  - 03-media/apptio-cloudability-standard/rn-rightsizing-oci-vms.jpg
  - 03-media/apptio-cloudability-standard/release_notes_screeenshot.jpg
  - 03-media/apptio-cloudability-standard/anomaly_detection_threshold_new.jpg
  - 03-media/apptio-cloudability-standard/cldy-res-inv-sorting.jpg
  - 03-media/apptio-cloudability-standard/oci_rn.jpg
  - 03-media/apptio-cloudability-standard/cost_visibility_usage_metrics_2.jpg
  - 03-media/apptio-cloudability-standard/cldy-bi-8.jpg
  - 03-media/apptio-cloudability-standard/gpu_support_container_insights.jpg
  - 03-media/apptio-cloudability-standard/mig-help-image-2.jpg
  - 03-media/apptio-cloudability-standard/ebs-new.jpg
  - 03-media/apptio-cloudability-standard/kubernetes.jpg
  - 03-media/apptio-cloudability-standard/rosa1.jpg
  - 03-media/apptio-cloudability-standard/cldy-idle-cost.jpg
  - 03-media/apptio-cloudability-standard/cost-management.jpg
  - 03-media/apptio-cloudability-standard/greentick.jpg
  - 03-media/apptio-cloudability-standard/azure-enabled.jpg
  - 03-media/apptio-cloudability-standard/azure-not-enabked.jpg
  - 03-media/apptio-cloudability-standard/kubernetes-label.jpg
  - 03-media/apptio-cloudability-standard/usagefamilyremapping.jpg

### Resource Inventory Support for Views Created with Account Groups - December 28, 2023

With this release, AWS and Azure Resource Inventory would support Views that are created using Account Groups in Cloudability. You can now filter the Resource Inventory data based on the Views that are created using any combination of Tag Dimensions , Account Groups , and Vendor filters.

How this feature can help you

Previously, Resource Inventory would show a "Restricted view" page if you switch to a View that is created using Account Groups .

### Enhanced Logic for Azure Compute in Resource Inventory - December 28, 2023

This release enhances our existing logic to display the Azure Compute resources in Azure Resource Inventory in Cloudability. As a result, you can expect to see a reduction in the number of resources under Compute service and an increase in the number of resources under the Managed Disk services in Azure Resource Inventory.

How this feature can help you

Previously, our logic to display resources under the Compute service factored for snapshot resources and this resulted in a higher resource count being shown than expected for your Azure compute resources. Our new logic is such that the snapshots will be accounted in the Managed Disk service instead of the Compute service. This way, you can expect to see a reduction in the number of resources under Compute service and an increase in the number of resources under the Managed Disk services in Azure Resource Inventory.

### GCP Detailed Billing - December 20, 2023

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

### AWS Automated Credentialing of Linked Accounts - December 19, 2023

With this release, you can quickly credential your AWS-linked accounts. Cloudability now leverages AWS organizations which allows you to group the linked accounts under the organizations, and execute the cloud formation template (CFT) at an organization level. This reduces the number of executions of the AWS CFT.

How to enable automated credentialing

1. Add your linked accounts under AWS organization in the AWS console.
1. On Cloudability , while credentialing the AWS Master Payer accounts, enable the Automated credentialing of linked accounts checkbox.
1. 
1. Generate the CFT template which should be executed in the AWS console.
1. Add credential for any of your linked accounts under the AWS organization, then save and download the template, and execute for the selected linked account in the AWS console.
1. On individual linked accounts, select Edit > Download > Verify credentials to complete the credentialing of the linked accounts.

### GCP Automated Credentialing of GCP Projects- December 19, 2023

This release enables you to quickly credential the GCP projects within Cloudability.

How this feature can help you

Cloudability now enables GCP organizations to group your GCP projects and execute the shell script at an organizational level reducing the number of executions of the script. Earlier it was required to download the shell script and execute it individually on every GCP project for your organization.

### Introducing Cloudability in EU Region - December 19, 2023

How this feature can help you

This release addresses the unique needs of our EU-based clients, ensuring their data remains within the EU boundaries. By localizing our services, we aim to empower organizations to bolster their compliance efforts and align with the regulations regarding cloud cost management data.

More information about the release

The launch of hosting Cloudability in the EU region holds great significance for our customers operating within this region. It provides a reliable and compliant cloud cost management solution that prioritizes data residency, enhances data privacy, and aligns with data protection regulations.

No additional setup or installation is required for customers who are directly onboarding to Cloudability in the EU. The plan to migrate existing customers will be shared early next year.

### Indicating AWS Region for AWS Service Control Policy - December 19, 2023

As an AWS user, this release allows you to indicate the AWS Service control policy region while credentialing your AWS accounts in Cloudability. It enables Cloudability to go and check the permissions on the mentioned region.

How this feature can help you

Earlier we were checking for permissions for AWS accounts only in the us-east-1 region. If SCP was enabled on your end for a specific region (other than us-east-1), you would receive an " Access Denied " error while going for a verification check for your AWS accounts. This release has handled the above situation and enables Cloudability to check the permissions on the mentioned region.

### Support for AWS Account Tags and Azure Subscription Tags - December 18, 2023

With this release, customers can now retrieve their AWS account-level and Azure subscription tags from their cloud accounts into Cloudability. This feature will help customers create tag dimensions for better cost allocation, and chargeback along with tracking their cloud spend.

More information about this release

For easy identification of account-level tags, we have appended the below-mentioned prefixes for account tags in AWS and Azure respectively:

Prefix for AWS: cldy:aws:accountleveltag:

Prefix for Azure: cldy:azure:subscriptionleveltag:

The account tags will appear while creating a tag dimension in the Organize > Tags & Labels screen.

- or the existing AWS customers in Cloudability , a new permission named Organizations: ListTagsForResource will be granted to the Cloudability IAM role that is added in their AWS cloud. This permission is required to get account-level tags from the AWS Organizations.
- For new AWS customers, the above-mentioned permission will be added to Cloudability credentialing template, so no configuration changes are required.
- For the existing and new Azure customers in Cloudability, no configurational changes are required, and the subscription-level tags will start appearing in Organize > Tags & Labels module.

### Cloudability Container Metrics Agent Supporting OpenShift Versions 4.13, 4.14 - December 14, 2023

How this feature can help you

This feature enables detailed insights for the container resource utilization and the associated costs for clusters using the ROSA variant operating on these versions of OpenShift.

You can now easily download and deploy our metrics agent via the standard provisioning workflow.

### Rightsizing ROI - ServiceNow Integration - December 13, 2023

How this feature can help you

This functionality provides the ability to generate ServiceNow request and /or incident tickets containing rightsizing recommendations automatically within your very own ServiceNow instance. This feature closely resembles the current Rightsizing ROI functionality that can integrate with the Jira Cloud.

By integrating Cloudability and ServiceNow, you can now collaborate quickly and efficiently around cloud resources and rightsizing recommendations. This automated ticketing system augments a more efficient rightsizing cadence to promote cloud optimization through normal service processes. You will also have easier accessibility to the records of the details of the recommendations within Cloudability as well as your ServiceNow platform along with actions (if any) taken on the recommendations. You can now automatically calculate and display the realized savings from resulting actions via the Rightsizing ROI page in Cloudability.

More information about the release

You can start by entering your ServiceNow vendor credentials by going to the Cloudability primary navigation menu and navigating to Settings > Vendor Credentials > ServiceNow . You can then set up a Rightsizing ROI policy by navigating to Settings > Rightsizing Policies and defining a policy to start automatically capturing rightsizing recommendations based on the criteria you have defined. This ROI policy criteria is then used to determine which rightsizing recommendations will automatically have tickets created within your ServiceNow instance.

Alternatively, rightsizing recommendations can be captured manually by navigating to the Rightsizing page under Optimize > Rightsizing and manually creating a ServiceNow request (or incident) for an individual recommendation from the menu at the right side of the recommendations table. To view the captured Rightsizing recommendations in Cloudability , navigate to Optimize > Rightsizing ROI .

### Cloudability Rightsizing - Page Level Filtering Options - December 12, 2023

How this feature can help you

This functionality is the first step towards providing Rightsizing filtering options at page-level that filter both the top recommendations as well the additional recommendation options provided in the details pane. There are new 2 options as part of this release:

1. The " Top Multi-Architecture " option which is available on Compute Rightsizing pages. This option filters the details pane recommendation options by showing at least 1 rightsizing recommendations for each CPU architecture - If there are cost savings available for the CPU architecture. The recommendations in the details pane still display in order of greatest cost savings.
1. The " Count Reduction Only " option available on Compute Group Rightsizing pages (currently ASG, MIG). This option filters all recommendations by showing the ones only which reduce the number of instances in the group.

More information about the release

This release benefits by providing you more options for which rightsizing recommendations can be filtered in order to meet your use cases and enhance usability. Additionally, having page-level filtering options that can filter both the top recommendations provided on the page as well as the additional recommendation options provided in the details pane allows more comprehensive filtering possibilities when you require this level of granularity to take appropriate cost saving actions.

From the Cloudability primary navigation menu, under the Optimize menu item select the option for Rightsizing . The " Top Multi-Architecture " option is available on the Compute Rightsizing page for each vendor (for example, AWS’s compute rightsizing page is EC2). The " Count Reduction Only " option is available on the Compute Group Rightsizing page for each vendor (for example, AWS’s compute group rightsizing page is EC2 ASG). Both options will be located near the top of their respective pages next to the current “Filters” that are already provided.

The " Top Multi-Architecture " option will require the “ Allow cross-architecture recommendations ” setting to be globally enabled on the Rightsizing Preferences page located under the Settings menu item as a prerequisite. Changes to these global preferences can take up to 24 hours to take effect.

### Cloudability Mixed Instance Type Recommendations in Rightsizing for AWS ASGs - December 7, 2023

This release provides new Cloudability rightsizing recommendations for mixed instance type for AWS EC2 Auto Scaling Groups (ASGs).

How this feature can help you

Cloudability Rightsizing now provides recommendations for mixed instance type AWS EC2 ASGs. Rightsizing recommendations were previously available only for single instance type ASGs. Like single instance type ASG recommendations, these new recommendations provide cost saving actions to implement on the group itself, which will then automatically apply to resources created by that group.

More information about the release

With added support for rightsizing recommendations for mixed instance type ASGs, you will now have access to additional recommendations for AWS Auto Scaling Groups for cost saving opportunities by identifying resources that can be resized to better match their underlying workloads.

### Cloudability Enhancement: Service Name Mapping Update for AWS Elastic Container Registry - November 22, 2023

This release fixes a bug to ensure that the AWS Elastic Container Registry is correctly mapped to the appropriate service name. With this update, AWS Elastic Container Registry will now be accurately mapped to AWS ECR. This change takes effect today.

If you need this update to be applied to your historical data, reach out to our support team or your account representative to request a reprocess.

### Container Cost Allocation now Supports Kubernetes 1.28 Versions - November 21, 2023

This release announces Container Cost Allocation support for Kubernetes version 1.28 across all providers. This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.28.

Customers can now easily download and deploy our metrics agent via the standard provisioning workflow.

### Oracle Container Engine for Kubernetes: Cost Management and Optimization - November 20, 2023

Users can now seamlessly map and manage all their Kubernetes (K8s) clusters across OCI, AWS, Azure, and GCP, as we are extending support to OKE.

- Container Cost Allocation: Explore and visualize costs for all OKE clusters, categorized by Namespaces and Labels.
- Enhanced Reporting: Cluster Name, Namespace, and Label dimensions are available in core reporting, including reports, dashboards, and TrueCost Explorer.
- Business Mapping & Views: Allocate and categorize containerized costs in tandem with regular cloud costs.
- Rightsizing Recommendations: Optimize resource utilization and cost efficiency by receiving recommendations to align request and limit values with the actual workload requirements, reducing waste and expenses.

For GPU instances, the primary cost factor is GPU and OCI doesn't provide any cost per CPU and Memory. Therefore, we are allocating container costs at GPU level for GPU clusters but there is 0 cost allocation for CPU and Memory.

### Cost Management and Optimization for Oracle Kubernetes Engine - November 20, 2023

This release introduces official Cloudability support for Oracle Kubernetes Engine (OKE). This release achieves feature parity for OCI, empowering users to granularly allocate costs by Namespaces and Labels, facilitating precise cost tracking so that they can be charged back to the business.

Users can now seamlessly map and manage all their Kubernetes (K8s) clusters across OCI, AWS, Azure, and GCP, as we are extending support to OKE.

Key highlights of this release include:

- Container Cost Allocation: Explore and visualize costs for all OKE clusters, categorized by Namespaces and Labels.
- Enhanced Reporting: Cluster Name, Namespace, and Label dimensions are available in core reporting, including reports, dashboards, and TrueCost Explorer.
- Business Mapping & Views: Allocate and categorize containerized costs in tandem with regular cloud costs.
- Rightsizing Recommendations: Optimize resource utilization and cost efficiency by receiving recommendations to align request and limit values with the actual workload requirements, reducing waste and expenses.

For GPU instances, the primary cost factor is GPU and OCI doesn't provide any cost per CPU and Memory. Therefore, we are allocating container costs at GPU level for GPU clusters but there is 0 cost allocation for CPU and Memory.

### Rightsizing Recommendations for OCI Virtual Machines - November 20, 2023

This release supports Cloudability Rightsizing for Oracle Virtual Machines (VMs). This new feature brings attention to over-provisioned and idle resources to provide cost saving opportunities, identifying OCI resources that can be resized to better match customers' underlying workloads and allowing them to track actions in Rightsizing ROI.

![rightsizing recommendations sceenshot ](../images/rn-rightsizing-oci-vms.jpg)

How this feature can help you

- Receiving actionable recommendations for several types of Virtual Machines: Legacy, flex, burstable, bare metal and instance pools.
- Receiving detailed cost savings analysis factoring in CPU, Network, Memory for both 10-day and 30-day time lines.
- Visualizing possible savings across OCI, AWS, Azure, GCP Cloud usage in Rightsizing Explorer.

More information about the release

To receive these recommendations, you need to go through the advanced credentialing process for your child tenancies so that Cloudability can pull the utilization data required for rightsizing. Once the advanced credentials are verified, it may take up to 48 hours for recommendations to appear in Cloudability. The recommendations will be shown on the Rightsizing page under the new “ OCI ” vendor tab.

### Azure Resource Inventory Reporting - November 15, 2023

How this feature can help you

As an Azure user, you have the flexibility to build this list from resources spanning multiple accounts and choose from different measures (dimensions and metrics) to surface the details relevant to them. This information available for each cloud resource unifies billing, utilization and descriptive meta data to provide you with a more comprehensive inventory view.

Azure Resource Inventory reporting feature must be explicitly enabled for your Cloudability Org. You must reach out to your TAM/CSM/account point of contact from Apptio to get this done. By default, only Admin or Cloudability Admin roles will be able to access this feature. However, inventory access can also be granted to any custom role by assigning the custom role with AWSResourceInventoryFullAccess permissions.

More information about the release

You can view month-to-date inventory data for each service. Upon enabling this feature, resource inventory data will be back filled to the beginning of the current month. Over time, inventory data will be available on a three-month rolling window. That is at any point in time, you will be able to access resource inventory data for the current month along with the previous two months. You have the option to export the reports in CSV format. These exports include all the columns supported for the particular service (i.e., there is no 20 column limit).

### Self-service Data Reprocess (Beta) - November 15, 2023

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

### Out-of-the-box Apptio BI Reports for Cloudability TotalCost - November 9, 2023

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

### Support for more Datadog regions - October 20, 2023

New regions supported

The following are the newly supported Datadog regions:

- ap1.datadoghq.com
- us3.datadoghq.com
- us5.datadoghq.com

Support for the existing Datadog regions remains intact, and Cloudability users using these do not require any updates at their ends.

- datadoghq.com
- datadoghq.eu

The process of credentialing Datadog into Cloudability remains the same, with the only addition being be the new regions which you can choose from the dropdown list. For more information on connecting Datadog in Cloudability , see Connect Datadog to Cloudability .

### Cloudability Reservation Portfolio and RI Planner support for Azure Cache for Redis and Synapse Analytics - October 19, 2023

How this feature can help you

Azure Cache for Redis and Synapse Analytics customers optimizing their spend through reservations (both Redis and Synapse Analytics), and pre-purchase plans (Synapse Analytics) can now view and manage their reservations in the Reservation Portfolio. Cloudability expands the services that Reservation Portfolio supports on the Azure Cloud in response to the growing number of customers who utilize Azure. By incorporating Azure Redis and Synapse Analytics, Cloudability provides these customers with additional benefits in terms of realizing the value of purchasing reservations on the Azure Cloud.

More information about the release

Reservations for Azure Cache for Redis and Synapse Analytics dedicated to SQL pools function similarly to Azure Compute, SQL, and Cosmos DB reservations. They are maintained regularly, and are billed hourly.

Pre-purchase plans for Azure Synapse Analytics function similarly to Databricks. These reservations are interchangeable credits that can be used across the duration of the reservation. Unlike most of the reservations, they are not maintained regularly. Our KPIs and table headers have been adjusted to properly reflect the information around the pre-purchase plan credits, and SCUs. Similar to Databricks, we've added a third chart to the details panel to help understand the burn-down on a given commitment.

Support for the Reserved Instance Planner for Azure Synapse Analytics pre-purchase plans is not available at this time.

If not already completed, you need to ensure that the necessary Azure credentials, and permissions have been enabled to provide Cloudability with access to your data.

MCA customers: Configure the billing account reader by role following the instructions here .

### Utilization Reporting enhancements for AWS EBS and GPU - October 18, 2023

These newly introduced metrics are as follows:

- Burst Balance - Provides information about the percentage of I/O credits (for gp2) or throughput credits (for st1 and sc1) remaining in the burst bucket. Used with General Purpose SSD (gp2), Throughput Optimized HDD (st1), and Cold HDD (sc1) volumes only.
- Volume Consumed Read Write Ops - The total amount of read and write operations (normalized to 256K capacity units) consumed in a specified period of time. Used with Provisioned IOPS SSD volumes only.
- Volume Throughput Percentage - The percentage of I/O operations per second (IOPS) delivered of the total IOPS provisioned for an Amazon EBS volume. Used with Provisioned IOPS SSD volumes only. This metric is not supported with Multi-Attach enabled volumes
- GPU Utilization - Percentage of time over a sample period where one or more kernels on the GPU was running.
- GPU Memory Utilization - Percentage of time over a sample period where memory was being written or read. For successful results with GPU metrics, make sure you have configured minimal GPU metrics as a prerequisite.

How this feature can help you

This release enhances the support for AWS utilization metrics in Cloudability and enables customers to get insights into AWS EBS and GPU utilization metrics.

### Support for Turbonomic integration with Cloudability - October 17, 2023

How this feature can help you

For current (and future) customers of both Cloudability and Turbonomic , there is optimization-related functionality & data that exist in one product but not the other. Previously there was no Out-of-the-Box integration between Cloudability and Turbonomic and therefore customers of both products would need to go to each product separately in order to utilize the functionality contained in each one. This feature will initiate the process of enhancing Cloudability allowing customers of both products to have additional Turbonomic functionality & data displayed directly in Cloudability itself.

More information about the release

In order to set up Turbonomic credentialling, select “ Settings ” menu item from the Cloudability primary navigation menu and then from the expanded sub-menu select “ Vendor Credentials ”. On the Credentials page, select the navigation tab for Turbonomic to start the process of hooking Turbonomic account credentials into Cloudability. Once the Cloudability/Turbonomic integration is set up, navigate to the new Turbonomic page by selecting " Optimize " menu item from the Cloudability primary navigation menu item and then from the expanded sub-menu select “ Turbonomic ”. The new functionality & data will be displayed starting with the Necessary Investments & Potential Savings Cloud charts and accompanying values from Turbonomic .

### Expanding Support for Cloudability Cost (List) metric to all Azure services - October 13, 2023

This release introduces a significant enhancement to Cloudability with a more comprehensive and consistent cost metric for cloud expenditures.

Our "Cost (List)" metric is now expanding its support to cover all Azure service in addition to its existing support for Azure Compute and Azure Database.

How this feature can help you

"Cost (List)", is a Cloudability cost metric providing consistent and "unadulterated" view of cloud costs by excluding the benefits of reservations, Spot instances, and custom pricing. In a cloud landscape where various types of discounts and commitments continually influence the rates paid for cloud usage, having an "unadultered" cost metric in invaluable. Doing so allows you to influence discounts or commitment coverage for consistency in cloud pricing. This not only helps with financial planning but is also effective in measuring the impact of your efficiency initiatives.

More information about the release

For this release, the changes focus on providing forward-looking insights. If you are interested in accessing historical data, please reach out to your account team or the TAM to have a backfill done.

### Support for Cost (Adjusted Amortized) metric in Cloudability AWS Resource Inventory - October 4, 2023

This release introduces the support for Cost (Adjusted Amortized) metric in AWS Resource Inventory feature.

You will find this metric as one of the default columns on AWS Resource Inventory report grid.

### Anomaly Detection Enhancement: Support to configure Email/ PagerDuty alerts on Percentage threshold - September 28, 2023

This release introduces a new capability in Anomaly detection feature that allows you to configure alerts based on the percentage threshold. This enhancement complements our existing alerting system which is based on absolute values, and provides you with more flexibility and precision in managing your alerts.

How this feature can help you

With this update, you can now configure alerts to trigger based on percentage thresholds in addition to the existing absolute value alerts. This means that you have the option to set up alerts based on a specific percentage change from a baseline or absolute values, depending on your monitoring needs. Both the combination or either of them (Percentage threshold, Absolute value) will be supported for a particular view. This flexibility allows you to tailor your alerting strategy to match your specific use cases and requirements.

Please be aware that this new percentage threshold alerting capability is not retroactive. To take advantage of this feature, you will need to set up new configurations for percentage thresholds if they are required for your monitoring. Existing alert configurations based on absolute values will continue to function as before.

![anomaly detction screenshot ](../images/anomaly_detection_threshold_new.jpg)

### Improved Kubernetes label handling in Cloudability Container Insights - September 28, 2023

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

### Sorting capability in Cloudability Resource Inventory - September 25, 2023

This release introduces the much more convenient manual sorting options to the Cloudability Resource Inventory feature released in July 2023. Back then, the feature only had the default auto sorting option by Cost (Total) descending and with this release, users can sort their inventory data based on any of the desired columns (dimensions or metrics) displayed on the inventory report grid.

Users can now select any of the column headers displayed on the inventory report grid in order to sort the inventory data in alphabetical order (for text-based columns) or ascending/descending order (for number-based columns). The option is indicated by the customary arrow icon, as shown below:

See Resource Inventory for more information on the original feature.

### Cloudability for OCI – Cost Management - September 14, 2023

How this feature can help you

This release enables OCI customers to:

- Automatically allocate all OCI costs back to the business based on their specific rules, leveraging Cloudability business dimensions
- Analyze their OCI spend and improve team ownership by leveraging resource-level analytics, interactive multi-cloud dashboards and personalized views
- Drive financial accountability by setting up OCI budgets and event notifications

If you are already an OCI customer, you can start your cost management journey by adding credentials for your tenancy following the instructions for Connect Oracle Cloud .

By default, Cloudability will ingest the current month of OCI data after your credentials are validated. If you would like additional months of data ingested, please reach out to the Apptio team who will be happy to assist you.

For those looking for programmatic access for managing their OCI credentials please check out our public API documentation .

### Cloudability Compute Instance Type/ Family Exclusion Filtering in Rightsizing Preferences - August 30, 2023

How this feature can help you

Previously, Cloudability only provided instance type/ family filtering for compute rightsizing recommendations at the page level and only for the top recommendations given, with no way to filter globally or on an individual recommendation basis. This release provides a new global setting for you within Rightsizing Preferences to exclude compute recommendations containing specific instance types/ families based on exclusion values as entered.

More information about the release

Instance-related filtering and/ or exclusion already exists locally on the compute rightsizing pages using the Instance Family (New) & Instance Type (New) filters. However, these only filter recommendations that have a top recommendation with these values. This new global Rightsizing Preferences functionality provides you a mechanism to exclude all compute recommendations that meet the criteria (values) entered by you regardless of the recommendation being a top recommendation or one of the many recommendation options contained in the rightsizing details pane. There are intentional limitations that are by design on which recommendations are applicable to this exclusion mechanism– recommendations of “terminate” and “no action” will not be bound by the exclusion list as a change to the instance type/family is not actually being recommended.

From the Cloudability primary navigation menu, under the Settings menu item select the option for Rightsizing Preferences. Under Compute (VM) Preferences, there is an option to “Exclude recommendations where the recommended instance type contains the following values”. Under this option, there will be text boxes where you can enter additional values which will then exclude any compute recommendations where the instance type/ family contains these values.

### Analyze the cost contribution for each resource type in Container Insights - August 18, 2023

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

### Comments enhancement for Rightsizing and Rightsizing ROI in Cloudability - August 14, 2023

This release provides enhancements added for the Rightsizing /Rightsizing ROI Comments functionality.

How this feature can help you

This functionality adds an indicator on the “Comments” icon when comments have been added and exist for a recommendation. Additionally, comments that exist for any specific recommendation shown on either the Rightsizing page or the Rightsizing ROI page will be merged and any comments made on either page going forward will appear on both pages.

More information about the release

Up until this release, there was no indicator shown when a comment was made on a Rightsizing recommendation. In order to see whether any comments had been made, you had to actually click on the comments icon and open up the comments modal. This release introduces an indicator on the comments icon in the table whenever any comments are available.

Previously, any comments made on a specific resource were stored separately when made on the Rightsizing page vs. the Rightsizing ROI page. To help avoid confusion, existing comments for specific resources will be merged from both the pages to create a singular “Comments” archive. Going forward, whenever a comment is added on either page it will appear on both pages and be part of one singular archive of comments for that specific resource.

The comments indicator will appear on the comments icon of a resource in any Rightsizing table where comments exist. This includes the Rightsizing and Rightsizing ROI pages as well as any applicable sub-pages.

### Apptio BI available in Cloudability (BETA) - August 9, 2023

You can access all your Apptio BI reports, including reports based on common FinOps use cases, innovative features, and analyze all data sources directly within Cloudability.

This release is now available to Cloudability customers.. If you want to integrate Apptio BI into your Cloudability application, reach out to your dedicated account team for further assistance and guidance.

### Cloudability - Introducing Three New Cloudability Dimensions- August 4, 2023

How this feature can help you

These dimensions provide enhanced insights and granularity into your Azure spending. These Azure-specific dimensions are:

1. Azure Reservation Order Name : This dimension allows you to track and analyze costs associated with different Azure Reservation Order names. It also helps in gaining a deeper understanding of how various reservation orders impact your overall spending and thereby, optimize your reservations accordingly.
1. Part Number : The Part Number dimension provides detailed visibility into costs based on the specific Azure part numbers associated with your resources. By using this dimension, you can better allocate costs and make informed decisions about resource utilization.
1. Reservation Name : With the Reservation Name dimension, you can now analyze and manage costs related to different Azure reservations. It also helps gaining insights into how reservations are utilized across various resources and thereby, take proactive steps to optimize your reservation utilization.

These new dimensions are specific to Azure cost data and will be available exclusively for Azure resources. They are part of our ongoing efforts to provide comprehensive, Azure-focused cost management capabilities.

### GPU support for Container Cost Insights- July 31, 2023

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

### Rightsizing support for GCP Managed Instance Groups - July 25, 2023

Previously, Rightsizing recommendations were provided for each individual resource only, even if the machine was generated by and used solely within a single ‘cluster’ such as a GCP Managed Instance Group. With this release, Cloudability Rightsizing provides recommendations for GCP GCE MIGs. Customers can take actions to implement on the group itself, which will then automatically apply to resources created by that group.

How this feature can help you

GCP customers that use MIGs can now automatically see specific recommended actions for savings at the group configuration level as opposed to only at the individual resource level.

The savings of the group will potentially be much larger than each resource within the group. Additionally, resources that are a part of managed instance groups are configured as a group, so providing recommendations at the group level and at the individual virtual machine level is optimal since these groups are configured as a whole entity.

More information about the release

GCE MIG is available under the GCP tab under Rightsizing . GCP MIG data and rightsizing recommendations are automatically displayed if the customer uses GCP MIGs.

This user experience is similar to Apptio’s existing rightsizing functionality for individual GCE resources. The main table shows all groups with spend in the time specified. Groups are sorted by cost savings by default. Customers can start at the top of the list to see the groups with the highest potential savings.

Recommendations for MIG resources will not be duplicated under multiple services (such as both GCE and GCE MIG). If a resource is part of a managed instance group, it will no longer appear under the standard GCP GCE rightsizing recommendations. It will only appear under the MIG rightsizing recommendations. Only On-Demand resources will be included in these recommendations.

### GPU Utilization support for GCP compute Rightsizing - July 25, 202

For modern workloads such as machine learning, customers are finding cloud virtual machines with not only CPUs, but also GPUs increasingly useful. With this release, GCP customers that have their data ingested by Apptio via GCP or Datadog will also be able to have their GPU data included to receive enhanced rightsizing recommendations.

It will now be possible for GCP customers with compute instances with GPUs to get savings recommendations based on GPU metrics ingested by Apptio, as well as instance type recommendations based on these metrics for instance types with GPUs. These metrics supply a new dimension for the Cloudability recommendations engine to provide additional savings for our customers. Previously, GPU data was not taken into consideration when providing GCP compute rightsizing recommendations.

More information about the release

Rightsizing recommendations for GCE instances with GPUs will automatically be displayed if properly set up and available. There will be a small additions to the “details” view of the recommendation for instances with GPUs as there will now be extra charts for both GPU (%) and GPU memory utilization.

1. Each VM must have GPUs attached .
1. Each VM must have a GPU driver installed .
1. Each VM must have Python 3.6 or newer installed.
1. Each VM must have the packages required for creation of Python virtual environments installed. N1 machine type support will not be part of this release.

### Change in the sender email address for Cloudability users - July 20, 2023

arlier Cloudability users subscribed to emails would receive emails from no-reply-support@apptio.com . From this release onwards, they would now be receiving emails from no-reply@apptio.com due to recent upgrades to our email service. Cloudability customers would simply need to add this new email address to their trusted list, if required.

### Cloudability Reservation Portfolio Support for Azure Databricks - July 20, 2023

How this feature can help you

Azure Databricks customers optimizing their spend through pre-purchase plans can now view and manage their reservations in the Reservation Portfolio. Cloudability expands the services that Reservation Portfolio supports on the Azure Cloud in response to the growing number of customers who utilize Azure. By incorporating Azure Databricks, Cloudability provides these customers with additional value in terms of realizing the value of purchasing reservations on the Azure Cloud.

More information about this release

Due to the difference in how these reservations are applied to usage, our KPI's and table headers have been adjusted to properly reflect the information around the pre-purchase plan credits, DBCUs. Additionally, we've added a third chat on the details panel to help understand the burn-down on a given commitment.

Note: No support for the Reserved Instance Planner is available at this time.

If not already completed, customers need to ensure that the necessary Azure credentials and permissions have been enabled to provide Cloudability with access to their data.

MCA customers: Configure the billing account reader by role by following the instructions here .

EA customers: Regenerate and rerun the script at the EA level by following the instructions here .

### Ticket assignee email notification supported - July 17, 2023

Earlier, Rightsizing ROI was only available with a Jira Cloud integration. After native Rightsizing ROI functionality was released last year, email notifications for ticket assignees were not available since this mechanism was handled via Jira. A separate native mechanism is being added to notify ticket assignees who are part of the native integration when a ticket is assigned to review and/or process.

How this feature can help you

This functionality allows Cloudability users to attach an email address to native Rightsizing ROI ticket assignees so that those assignees can be notified via email when they get assigned a Rightsizing ROI ticket. Available email addresses will be selected from existing Frontdoor users.

More information about this release

The functionality is available when assigning native ROI tickets. On the Rightsizing ROI page, the user can select the details button of a tracked rightsizing ROI recommendation and then select an assignee with an email address which allows for corresponding email notifications. In addition to this, the functionality is available when the user hovers over the details of the recommendation to be tracked in Rightsizing ROI and selects Create Cloudability Issue .

### AWS Resource Inventory - July 7, 2023

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

### Container Cost Allocation – Improved CPU/Memory weighting for Namespace & Label allocation - July 3, 2023

This release improves how costs are allocated to individual Namespaces and Labels, better matching how the underlying Virtual Machines are charged by the cloud vendors.

Enhancements to Container Cost Allocation

With this release, Cloudability has improved how costs are allocated to individual Namespace and Label values to better match how the underlying Virtual Machines are charged by the cloud vendors. The process of splitting and allocating the cost of each VM involves apportioning the total cost across the constituent resources (CPU, Memory, Network, etc.) and then assigning the cost to each Namespace and Label based on how much of these resources they consumed. Memory and CPU combined make up the largest component (85%) of VM costs.

Until now, Cloudability used a standard ratio to split this component regardless of VM type (skewing costs toward memory). With this release, Cloudability has made the ratio dependent on machine type – compute-optimized machines will have the ratio skewed towards CPU relative to memory-optimized machines. This has been achieved by putting prices on CPU (core hours) and memory (GB hours) based on analysis of different VM categories and how these two resource types impact VM prices. The net result is a more accurate representation of how each Namespace and Label is contributing to costs.

More information about this release

This release does not impact cluster level cost allocation. For more information, join the conversation on the Apptio Community .

### Container - Cost Allocation for EBS supported- July 3, 2023

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

### RI Portfolio and Planner support for Azure Cosmos DB - June 22, 2023

How this feature can help you

Customers can view the savings and benefits of the proposed RI purchase, and filter the recommendations based on look back period, region, scope, terms, and accounts. The Reservation Portfolio will provide Cloudability customers with their current reservation portfolio for Azure Cosmos DB instances to go along with the other services we currently provide support for.

Cloudability expands the services that Reservation Portfolio and Reserved Instance Planner support on the Azure Cloud in response to the growing number of customers who utilize Azure. By incorporating Azure Cosmos DB, Cloudability provides these customers with additional value in terms of realizing the value of purchasing reservations on the Azure Cloud. Also, the addition of Azure Cosmos DB support provides customers with actionable insights and recommendations that improve their business outcomes, all from a single pane of glass.

More information about the release

As part of this release, the Planner/Recommendation feature will now be located under the Optimize > Reserved Instance Planner menu item while the Portfolio feature will continue to be located under the Insights > Reservation Portfolio menu Item.

If not already completed, customers need to ensure that the necessary Azure credentials and permissions have been enabled to provide Cloudability with access to their data.

### Support for Kubernetes 1.26 and 1.27 Versions - June 15, 2023

How this feature can help you

This capability will enable customers to gain visibility into their container resource usages, and the cost for their clusters running on both those Kubernetes versions.

Customers should now be able to download and deploy our metrics agent using the regular provisioning workflow.

Our metrics agent has not been tested with Azure Kubernetes Service (AKS) and Google Kubernetes Engine (GKE) for 1.27 version. After Azure and GCP officially announce the support for 1.27 version, we will validate our metrics agent and update our release notes.

### Support for Red Hat OpenShift clusters on AWS (ROSA) - June 7, 2023

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

### Azure Savings Plan Portfolio and Recommendations supported - May 31, 2023

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

### Resource termination recognition supported in Rightsizing ROI – May 31, 2023

In this release, resource termination is recognized when calculating realized savings in Rightsizing ROI.

How this feature can help you

This functionality allows Cloudability users to utilize Rightsizing ROI functionality for calculating the realized savings of actioned recommendations when the action is termination of the resource. Once a rightsizing recommendation has been added via Rightsizing ROI and the resource has been terminated, the realized savings from the termination will be calculated and displayed both for the individual resource as well as added to the rolled-up total of all realized savings.

This is in addition to the support already provided for realized savings calculations when a resource is rightsized. Support will be provided for all services currently supported by Rightsizing ROI.

More information about this release

From the Cloudability primary navigation menu,

- Under the Optimize menu, select Rightsizing ROI .
- Whenever the resource was terminated, a Realized Savings amount appears at the bottom of the list of tracked rightsizing recommendations.
- Note: The Realized Savings amount will also be added to the realized savings total displayed at the top of the page.

### Idle cost distribution available for containers in Cloudability core analytics - May 19, 2023

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

### Prompt when rendering 500 or more data points in Cloudability charts - May 18, 2023

Previously, Cloudability users ran into page performance issues when they tried to render 500 or more data points in their chart visualizations. Inarguably, 500 or more data points in a single chart do not serve its purpose due to poor readability, the rendering of the same often slowed down the entire Dashboards page for our users.

How this feature can help you

Cloudability will now display a prompt when users try to render 500 or more data points in their charts, which will prevent them from running into page performance issues. At the time of chart creation, users may not be aware that they’re trying to render visualization for a high cardinality measure like Resource ID but a prompt like this would help them flag the potential risks ahead if they decide to proceed with their action. This prompt will be displayed on all the charts where the limit is exceeded and upon each time the Dashboards page is loaded in Cloudability.

More information about this release

The prompt will have two CTAs:

- Edit Query - Allows to go back to edit window and reduce the data points (to below 500).
- Graph Anyway – Users can proceed to render with the chosen number of data points.

### GPU Utilization support for AWS ASG Rightsizing - May 11, 2023

How this feature can help you

More information about this release

1. From the Cloudability primary navigation menu, Select Optimize > Rightsizing
1. Select the AWS tab, and then select AWS ASG . Rightsizing recommendations for auto scaling groups with GPUs will automatically be displayed once properly set up and available. The "details" view of the recommendation for auto scaling groups utilizing GPUs will now include additional charts for GPU (%) and GPU memory utilization, just as in the AWS EC2 rightsizing recommendations. No additional setup is required for customers who already have AWS Auto Scaling Group rightsizing recommendations and GPU utilization ingestion set up with Cloudability.

### “Max” values added to Rightsizing API and CSV export - April 18, 2023

This release announces the launch of “Throughput Max” and “IOPS Max” values to both the Rightsizing API endpoint(s) and the Rightsizing CSV export(s) for each corresponding vendor’s disk service that is supported in Rightsizing.

More information about this release

The values in the API endpoint are designated as “iopsMax” and “throughputMax”. The values in the exported CSV will contain the column names “IOPS Max” and “Throughput Max”.

### Launch of Cloudability GCP Committed Use Discount Recommendations - April 6, 2023

Cloudability now offers recommendations for GCP CUDs using its own custom engine and new analysis interface. With this new interface, customers can perform what-if analysis, and can have more control over the recommendation generated, allowing them to adjust the recommendations based on their future usage, business strategy, and factor in their risk.

How this feature can help you

Firstly, customers can filter their usage for analysis, which allows them to include or exclude usage for a more accurate analysis that represents their future usage. If a workload was running during the analysis period but should not be covered – such as a testing or development workload, then it can be removed from the analysis. Also, if a workload is being decommissioned or you are going to replace a particular type of usage such as an operating system or database software, then you can exclude that usage from the analysis. In this way, your business strategy will be aligned with more accurate recommendations for future usage.

Customers can add up to 10 Cloudability dimensions to their analysis for filtering. These dimensions can be any of the configured Tags & Labels , Account Groups , or Business Mappings .

### Support for Azure Cost Management APIs - March 30, 2023

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

### Allow Memory/GPU reducing recommendations without metrics - March 29, 2023

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

### Azure Custom Role Credentials UI Upgrade - March 15, 2023

This release showcases the Azure custom role permissions in Cloudability Credentials UI in a user-friendly way. Customers would be able to view if they have Azure custom role enabled or not under credentials details. There can be a couple scenarios on roles which are outlined below.

1. Cloudability Customers with Azure reader role and No Custom role will continue to view the Azure reader role as a green tick ( ) and the custom permissions will not be shown. Management: Reader Subscription: ReadSubscription
1. Cloudability Customers with Custom role enabled will only see the custom permissions and will not see the Azure reader role.

- In order to have only Azure custom role, customers should remove the Azure reader role and then enable the custom role.
- This is applicable to the subscription accounts and not on the billing account.

### Separation of Azure Resource Group Tags - March 2, 2023

This release adds the capability for Cloudability to differentiate between Azure Resource Group tags from Azure Resource tags so that customers can distinctly identify and manage them.

Separation of Resource Level tags and Resource Group tags

Previously, Cloudability made no distinction between a Resource Group tag and a Resource tag, both were merged and treated as Resource tags. Customers can now better track and manage their Resource Groups by creating a new business dimension for them, applying specific rules/business mappings to them etc.

Cloudability will now change the format of the tags as follows:

"cldy:Azure:ResourceGroupTag:<TagKey>" for tags generated from Resource Group level

"cldy:Azure:ResourceTag:<TagKey>" for tags generated from Resource level

This feature is not backward compatible. Resource Group tags that were discovered and treated as Resource tags in Cloudability prior to this release would remain as is.

### Container Cost Allocation – Improved CPU/Memory weighting for Namespace & Label allocation - March 1, 2023

This release improves how costs are allocated to individual Namespaces and Labels, better matching how the underlying Virtual Machines are charged by the cloud vendors.

Enhancements to Container Cost Allocation

With this release, Cloudability has improved how costs are allocated to individual Namespace and Label values to better match how the underlying Virtual Machines are charged by the cloud vendors. The process of splitting and allocating the cost of each VM involves apportioning the total cost across the constituent resources (CPU, Memory, Network, etc.) and then assigning the cost to each Namespace and Label based on how much of these resources they consumed. Memory and CPU combined make up the largest component (85%) of VM costs.

Until now, Cloudability used a standard ratio to split this component regardless of VM type (skewing costs toward memory). With this release, Cloudability has made the ratio dependent on machine type – compute-optimized machines will have the ratio skewed towards CPU relative to memory-optimized machines. This has been achieved by putting prices on CPU (core hours) and memory (GB hours) based on analysis of different VM categories and how these two resource types impact VM prices. The net result is a more accurate representation of how each Namespace and Label is contributing to costs.

More information about this release

This release does not impact cluster level cost allocation. For more information, join the conversation on the Apptio Community .

### Container Cost Allocation - Display mapped Kubernetes labels only - January 26, 2023

This release includes enhancements to display only mapped Kubernetes labels on the Container Cost Allocation page.

Enhancements to display only mapped Kubernetes labels

To improve usability and performance, the Container Cost Allocation page will now display only those label keys that have been explicitly mapped on the Tag & Label Mapping page. The Container Cost Allocation page will no longer display all historical labels.

If the Kubernetes label keys are already mapped in your Cloudability environment, then you do not need to make any changes. To add more Kubernetes labels, you can ask your Cloudability administrator to map the specific label keys on the Tags & Mapping page. Be aware that if the Kubernetes label keys are not mapped in your environment, then the Label Key dropdown will not list any keys.

Although the label keys will appear on the Container Cost Allocation page immediately after mapping, it will take 24–48 hours for the values to populate. There is no impact on Namespaces, Services, or visibility of Kubernetes constructs within Cloudability dashboard and reports associated with this release.

### Unit of Measure enhancements to Data transfer, GB Hours, and GB Months metrics - January 18, 2023

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

### Support for Kubernetes 1.25 - Container Cost Allocation - January 17, 2023

This release enables the Container Metrics agent to run and collect usage information from clusters running on Kubernetes 1.25 in Azure Kubernetes Service (AKS) environment.

Support for Container Cost Allocation on Kubernetes 1.25 in AKS

Cloudability now supports Container Cost Allocation on Kubernetes 1.25 in AKS environments. This capability will enable you to gain visibility into container resource usage and cost of clusters running on Kubernetes 1.25.

You can download and deploy the Container Metrics agent using the regular provisioning workflow. You can select Kubernetes 1.25 from the Kubernetes Version picker on the Add Cluster Data page.

The Container Metrics agent has not been tested with clusters running Kubernetes 1.25 in the Amazon Elastic Kubernetes Service (EKS) and Google Kubernetes Engine (GKE) environments. This will be done after AWS and GCP officially announce support for Kubernetes 1.25.

### Usage Family enhancements - January 17, 2023

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

---

## Cloudability Standard: What's new in 2025

<!-- sub-header -->
- **breadcrumb:** What's new in Cloudability > Cloudability Standard: What's new in 2025
- **source_path:** SSVCLNQ/release-notes-standard/whats-new-2025.html
- **original_file:** cloudability-standard-whats-new-in-2025.md
- **images:**
  - 03-media/apptio-cloudability-standard/threshold-based_alerting4.jpg
  - 03-media/apptio-cloudability-standard/wp_json1.jpg
  - 03-media/apptio-cloudability-standard/wp_json2.jpg
  - 03-media/apptio-cloudability-standard/wp_json3.jpg
  - 03-media/apptio-cloudability-standard/oci-credentialing-namespace.jpg

### Enhancements to User Management UI and Default View - December 19, 2025

This release introduces usability enhancements to User Management and Default View configuration , improving visibility and consistency for both admins and users.

- Updated User Management UI : The user edit experience has moved from a left-side panel to a new right-side panel under Users & Groups → Users . The new panel now: Displays all view types, including Hierarchical Views (HVs) and Views shared via User Groups Supports search and filtering by Selected , Unselected , or All views
- Hierarchical Views as Default Views : HVs can now be selected as default views: Admins can assign an HV as a user’s default from User Management Users can set an HV as their default view from Manage Profile → Preferences Only HVs the user has access to appear in the list; and only the highest level node which user has access to, can be set a default..
- Improved behavior when Views Are Deleted or Permissions Change If a default view (including an HV) is deleted, the user’s default will automatically revert to the Org-level default view. If no org-level default exists, the default view will be set to blank. Admins will now see a warning message when deleting views or changing permissions that may impact user defaults.

### Anomaly Alerts for Multiple Users - December 19, 2025

This release adds support for sharing anomaly alerts. Users can now include recipients directly on an alert, making it easy to notify others without requiring individual alert setup.

In addition, a new Alert Sharing tab is now available on the Alert Configuration page, providing a centralized view of all alert subscriptions.

.

### Vendor Credentials - Bulk Verify for Azure, OCI and IBM - December 19, 2025

This release adds support for bulk verify action in Vendor credentials for Azure, OCI and IBM which helps in easy onboarding of CSP accounts. With this release Bulk Actions functionality will be available to all customers having the below options.

- AWS - Bulk Save, Bulk Update, Bulk Verify
- Azure - Bulk Verify
- GCP - Bulk Save, Bulk Verify
- OCI - Bulk Verify
- IBM - Bulk Verify

### Enhanced Forecasting Beta – December 9, 2025

Try out our new Enhanced Forecast Page (Beta) that delivers more accurate, transparent, and flexible cloud spend forecasting. This new forecasting experience provides:

- Smarter forecasts powered by our new Intelligent Forecasting engine, which evaluates multiple models simultaneously and automatically selects the best fit.
- Choose your own spend drivers (up to three dimensions) to break down forecasts using the metrics that matter to you.
- Full forecast detail with grouping, filtering, sorting, and drill-down for deeper analysis.
- Greater transparency with model details, accuracy scoring, and inline visualizations for every line-item.
- More control with options to exclude unusual historical periods, view all model results and change default selection

During the initial rollout, this new page appears alongside the existing Forecast page under the Plan menu in the left navigation panel. At General Availability it will replace the current page.

### AWS - Support for CUR 2.0 Parquet format – December 9, 2025

This release adds support for AWS CUR 2.0 in parquet format which will help customers to configure either of the AWS CUR 2.0 file and compression formats.

• Text/csv – gzip

• Parquet - parquet

### Multi Cloud AI Services Dashboard – December 8, 2025

Cloudability announces the release of the Multi Cloud AI Services Dashboard, a comprehensive solution for monitoring AI and machine learning costs across AWS, Azure, and Google Cloud Platform. This new dashboard provides FinOps teams with insights into generative AI spending, enabling data-driven decisions to control costs while scaling AI initiatives.

Getting Started

The Multi Cloud AI Services Dashboard is available to all IBM Cloudability customers with connected AWS, Azure, or GCP accounts. To access the dashboard:

1. Navigate to Home > My Dashboard in the Cloudability console
1. Select Multi Cloud | AI Services Dashboard from your dashboard list
1. Use the date range selector to customize your analysis period
1. Scroll through the dashboard sections to explore cost details by service and provider

To learn more, contact your IBM Cloudability account team or Technical Account Manager.

### Vendor Credentials - Preventing data loss if user clicks outside of side panel – November 25, 2025

This release adds a modal to the vendor credentials page if the user clicks outside the side pane while filling in the credentials information.

Before this release, if the user clicks outside the side panel of Vendor credentials screen, then the screen used to go away and the data filled in the form was lost requiring the user to refill the information again.

### Cloud Sustainability - Embodied Emissions – November 14, 2025

Today we have launched inclusion of Embodied Emissions as part of Carbon Emissions reporting. This enhancement provides a more comprehensive representation of total carbon impact across your public cloud usage.

Users can now view the Carbon Emissions including both Operational and Embodied Emissions.

Before this release, users who wanted to measure their Carbon Emission could only access Operational Emissions.

With the inclusion of Embodied Emission, the “Estimated Carbon Emission” metric now reflects the total Carbon Emission which is the sum of Operational and Embodied Emissions.

### Cost Sharing for Reports and Dashboards – November 7, 2025

With this release, Cost Sharing is now available in Cloudability Reports and Dashboard Widgets. You can now visualize your cost data with allocated costs applied with a complete view of both direct and shared costs in your reports and dashboards.

- Toggle Cost Sharing per Report or Widget : Enable or disable Cost Sharing on native Cloudability reports and widgets to see how allocated costs affect your data.
- Visual indicators throughout the interface : Business dimensions with allocation rules now display allocation icons in dimension selectors, making it easy to identify which dimensions are affected by your Cost Sharing rules at a glance.
- Intelligent validation and error handling : The editor automatically manages dimension and metric compatibility.
- Seamless integration across features : Cost Sharing works consistently across Reports and Dashboards.

- Complete Cost Visibility : See the full picture of your costs including both direct expenses and costs allocated from shared resources. Flexible Analysis : Toggle between allocated and non-allocated views to understand the impact of your cost distribution rules. Prevented Errors : Automatic validation ensures your reports and widgets always use compatible combinations of dimensions, metrics, and filters. Consistent Experience : Cost Sharing works the same way across Reports and Dashboards, making it easy to build and share insights.

For more information, visit Cost Sharing for Reports and Dashboards .

### Optimization Hub in Cloudability: Centralized Insights for Commitment and Resource Optimization - November 7, 2025

Cloudability has added new functionality in the Optimization section to help users get a centralized view across their commitments and resource optimization initiatives. This dashboards show both forward looking optimization opportunities as well as backwards looking realized savings and impact of these efforts.

For complete visibility, users need access to cost data, as well as permissions to view Commitment, Rightsizing, and Rightsizing ROI data.

### Save and Share Reports in Cloudability Resource Inventory – October 31, 2025

Previously, resource inventory data can only be viewed in the UI and at best exported in CSV format – once user navigates away from the Resource Inventory module the queried data and filters would get reset. With this release, we support the capability to save a specific report with its date, service and filter selections and share this report with other users in the org by granting them “View Only” or “Edit” permissions. We also support "rolling" date functionality for the saved reports. The ability to save and share resource inventory reports would empower the creation of robust show back reports for teams to understand their consumption and informed chargeback models for internal billing.

### Option to exclude resources from recommendations and display of full region names in Cloudability Workload Planning - October 30, 2025

With this release, we have done 2 enhancements:

1. Option for admin users to specify those resource types that should not appear in the WLP recommendations for their org. This can be done using either of these 2 options: by adding the keyword so that the recommendations would skip those resource types that contain the keyword. Eg: giving the value "xlarge" would exclude all those resources that has "xlarge" in their names. by adding asterix (*) along with the keyword so that the recommendations would skip those resource types that starts with that keyword. Eg: giving the value "t4*" would exclude all those resources that starts with "t4".
1. Previously WLP showed only the region codes (eg: us-east-1). Now we show the entire region name along with their respective region codes (in parenthesis). Eg: us-east-1 will now be shown as US East N. Virginia (us-east-1). The regions are also sorted in the alphabetical order while selecting under the Common Information section

### Rightsizing ROI: Ticket Deletion and Filters – October 24, 2025

Rightsizing ROI : Allow ticket deletion and date filtering

Cloudability’s rightsizing ROI feature has been enhanced with new functionality to improve usability:

Savings Visualization : A new chart has been added to the Rightsizing ROI page which displays the 30 days savings amount in the month which it was implemented/closed. This helps users understand the impact of actions taken throughout various periods of time.

Ticket Deletion : Now Rightsizing ROI users can delete existing tickets that are no longer relevant. Users can eliminate noise for recommendations tickets that no longer apply or users want to delete and create new tickets based on updated recommendations.

Date Filtering : Users can now filter by date ranges (Created or Closed date) in the uI to focus their analysis or savings reporting on specific windows of time

Filtering and ticket deletion functionality is supported in the Cloudability UI as well as in the Rightsizing ROI API.

### Hierarchical Account Selection for GCP Commitment Recommendations – October 16, 2025

Today, we delivered an incremental feature to support our customers with multiple GCP Billing Accounts. The account picker on the GCP recommendations page is now multiselect and hierarchal. As a result, recommendations for different Billing Accounts can all be shown on a single page. All accounts is now the default selection and the Billing Account has been added to the table.

Now explicitly, the account selection on Recs is a usage picker. The recommendation is driven off of whatever spend is under the accounts selected.

For more information, visit the commitment management help documentation.

### Export reports in user-defined locale format – October 16, 2025

Today, Cloudability Reports introduced an enhancement allowing users to export the Report data in a CSV format that is consistent with their environment's selected locale format, using either a dot "." or a comma "," as a decimal separator.Locale settings can be modified on the “Currency” tab under the "Manage Profile” settings by the account administrator.

### Improved Price Transparency and Simplified Object Storage Configuration in Cloudability Workload Planning – October 14, 2025

1. We’re introducing a new calculator icon beside each pricing recommendation in Workload Planning. Clicking the icon now displays the exact formula used to calculate the pricing, helping you clearly understand the cost breakdown. This enhancement addresses previous customer feedback around reconciling price differences between Workload Planning and native cloud pricing calculators.
1. Additionally, we’ve removed the resource type selection for the Object Storage service. This selection was redundant since all configuration options for Object Storage are already displayed in the Recommendations screen. This update simplifies the experience while maintaining full visibility into cost optimization opportunities.

### FOCUS 1.1 Support in Cloudability – October 13, 2025

Starting today, customers can easily ingest any dataset in Cloudability that complies with the FOCUS v1.1 specification, in addition to FOCUS v1.0 , and gain cost visibility into the ingested spend.

There is no change to the credentialing process for the FOCUS 1.1 format and it follows the same process as FOCUS 1.0.

### Commitment Support for AWS OpenSearch Reserved Instances – October 10, 2025

Today, we delivered support for AWS OpenSearch Reserved Instances. The eighth AWS commitment type supported, OpenSearch commitments provide a discount on on-demand in exchange for a one or three year commitment to hourly usage. This commitment type is categorized as a resource-based commitment, and as such, requires selection specific usage parameters: Instance Type, Payment Option, and Region. This commitment behaves similarly to the other non-compute AWS commitment types. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

### Azure Cost Management Exports: Gzip Compression support – October 9, 2025

- Export format : CSV
- Compression : None or Gzip

This would help reduce the file size of Azure exports.

### Cost Sharing Configuration Enhancement - Automatically Allocate to New Business Dimension Values – October 2, 2025

This release introduces an improvement to how cost sharing rules handle new business dimension values in Cloudability.

You can configure your cost sharing rules and corresponding buckets as an include or exclude statement. When selecting ‘include’, you are explicitly including the business dimension values you would like to allocate to. When you select ‘exclude’, you will allocate to all business dimension values (including new business dimension values) by default, unless you choose to explicitly exclude them.

The new Exclude helps eliminate the manual work of updating each cost sharing rule whenever you add new values to your business dimensions.

### Cloudability Containers: IBM FinOps Agent – October 1, 2025

This release introduces the IBM FinOps Agent. The IBM FinOps Agent consolidates and streamlines metrics collection while introducing new capabilities in security, resiliency, and installation experience.

IBM FinOps Agent is designed to replace the legacy Metrics Agent. It will also serve as the data foundation for future feature releases.

New Features:

- Helm-based installation: Aligns with Kubernetes best practices to simplify deployment and upgrades.
- Self-managed API keys: Integrates with Frontdoor API keys, letting you create, rotate, and manage credentials to meet your security requirements.
- Improved resiliency: Disaster recovery for uploads: Uses persistent volumes to preserve collected data during restarts or service issues. Short-lived pod capture: More accurately attributes costs to transient workloads.
- Future-ready architecture: Provides the foundation for future innovations in container insight

Visit Provision your container agent to learn more.

### Commitment Support for Azure Database for PostgreSQL – September 30th, 2025

Today, we delivered support for Azure Database for PostgreSQL. The tenth Azure commitment type supported, Azure Database for PostgreSQL commitments provide a discount on compute in exchange for a one or three year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Deployment Option, Instance, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

### Commitment Support for Azure Blob Storage Reserved Capacity – September 29th, 2025

Today, we delivered support for Azure Blob Storage Reserved Capacity. The ninth Azure commitment type supported, Azure Blob Storage Reserved Capacity commitments provide a discount on capacity for block blobs and for Azure Data Lake Storage data in exchange for a one or three year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Access Tier, Redundancy, Size, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

### Usability Enhancements – Views, Users and Groups – September 29, 2025

This release provides multiple usability enhancements to Views, Users and Groups feature:

- Duplicate/Clone a View - As a View Admin, you often need to create multiple views that share similar filters and permissions. Manually recreating each view can be time-consuming and repetitive. View Admins can now use ‘Duplicate’ option to duplicate/clone views with one click—copying filters, permissions, and settings instantly. Just rename and adjust as needed. This saves time and reduces errors when creating similar views. For more information, see Duplicate a View .
- Show Default View Usage - Before deleting or restricting access to a view, Admins can now gain visibility into who is actively using it as their default. New UI option ‘Show Default Usage’ lets admins see users who have set a view as their default - whether shared directly or via groups. This will help view admins make informed decisions before deleting or restricting views. For more information, see Show Default Usage .
- Enhanced CSV Export for Views - CSV exports now include Default View Users, Groups Shared With, Owner, and Description fields. Default View Users list helps admin identify the users who are using it as a default view. These additions improve visibility and collaboration among View Admins.
- Duplicate View Name Validation - View names are now validated as you type during creation. If a name already exists, you’ll see an error and the Save button is disabled. This prevents the panel from closing and ensures you enter a unique name without losing your work.
- Edit Multiple in View Assignment UI - This fix on View’s assignment UI restores visibility of users and groups for ‘Edit Multiple’ feature. A new warning clarifies that changes apply to all selected views - preventing accidental bulk edits.
- Public APIs for User & Entra ID Groups - User Groups and Entra ID Groups now have public APIs. This enables easier integration and automation of group-related workflows. For more information, see API documentation .
- Email Visibility and Email Search in User Management - User management UI (under Settings > Users & Groups) now shows email addresses and supports email-based search. This helps admins quickly identify users, especially when names are similar. For more information, see Manage Users .

### Pivot Tables in Dashboards – September 24, 2025

Cloudability Dashboards introduces pivot table functionality. This improvement allows users to use Dimension values as columns, making it easier to analyze the metric breakdown by any dimension.

Pivot tables provide a powerful way to summarize, analyze and explore your data by using any dimension’s values as the table column. Users can easily aggregate data by category, date or any other dimension.

These tables are enabled by default for all existing Cloudability Dashboard tables. Additional control functionality, such as enabling/disabling pivots and configuring a default pivot value, will be added soon.

### Integration with Jira Cloud and ServiceNow – September 24, 2025

With this release, we introduce support for integrating Jira Cloud and ServiceNow with Anomaly Detection . This enables users to quickly create and track anomaly investigation tickets, with automatic bi-directional status updates, streamlining workflows and accelerating incident resolution.

### Support for AWS Lambda in Cloudability Resource Inventory – September 19, 2025

With this release, we introduce support for AWS Lambda service in Resource Inventory which would help customers to build an authoritative list of their AWS lambda resources. They can combine cost, utilization and other key resource level insights for their Lambda resources like Function Memory Size, Function Last Modified, Average Number of Invocations etc. that would help them take optimization actions more proactively.

### Bulk Actions on Vendor Credentialing AWS/GCP – September 18, 2025

Cloudability vendor credentials introduces bulk actions for AWS and GCP. This helps in easy onboarding of AWS and GCP accounts as users can quickly Save, Update or Verify accounts.

AWS Documentation - AWS Credentialing using Bulk Actions

GCP Documentation - GCP Credentialing using Bulk Actions

### Usability Enhancements in Cloudability Resource Inventory – September 10, 2025

This release includes 2 usability enhancements

- Enhanced Statistical Filtering - Previously, the Display Top/Bottom filters in Resource Inventory always applied to the full report, even if users had other global filters in place. With this release, the Top/Bottom selection now applies directly to the filtered dataset, ensuring users see only the most relevant resources. For example, if user has filtered a report down to 70 records from 100 (using global filters) and then selected Top 50%, they will now see the top 35 from those 70—not from the original 100.
- New KPI for Azure - we added a new KPI called Total Instances in Azure compute service that allows users to quickly filter those compute instances coming under the usage family of instance usage from other usage families like Data Transfer, Licenses etc.

### Cloudability Governance - Public Preview – September 10, 2025

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

### Deselect all dimensions in Dashboard – September 4, 2025

Cloudability Dashboards introduces an improvement that allows users to select a single Dimension from the Chart’s legend. They can focus on a single Dimensions easily, without having to discard other Dimensions from the legend individually.

### Support for OCI Managed Databases in Workload Planning – August 28, 2025

The Workload Planning users can create workload estimates for OCI Managed Database. Previously, Managed Databases service was supported for all cloud vendors except OCI. With this release, we are supporting MySQL and PostgreSQL which are the Managed Database services available for OCI today.

### Adjust Negative Values in Dashboards Charts – August 27, 2025

This release introduces an improvement that allows users to automatically scale their charts Y-axis to adjust for negative values. Previously, all charts' axes started at 0 and viewing negative values required manually configuring the static 'start scale' option. This option is enabled by default for new charts and users can still opt-out of the functionality by deselecting the 'Start scale from lowest value' checkbox. Both existing and previously configured charts will not change their behavior.

### Copy and Paste Comma-Separated List of Filters in Dashboards and Reports – August 27, 2025

This release introduces an improvement allowing users to copy and paste a comma-separated list of filters in Cloudability Dashboards and Reports.

- Copy the list of filters' values by using Ctrl+C in the values field.
- Paste a comma-separated list into the value field, using Ctrl+V, that will be automatically separated into individual values.
- Values containing the comma "," as part of the value are escaped as follows: "single\,value".

### User Groups and Entra ID Group Usability Enhancements – August 25, 2025

This release introduces more usability improvements to the User Groups and Entra ID Groups features:

- Delete confirmation for User/Entra ID Groups now displays the number of users in the group.
- Group names which are limited to 63 characters, now provides real-time validation and improved error messages.
- Sorting is enabled on all columns in the User and Entra ID Groups lists, with default sorting by Created Date (newest first)
- Default scope and hint text added to the Entra ID sync modal for better usability.
- Minor UI changes on the Users screen.

For more information about User Groups and Entra ID Groups, see Manage Users and User Groups

### Cloudability Containers: Introducing Pre & Post Visualization Filter – August 14, 2025

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

### Cloudability Containers: Introducing Metrics Agent Observability tool – August 14, 2025

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

### Enhancements to Users & Groups feature – August 13, 2025

This release introduces two improvements to the recently launched User Groups and Entra ID Groups features:

- Permission-Based Access : Previously limited to the 'Cloudability Admin' role, access to User Groups and Entra ID Groups is now aligned with existing permissions. This ensures that admins who previously had access to the User Management feature will continue to have access to Users & Groups without needing an additional role.
- Delete Entra ID Groups : You can now delete Entra ID Groups in Cloudability. This update fulfills a post-GA commitment by delivering the promised support for Entra ID Group deletion.

### FinOps Foundation FOCUS Validator in the Other Data Sources (FOCUS)– August 7, 2025

This release adds the FinOps Foundation FOCUS validator link in the credentialing screen for Other data sources (FOCUS) within Cloudability.

This would help validate the FOCUS formatted file and check for any errors before uploading the file into shared storage for data ingress.

### Supporting Kubernetes Service in Workload Planning – August 5, 2025

Workload Planning users can create workload estimates for Kubernetes service across different cloud vendors. Like Virtual Machines and Databases, you can do it for AWS, Azure, GCP and OCI. Select Kubernetes from the Service Type dropdown and provide the number of clusters to generate different pricing options. Optionally, define your specific node configuration to get the combined pricing recommendations for both clusters and VMs.

### Cloudability Containers Insights: Change in cost allocation strategy for Azure clusters – August 4, 2025

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

### Grouping of Metrics and Dimensions in Widget Edit – July 30, 2025

Cloudability introduces grouping of metrics and dimensions in the widget edit mode for easy navigation. Admins can expand and collapse the lists of measures based on the data source. This feature is available in both Dashboards and Reports.

### Cloud Spend Summary Email Enhancements – July 30, 2025

The following enhancements have been made to spend summary email content:

- Added the Cloudability environment name in the email
- Added the last updated date for the month end estimate
- Reduced the delivery time window for emails from 10 to 3 hours

### Rightsizing ROI: Fix to Realized Savings Calculation – July 25, 2025

This release fixes the issue with display of normalized realized savings value in Cloudability Rightsizing ROI.

Rightsizing ROI tickets show realized savings normalized to a 30-day period. Previously, for some manually created tickets with terminated resources, the realized savings value was only calculated for a 10-day period.

All tickets will reflect a 30-day calculation period resulting in an increase in value for your historic realized savings.

For more information, see Rightsizing ROI End Points .

### Supporting Email Alerts for Vendor Credentials Status – July 24, 2025

This release introduces email alerts for the status of accounts under Vendor Credentials in Cloudability.

- Opt-in alerts: Admins can subscribe for daily, weekly, or monthly alerts. Check whether your accounts are fully credentialed, or are incomplete or have errors.
- Actionable insights: Each email includes direct links to Cloudability with pre-applied vendor and account filters, making it easy to act where needed.

### Adding New Banners for Vendor Credentials Actions – July 24, 2025

This release adds two banners on the Vendor Credentials page which summarizes the action needed on various accounts in Cloudability. These banners, which act as quick filters, highlight the number of invalid and incomplete accounts where action is needed.

### Usability Enhancements in Workload Planning – July 16, 2025

- Provide list of all the supported resource types for bulk import
- Auto fill input parameters in Attached Storage as per the VM configuration entered
- Categorization of compute and database resource types within the resource type dropdown
- Support for email notifications when a workload has been shared

For more information, see Get Recommendations for Workload Planning

### Cloudability Premium: Disabling Turbonomic integration for customers – July 15, 2025

This release disables Turbonomic as a data source in Vendor Credentials for Cloudability Premium Customers. You can now select any period for daily automatic updates on the dashboard.

Cloudability Premium customers have unified credentialing between Cloudability and Turbonomic. They will continue to view these metrics in Turbonomic by switching over via their Frontdoor environment. For Cloudability Standard and Essentials customers, Turbonomic is still available to add as a data source in Cloudability.

For more information, see Turbonomic .

### Cloudability Dashboards: Custom rolling date changes – July 9, 2025

This release adds another option to Cloudability dashboards for configuring the rolling date ranges. You can now select any period for daily automatic updates on the dashboard.

### Cloudability Vendor Credentials: Deprecating Azure EA reporting APIs support – July 9, 2025

This release deprecates support for APIs in Cloudability vendor credentials for Microsoft Azure.

Going forward, use the cost management APIs or Azure exports for adding Azure EA accounts into Cloudability.

For more information, see Connecting with Azure EA – Cost Details API .

### User Group and Entra ID Group Support in Cloudability – July 8, 2025

This release includes support for user groups and Microsoft Entra ID Groups in Cloudability. Admins can now create user groups manually or import them from Entra ID. This helps you efficiently assign users Views based on teams, roles, or business units.

Enhancements:

- Manual user group creation: Create and manage custom user groups in Cloudability and add users to them. Once created, you can work with these groups in View assignment.
- Microsoft Entra ID Group integration : Credential your Microsoft Entra ID and import Entra ID groups to Cloudability using the custom sync criteria.

For more information, see Manage Users and User Groups and Connect Microsoft Entra ID

### Cloudability Containers: Configuration for setting up proxy on GetUploadURL– July 7, 2025

This release introduces new configuration options in the Cloudability metrics agent. This provides more flexibility to manage proxy settings for specific outbound calls by the agent.

The Cloudability metrics agent makes two outbound calls:

- The first call generates an URL.</li><li>The second call uploads the data to the S3 bucket using the URL.
- The new configuration flag CLOUDABILITY_USE_PROXY_FOR_GETTING_UPLOAD_URL_ONLY for the cloudability metrics agent when set to true applies the proxy to the first call only.

For more information, see Kubernetes Cluster Provisioning

### Cloudability Containers 1.0 deprecation – July 7, 2025

This release deprecates Container Insights 1.0. You will now be redirected to Container Insights 2.0.

Going forward, use the cost management APIs or Azure exports for adding Azure EA accounts into Cloudability.

For more information, see Cloudability Container Insights 2.0. .

### Change date ranges on Cloudability dashboards – July 1, 2025

This release includes updates to Cloudability dashboards letting you change the date range for all widgets in a report.

The global date range selector is available on all reports by default.

### Cloudability Metrics Agent 2.13.0 – Secret Management and Template Updates – July 1, 2025

This release updates Metrics Agent version 2.13.0 with the capability for CLOUDABILITY_API_KEY to align with Kubernetes best practices for secret management. This enhances the security of credentials used by the agent.

Enhancements included:

- Volume-mounted secret management : The CLOUDABILITY_API_KEY is now stored as a volume in the Metrics Agent pod replacing the previous method of setting it directly as an environment variable.
- The UI and helm provisioning support : This change is reflected in the provisioning workflow within the UI and for Helm installs from version 2.13.0 onwards. For Helm installs, decode the base64 key first. For detailed setup instructions, see https://cloudability.github.io/metrics-agent/ .
- Provisioning endpoint update : The following updates are made for the provisioning endpoint for all customers irrespective of the Metrics Agent version. API key automatically moved to Kubernetes Secret. Base64 used to encode the API key data ensuring seamless execution of kubectl apply -f <template> during provisioning.
- Configurable file path : You can now define where to store the API key using the CLOUDABILITY_API_KEY_FILEPATH environment variable for custom mount paths.

The Cloudability Metrics Agent will continue supporting the CLOUDABILITY_API_KEY as an environment variable for backward compatibility, it will advise you to transition to volume-mounted secrets.

For more information, see Kubernetes Cluster Provisioning .

### Cloudability Hierarchical Data & Views – June 30, 2025

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

### Support for Kubernetes v1.33 & OpenShift 4.18 – June 30, 2025

This release includes support for Kubernetes version 1.33 & OpenShift 4.18 for Cloudability container agent. This update allows you to maintain full container cost visibility for Kubernetes v1.33 on EKS, GKE, AKS, and OKE environments and Open Shift 4.18.

For more information, see Kubernetes Cluster Provisioning .

### Views Usability Enhancements – June 30, 2025

We launched the following key usability enhancements to Views:

- Display of owner names alongside each View for transparency, accountability and better maintenance
- Addition of a description field for each View to add contextual information about its purpose and usage for better management of outdated and redundant Views

### Shared Costs in Reporting API – June 27, 2025

This release introduces Shared Costs in Cloudability’s Reporting API. With newly added dimensions like Cost Type and Allocation Source, you can now access data around allocated costs more efficiently

For more information, see Cost Reporting End Point .

### Support for GCP Resource Inventory – June 26, 2025

This release introduces support for GCP Resource Inventory. This feature lets you report your cost, utilization, and resource level metadata for Compute and Persistent disk services in a single pane of glass view.

You can enable the Resource Inventory feature from the respective Active Admin portal depending on your geographic location. Within 3-4 business days of its enablement, you will receive complete inventory data into Cloudability.

For more information on this feature, See GCP Resource Inventory .

### Removing Label Filter Dropdown from Container Dashboard – June 25, 2025

The Label dropdown filter has been removed from the Container Cost Allocation page. The existing Label filters are automatically saved under Add Filter. Navigate to Add Filter > Dimension > Label to add same filters by Label Key and Value.

### Anomaly Detection Alert for Initial Surge​ – June 25, 2025

This release includes improvements to the anomaly detection algorithm. These improvements ensure prompt customer alerts for first-time surge spends in any service. It also includes coverage for reactivated spend anomalies.

For more information on this feature, See Anomaly Detection .

### Support for Google BigQuery in Workload Planning​ – June 25, 2025

Workload Planning users can now create workload estimates for Google BigQuery service. Select Google BigQuery in the Service Type dropdown, provide your service requirements specific to your workload, and generate different pricing options for BigQuery.

### Cloudability Dashboards Table Totals – June 17, 2025

We have added an extra row for Cloudability dashboards that includes the sum of all visible table rows to all table widgets. This behavior is enabled by default and applies to all tables. For columns containing numbers or currency, the extra row will show a sum of all visible columns. For columns containing percentages, the extra row will reevaluate the percentage calculation for the entire data set.

### Cloud Sustainability Metrics GA – June 16, 2025

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

### Adding support for GCP Tags – May 28, 2025

We have launched support for GCP tags within Cloudability.

Earlier, Cloudability supported GCP labels. With this release Cloudability supports both GCP Labels and Tags for visualizing cost throughout Cloudability.

With this release Cloudability will start ingesting GCP Tags fetched along with GCP billing data available to be configured in Cloudability’s Tags and Label page. Once configured they would be treated as another Tag Dimension and can be used like current Tags, labels, or even as part of Business mappings within Cloudability.

GCP Tags are displayed in the below format:

Key = cldy:gcp:tag:<tagkey>

### Containers: Allow "Top 10" widgets to support different limits – May 27, 2025

Users can now choose from a wider range of sorting options when adding a custom top/ bottom widget in the Container Cost Allocation dashboard. In addition to the existing 10, the widget now supports the option of top/ bottom widgets from 25 to up to 50 providing deeper flexibility and visibility into cost-driving resources. This enhancement enables you to tailor the insights to your scale and analysis requirements.

### Enhanced UI/UX in Workload Planning - May 27, 2025

1. Common information section, adding a new workload with a single glass pane view for each CSP
1. The Add Resource slide out, accommodating more input fields when provided specific resource requirements from a CSP
1. Added help info in the UI to guide users navigate through the feature
1. Simplified selection of regions by restricting it to Service Providers section in Common Information only
1. The Resource Type dropdown in Add Resource section with detailed and descriptive information. Such as the resource's full configuration ( g5.12xlarge - 48 CPUs, 192 GB RAM, 3800 GB Local Storage ) instead of just its name ( g5.12xlarge ).

### Cloudability: Enhancement to Sustainability Metrics Calculation and Expanded GPU support for Azure and OCI Compute – May 15, 2025

We have launched a couple of enhancements to Cloud Sustainability Metrics.

We have improved the calculation methodology for sustainability metrics in IBM Cloudability. As a result, customers will notice an increase in metric values going forward. These changes are due to a fix applied to the underlying calculations and will not be applied to historical months.

Additionally, we have also expanded the GPU metric support. While support already existed for AWS and GCP, this release enhances and adds support for Azure and Oracle as well.

### Cloudability Premium : Vendor Credentials Update to ON/ OFF under Automate Actions – May 14, 2025

We have launched updates to the ON/ OFF Status within Automate Actions in the Vendor Credentials page in Cloudability Premium.

- OFF was displayed if Optimization was set as Read Only .
- ON was displayed if Optimization was set as Optimize Resources .

With this release the ON/ OFF will function as follows:

- For AWS and GCP if the Automated credentialing is selected Automate Actions : ON/ OFF will follow the selection based on the parent (AWS Master Payer/ GCP Billing) account If Parent Account is ON , all the child (AWS linked accounts/ GCP projects) accounts would be ON . If Parent Account is OFF , all the child accounts would be OFF . Child accounts cannot be changed Individually when opted for Automated Credentialing.
- For AWS and GCP if the Automated credentialing is not selected Both Parent and child accounts can have different ON/ OFF status under Automate Actions . The ON/ OFF status can be changed individually without any dependency between Parent and Child.
- For Azure the status is only reflected on the subscriptions while credentialing.

### Cloudability Cost Sharing - Allocation Source in ApptioBI – May 13, 2025

Cloudability announces lineage for reporting on shared costs in ApptioBI. We have introduced a new dimension called Allocation Source in ApptioBI, enhancing visibility into shared costs configured in Cost Sharing.

Earlier, users could see only summarized shared costs, which made tracing origins challenging. The new Allocation Source dimension, available within the Cost and Usage (Allocated) projection, provides clarity by identifying the specific sources contributing to shared costs. Users can now easily contextualize shared cost data within their ApptioBI reports.

Key Features

- Trace shared costs back to their original sources clearly
- Improve understanding and transparency of cost sharing for better business insights

Limitations

Allocation Source is not supported for widgets that simultaneously include two or more business dimensions with active cost sharing. Attempting this configuration will result in an error.

Future Enhancements

Integration of Allocation Source into Reports. We are working on Dashboards and it is expected to be available in an upcoming release.

### Cloudability Premium: Vendor Credentials: Adding and reclassifying Turbonomic permissions – May 12, 2025

Today we have launched updates to the permissions required by Cloudability Premium (Cloudability and Turbonomics) to operate seamlessly with each other.

Earlier, a few permissions in AWS, Azure and GCP were either missing or needed to be reclassified in the vendor credential flows during the download of AWS, Azure and GCP scripts. This release has updated these permissions in the scripts for Cloudability Premium Vendor Credentials flows.

### Cloudability : Support for newer versions of IBM Cloud Cost files – April 30, 2025

Today we have launched updates to the ingestion of newer version of IBM Cloud cost files which allows customer to continue viewing the spend on IBM Cloud within Cloudability.

Recently IBM Cloud has upgraded the versions and formats of the cost files, the newer version being:

- Account Summary level CSV – v1.3
- Instance level CSV – v1.4

Earlier, The older version of IBM cloud cost files as supported till date will continue as usual making this change reversible.

There is no change for the credentialing steps or permissions required for IBM cloud. There are no new dimensions or metric additions with this release as well.

### Business Metrics GA – April 22, 2025

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

### Cross Region Recommendations in Workload Planning – April 21, 2025

With this release, you can select multiple preferred regions in both Common Information and Resource Type sections in, with the recommendations being shown for the resource in different regions.

Previously, the recommendations in Workload Planning were restricted only to the specific region selected by the user either in Common Information (if the user hasn't defined the exact resource type) or the specific selected region while defining the exact resource type.

### New Standard Role - Cloudability Billing Admin – April 21, 2025

Today, we introduced a new standalone role titled Cloudability Billing admin for assigning billing admin privileges in Cloudability.

Earlier to assign someone with the billing admin permission in an org, an admin was required to create a custom role with the permission named " OrgCurrencyFeatureAccess ". Going ahead, an admin would just need to assign the role called " Cloudability Billing Admin " to provide a user with the billing admin privileges. This would be a standard role available to all customer orgs across all Cloudability SKUs.

### Cost Sharing for Business Metrics – April 4, 2025

Customers can now allocated shared costs across all of their Business Metrics when using Cost Sharing.

Earlier, only supported cost sharing rules across the default cost metrics that supported. With this release, you can allocate across any currency Business Metric (except non-currency Business Metrics) that exists in your environment for more accurate allocation of shared costs in different contexts. This is available for all customers and can be seen in the Explorer page of cost sharing and ApptioBI upon selecting a metric to report on.

### Import and Export of Cost Allocation Rules – April 4, 2025

Today, we introduced import and export functionality for our cost allocation rules. Now, you can upload your cost allocation rules without having to configure them in the user interface or do this programmatically through the API.

We support the import of CSV file types for those customers who want to leverage bulk allocation rule generation. The template of the CSV can be found in the Help Center documentation .

How this feature can help you

For those who want to edit and/or add on to rules, you can now export the list of rules you currently have in a business dimension, which will provide you the list of rules that currently exist in the format needed.

In addition to import/ export for cost allocation rules, we have also released export functionality for the data that lives in the Explorer page, making it easier to export the direct and shared costs for a given set of cost allocation rules.

### Prompt for Outdated Pricing Data in Workload Planning – March 27, 2025

With this release, users will see a notification banner for workloads which are six months or older. Use Regenerate button on the banner to regenerate recommendations for those workloads with up-to-date pricing.

### Improved Navigation for Anomaly Email Notifications - March 26, 2025

Today, we introduced improvements to the Anomaly Email Notification experience, designed to simplify navigation and provide clearer insights for users.

Previously, clicking on the "View Anomaly" link in email notifications redirected users to a general anomaly detection page displaying all anomalies instead of the specific one referenced in the email. Additionally, anomalies sometimes disappeared or showed incorrect details after updated cost files were processed adding to the confusion.

With this release, both challenges are addressed to ensure a smoother and more intuitive anomaly review process.

- Direct Navigation with "View Anomaly" Link: Users are now redirected straight to the specific anomaly mentioned in the email, with its details page open for immediate review.
- Updated Cost Tooltip: If an anomaly's cost changes due to updated cost files, a tooltip will display the revised anomaly cost for better clarity.
- Disappearing Anomaly Notification: If an anomaly disappears after updated cost files are processed, a pop-up message will notify users that the anomaly no longer exists.

### Container Cost Allocation now supports Kubernetes Version 1.32 - March 19, 2025

Container Cost Allocation now supports Kubernetes Version 1.32 - March 19, 2025Today, we announce the support of Container Cost Allocation on Kubernetes version 1.32 across all providers. This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.32.

Container Cost Allocation now supports Kubernetes Version 1.32 - March 19, 2025Today, we announce the support of Container Cost Allocation on Kubernetes version 1.32 across all providers. This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.32.

### Validations on Shared View Access - March 18, 2025

In this release, we added an additional validation when Views Authors want to reduce the permissions of Shared View to Private or want to remove users’ access.

Earlier, Cloudability allowed View Authors to change the permission of shared views to Private or remove users from View access without any restrictions. As a result, the users who had previously set Shared View as Default View continued to receive alerts for that View even after the permissions were changed to Private or they were removed from the access. This occurred only when Shared View was set as Default View .

Going forward, before the View authors reduce the permission of a Shared View , they will be presented with list of users who have set the Shared View as Default View . Otherwise, the View Author would be able to change the view permission to 'Private' or able to remove user from View access without any restriction.

Change Default View to Organization's Default View for Impacted Users:

Since Cloudability allowed this earlier, users who still have Private Views as Default View continue to receive email alerts. We will fix the Default View for those users from the backend and set their Default View to the organization's Default View. This will ensure that the users will not have a "missing" or inaccessible Default View .

Additionally, impacted users can log in to Cloudability and change their Default View from the organization's Default View to another View they have access to. To set your default view:

1. Click your Profile icon and select Manage Profile
1. From your Profile page, select Preferences tab
1. Select a view from the Default Account View

### Bulk Import via Excel File for Workload Planning - March 6, 2025

Currently, Workload Planning provides support for bulk import using JSON file. With this release, will support excel file import, making it easy for excel users. Like JSON bulk import feature, you can first download the excel template and then input all your resource information as per the instructions provided in the template file. Uploading this excel file back would create all the resources as per the information provided.

### AWS and Azure Commitment Recommendations Enhanced for Accessibility - March 4, 2025

Today, Commitments released accessible AWS and Azure commitment recommendations pages. The release, while primarily aesthetic, moves the header options from the drawer to a simple menu dropdown.

### Enhanced Filtering on Anomaly Detection Page - February 26, 2025

Today, we introduced new filtering capabilities to the Anomaly Detection feature, making it easier to monitor, analyze, and act on cost abnormalities efficiently.

Anomaly detection enables organizations to identify unusual or unexpected behavior in their cost spending. It provides a cloud-agnostic, comprehensive analysis across all services to detect anomalies in cost data, helping mitigate sudden billing shocks by sending alerts and enabling users to take action.

Previously, you could only filter by Views or sort columns. Now, you can instantly narrow down results to the relevant services or accounts, and filter anomalies based on specific cost thresholds to focus on the most significant issues.

These new filters will provide:

- Expanded filtering: Filter anomalies by Account Name, Service, Usage Family, Total Cost, and Unusual Spend for a more granular view
- Threshold-based filtering: Set specific thresholds for Cost and Unusual Spend to quickly identify high-impact anomalies
- Multi-filter support: Combine multiple filters to refine results and analyze cost variations with precision

### Resource Inventory Column Support for Account Groups - February 21, 2025

With this release, resource inventory users can add account groups as a column in the UI for their inventory reports. This additional detail can be helpful when analyzing resources and categorizing them in ways relevant to the business.

### Threshold-Based Alerting - Container Insights UI - February 17, 2025

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

### Auto Populate Vendor and Region for Storage while creating a Virtual Machine resource in Workload Planning - February 14, 2025

Today, we released an enhancement to Auto Populate Vendor and Region for Storage (and make them non editable) while creating a Virtual Machine resource in Workload Planning.

Earlier, while adding a Virtual Machine resource, both Vendor and Region options used to appear for the attached Storage resource. This is not logical because the Vendor and Region for the attached Storage should be the same as the Virtual Machine. With this release we will Auto Populate Vendor and Region for Storage (and make them non editable) while creating a Virtual Machine resource in Workload Planning

### Dynamic Data Transfer Cost for Container Cost Insights - February 10, 2025

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

### Enhanced Container Insights with GCP Resource-Level Billing - February 10, 2025

Today, we announced the enhancement of our Container Insights feature to support GCP resource-level billing within Cloudability. This update marks a significant step forward in providing more granular cost visibility for our GCP customers.

Its key benefits are:

As part of this release, we are introducing a new column on the Container Insights page called the Miscellaneous Cost column. This column will reflect cluster-specific costs and will initially be available for GCP, with plans to expand support to other cloud service providers (CSPs) in the near future. These costs encompass additional expenses associated with containerized applications that extend beyond nodes, volumes, and data transfer. They include various services and resources necessary for cluster operations, providing a comprehensive view of all costs related to running containerized applications.

We do not plan to support GCP’s native GKE Cost Allocation at this moment, considering our advanced capabilities.

### Automating GCP SKU Updates and Enhanced Classification Within Reporting Dimensions - February 3, 2025

Today, we launched an update where we transitioned the process of updating the GCP SKU list from manual to automated. GCP updates the SKU list regularly and this enhancement automates the fetching of the latest SKU list in Cloudability which improves SKU classification.

Before this release, we were updating the GCP SKU list manually. This enhancement eliminates the potential for human error, significantly reducing SKU update cadence and ensuring data accuracy and consistency for GCP reporting.

Now, GCP customers can view the latest values across various dimensions in reporting while using GCP as a vendor.

With this release, we’ll also trigger a data reprocess process for all GCP customers so that their SKUs reflect the latest updates.

With this release and running the reprocess, the overall cost for a GCP customer would remain the same. However, there could be reclassification of some values within the dimensions/ reporting which might affect reports or forecasts if there are filters applied on reports.

### Cost Sharing Availability in Cloudability - January 30, 2025

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

### Workload Planning – Resource Requirements Import - January 24, 2025

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

### Ability to Add Custom Namespace While Credentialing OCI - January 20, 2025

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

### ATUM Mapping Dimensions - January 17, 2025

Today, Cloudability launched five ATUM dimensions in Reporting. These dimensions extend the TBM Taxonomy into Cloudability , enabling customers to understand cloud spend through this standardized categorization.

Five new ATUM dimensions launched are:

1. ATUM Tower : Represents a high-level IT view of your organization’s technology functions, providing a broad cost categorization. Examples values include Network, Platform, End User and Application.
1. ATUM Sub-Tower : Offers a more detailed categorization under each tower, for example breaking Platform down into Middleware and Database.
1. ATUM Service Type : Represents a high-level business view of your cloud spend. This is the top-level categorization into services with values such as Platform Services, Delivery Services and End User Services.
1. ATUM Service Category : Offers a more detailed categorization under each service type, for example breaking Delivery Services down into Operations, Security and Compliance, and Support.
1. ATUM Service Name : This is the most detailed categorization related to services, for example breaking the Operations service category down into Event Management, IT Service Management, and Deployment and Administration.

The new ATUM dimensions, aligned with the TBM taxonomy, provide more detailed cost categorization, allowing organizations to understand their technology spending at multiple levels of granularity.

These dimensions are seamlessly integrated into Cloudability Reporting and dashboards for all customers.

### Workload Planning – Azure Savings Plan Support – January 7, 2025

Today, we are providing Workload Planning users with cost estimates for Azure compute resources with the Savings Plan commitment option.

Earlier, Workload Planning only supported Azure Reservations as the default commitment type for new workloads. There is now an option to select Azure Savings Plan or Azure Reservations with one-year or three-year term and get cost estimates based on their associated savings.

---

## Cloudability: What's new in 2024

<!-- sub-header -->
- **breadcrumb:** What's new in Cloudability > Cloudability: What's new in 2024
- **source_path:** SSVCLNQ/release-notes/whats-new-2024.html
- **original_file:** cloudability-whats-new-in-2024.md
- **images:**
  - 03-media/apptio-cloudability-standard/kube_1.31.jpg
  - 03-media/apptio-cloudability-standard/pod-level_visibility.jpg
  - 03-media/apptio-cloudability-standard/ibm_cloud_billing.jpg
  - 03-media/apptio-cloudability-standard/cld_sustainability_metrics.jpg
  - 03-media/apptio-cloudability-standard/data-reprocess-1.jpg
  - 03-media/apptio-cloudability-standard/covergae-modal-commitmnet-portfolio.jpg
  - 03-media/apptio-cloudability-standard/focus-2.jpg
  - 03-media/apptio-cloudability-standard/container-cost-allocation-1.jpg
  - 03-media/apptio-cloudability-standard/container-cost-allocation-2.jpg
  - 03-media/apptio-cloudability-standard/container_1.jpg
  - 03-media/apptio-cloudability-standard/container_2.jpg
  - 03-media/apptio-cloudability-standard/workload-planning-gpu-1.jpg
  - 03-media/apptio-cloudability-standard/workload-planning-gpu-2.jpg
  - 03-media/apptio-cloudability-standard/cur-1.jpg
  - 03-media/apptio-cloudability-standard/cur-3.jpg
  - 03-media/apptio-cloudability-standard/container-kubernetes1.3.jpg
  - 03-media/apptio-cloudability-standard/vc1.jpg
  - 03-media/apptio-cloudability-standard/vc2.jpg
  - 03-media/apptio-cloudability-standard/vc3.jpg
  - 03-media/apptio-cloudability-standard/vc4.jpg
  - 03-media/apptio-cloudability-standard/vc5.jpg
  - 03-media/apptio-cloudability-standard/vc6.jpg
  - 03-media/apptio-cloudability-standard/ms_azure_edited.jpg
  - 03-media/apptio-cloudability-standard/wp_1.jpg
  - 03-media/apptio-cloudability-standard/wp_2a.jpg
  - 03-media/apptio-cloudability-standard/wp_3.jpg
  - 03-media/apptio-cloudability-standard/cca-kubernetes129.jpg
  - 03-media/apptio-cloudability-standard/oci_1.jpg
  - 03-media/apptio-cloudability-standard/oci2.jpg
  - 03-media/apptio-cloudability-standard/oci3.jpg
  - 03-media/apptio-cloudability-standard/wp11.jpg
  - 03-media/apptio-cloudability-standard/wp12.jpg
  - 03-media/apptio-cloudability-standard/wp13.jpg
  - 03-media/apptio-cloudability-standard/wp2.jpg
  - 03-media/apptio-cloudability-standard/workload-planning-oci-1.jpg

### Statistical Filtering of Resource Inventory UI – 25 December, 2024

With this release, we introduced a new option in the Resource Inventory UI (both AWS and Azure) which allows you to choose and display a subset of Resource Inventory data. From the inventory data generated for a specific service and time period, you can now choose to display a subset of that data, whether it is the top x number or the top x percentage of resources based on your preferred cost or utilization metric.

For example: Resource Inventory displays 1000 records for EC2 service for a period of seven days. You can further filter this display by choosing to view only top 25% of these resources, based on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total), sorted from highest to the lowest.

### Public API Support for Resource Inventory - 24 December, 2024

Today, we rolled out support for public API end points for both AWS and Azure Inventory data which are currently available through the Cloudability UI. This release addresses the needs of those customers who want to pull the data programmatically. Previously, these data could only be accessed from the Cloudability UI.

### vCPU Hours Metric in Cloudability - December 20, 2024

Today, we are excited to announce the expansion of the vCPU Hours metric in to include support for Google Cloud Platform (GCP). Building on the launch of this metric for AWS earlier this year, users can now gain deeper insights into their GCP resource utilization as well.

vCPU Hours metric provides enhanced visibility into resource utilization, enabling more precise cost attribution and informed capacity planning. By calculating the total running time of vCPUs across resources, it empowers you with the understanding and capability to optimize workloads effectively.

We are working to extend support for the vCPU Hours metric to Azure, Oracle Cloud Infrastructure (OCI), and IBM Cloud in 2025 and 2026.

### Commitment Support for GCP Cloud SQL CUDs - December 19, 2024

Today, we delivered support for GCP Cloud SQL CUDs.

This is the third GCP commitment type we support along with Compute Engine CUDs and Compute Engine Flex-CUDs. GCP Cloud SQL CUDs are a spend-based commitment where you commitment to a $ amount you wish to cover in exchange for a discount on on-demand prices. They work similarly to GCE CUD types in that they stack with custom negotiated pricing. Note that the Cloud SQL discount can also be negotiated and is frequently made less advantageous when large custom discounts are negotiated.

### Enhanced GCP Commitment Recommendations User Interface - December 19, 2024

Today, Cloudability introduced an enhanced user interface experience across GCP Commitment Recommendations.

The user experience was an improvement from the existing Compute CUDs implementation in the form of the Enhanced GCP Commitment Recommendations User Interface.

In addition, GCP only delivered the Compute Flex-CUDs earlier. We have included support for Resource-based Compute CUDs as well which carries a much higher savings rate in our new and enhanced user interface experience.

### Shared Cost Allocation for Kubernetes Constructs - Container Insights UI - December 18, 2024

Key Highlights

- Granular Visibility : Allocate shared costs to specific Kubernetes namespaces, providing transparency for application owners and cost centers
- New Metrics : View allocated shared costs in the UI with metrics such as Shared Cost , Network Shared , and Memory Shared among others
- Flexible Rules : Define and manage shared cost allocation rules for organization-wide or cluster-specific configurations

Start Date : Shared costs will be calculated only from the feature launch date. Queries before this date will display empty results in the Shared Cost column.

Rule Behavior :

- Rules apply to future dates (in UTC) and are not retroactive
- Updates or deletions take effect on their scheduled date
- Multiple rules work in a union relationship across namespace

For detailed configuration steps and clarifications, refer to Help Center.

### Container Cost Allocation Now Supports Kubernetes 1.31 Version - December 18, 2024

Container Cost Allocation is now officially supported on Kubernetes version 1.31 across all providers. This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.31.

### Cloudability Container Insights: Introducing Granular Pod-Level Visibility - December 17, 2024

Key Capabilities

- Granular cost tracking : Gain visibility into cost and usage metrics at pod level
- Hierarchical navigation : Seamlessly explore from Cluster → Namespace → Workloads → Pods and containers
- Detailed insights : Understand cost allocation and resource utilization with unprecedented depth

This release will surface the pod-level visibility from the date of release and will not reflect historical time periods.

### Cloudability for IBM Cloud – Cost Management (GA) - December 13, 2024

How this feature can help you

This release enables IBM Cloud customers to:

- Allocate IBM Cloud costs back to business based on specific rules, leveraging Cloudability business dimensions automatically.
- Analyze their IBM Cloud spend and improve team ownership by leveraging resource-level analytics, interactive multi-cloud dashboards, and personalized views.
- Drive financial accountability by setting up IBM Cloud budgets and event notifications.

How to manage your IBM Cloud spend

IBM Cloud customers can start their cost management journey by adding credentials for their account. Cloudability will ingest IBM Cloud data of the current month once your credentials are validated. For additional historical data ingestion, complete these steps and then reach out to the Apptio Support team. Check the API documentation for programmatic access to manage IBM Cloud credentials. Join the conversation on the Apptio Community for more information.

More information about this release

In this release, we’ve also added additional custom tags specific to IBM Cloud, which can be used as additional dimension for reporting:

- Resource Group Name: cldy:ibm:resourcegroupname
- Resource Group ID: cldy:ibm:resourcegroupid
- ClusterID: cldy:ibm:clusterid
- Plan ID: cldy:ibm:planid
- Consumer ID: cldy:ibm:consumerid
- Instance Name as ‘Resource Name’

With this GA launch, the spend managed by IBM Cloud in Cloudability will be included in your Monitored Costs, and will be subject to your contracted Monitored Cost Limit.

### Shared vendor credentials between Cloudability Premium and Turbonomic - December 10, 2024

Today, CSP (AWS, Azure and GCP) and APM (Datadog, New Relic) accounts created in Cloudability as a part of its Premium package will now be shared with Turbonomic . With this release, Cloudability Premium customers do not need to configure the same cloud accounts in Cloudability and Turbonomic tools saving significant configuration time.

Subsequent releases of Cloudability Premium build on this release to share and exchange data. Provisioning clusters flow in Cloudability is undergoing a minor change which now allows two different agent installation scripts to be downloaded – Cloudability and Turbonomic agents on the cluster being provisioned in Cloudability.

Features

Cloudability Administrators can now can request additional permissions required for Turbonomic to integrate with Cloudability. as a part of Cloudability Premium

deployment. When adding CSP accounts (AWS, Azure or GCP), additional permissions are sought that Turbonomic requires to connect the same CSP accounts as a part of billing reports (basic credentials), utilisation reports (advanced credentials) or can opt to provide additional permissions for Turbonomic to execute actions or automate them via policies.

In the case of existing Cloudability customers upgrading to Cloudability Premium , all the existing CSP accounts need to be edited, additional permissions granted and re-verified in order to have the same cloud accounts continue to collect and process data.

In the case of APM accounts (Datadog, New Relic), additional inputs need to be provided (and re-verified in case of existing Cloudability customers upgrading to Cloudability Premium ).

While provisioning clusters in Cloudability , administrators will get an option to download Cloudability and Turbonomic Kubernetes agent installation scripts. Both agents need to be running for Kubernetes cost allocation (from Cloudability ) and cost optimization recommendations (from Turbonomic ) to run seamlessly.

How this feature can help you

The same CSP accounts and APM accounts need to be configured in both Cloudability and Turbonomic for these two products to collect, ingest and process billing and utilization data from these sources. To save configuration time, we allow the CSP and APM account configuration once in Cloudability which both the products can leverage and save configuration time for the administrators. Once the accounts are configured and verified in Cloudability, these account configurations are shared with Turbonomic that allows Turbonomic probes to run seamlessly.

Similarly, while provisioning Kubernetes clusters, Cloudability administrator is presented with option to download both Cloudability and Kubernetes installation scripts with installation instructions. Once both are installed, only then both cost allocation and cost optimization features work for Kubernetes clusters in Premium deployments.

### AWS S3 Rightsizing - Glacier Instant Retrieval Storage Class Support - November 26, 2024

Today, Cloudability launched support for AWS S3 Glacier Instant Retrieval rightsizing recommendations. Customers will now start receiving rightsizing recommendations for the Glacier Instant Retrieval storage class along with the rest of the currently supported S3 classes.

Where to find the new functionality

No additional setup is required to start receiving these recommendations as long as Cloudability is correctly Connected to Amazon Web Services.

For using the new feature, follow the steps:

1. From Cloudability home, navigate to Optimize menu and select Rightsizing.
1. Select the AWS tab on the Rightsizing page and select the S3 sub-tab. Rightsizing recommendations for Glacier Instant Retrieval will be present in the list of recommendations if they exist and are not being filtered out.

How this feature can help you

Amazon S3 offers a range of storage classes you can choose from, based on the performance, data access, resiliency, and cost requirements of your workloads. In order to provide rightsizing recommendations for the lowest cost storage across different access patterns, recommendations will now be provided for the Glacier Instant Retrieval storage class in additional to the other classes currently supported by Cloudability. The Glacier Instant Retrieval storage class is typically used for archive data that needs immediate access.

### Cloud Sustainability Metrics - November 25, 2024

Where to find these metrics

These new metrics are available within Cloudability reports and dashboards and Apptio BI.

- Estimated Carbon Emissions (MTCO2e): This metric captures the estimated carbon emissions in metric tons of carbon dioxide equivalents.
- Power Consumed (kWh): This metric captures the power consumed in kilo watt hours.

These metrics are available at a resource level for the supported services.

| AWS | Azure | GCP | OCI |
| --- | --- | --- | --- |
| EC2 | Compute (non GPU) | GCE | Compute (non GPU) |
| EBS | Managed Disk | Persistent Disk |  |
| RDS | Azure Database | Cloud SQL |  |

You should be able to use this with your existing configurations of views, business mappings, account groups or tag mappings. These are also available via exports and Cloudability APIs.

Steps to use these metrics

We have configured a default dashboard within Cloudability to get started under All Dashboards called Sample Cloud Sustainability Dashboard .

For using the cloud sustainability metrics:

1. Navigate to Cloudability Home.
1. Click New report/ Add Widget.
1. Under Cloudability metrics section, scroll to Sustainability category.
1. Select metrics.

These metrics are available only to customers having Cloudability Enterprise, Cloudability Standard and Cloudability Premium SKU’s.

### Self-service Data Reprocess - November 22, 2024

This feature allows you to reprocess your data, without relying on Support or Customer Success teams. Compared to the request-based process, this feature offers faster turnaround time, eliminates manual steps, enhances transparency for user requests, and improves the overall experience.

With this release, we have also addressed a critical issue where the reprocessed data was not immediately reflected in Reports after job completion, causing delays in viewing updated information. Now, after the job is completed you can query the reprocessed data in Reports immediately. Additionally, the Job Status tab displays the job completion time and the Reason field.

During the initial rollout, we received feedback on some user experience and product gaps from customers exporting their Cloud Data from Cloudability (or via CDI) to Costing & Planning . Therefore, we decided to put this feature on hold for customers using Cloudability or CDI to Costing & Planning integration, however it will be available to customers who only have Cloudability. We are actively working on enhancing the experience and expect to launch the improved feature early next year. Cloudability customers with Costing & Planning who had access during the initial rollout will continue to retain that access

The feature is not enabled by default as this is an Opt-in feature. Reach out to Support Team to get access to the feature.

More information about the feature

The feature, when enabled, can be accessed by navigating to Organize > Data Reprocess in Cloudability

For Costing & Planning customers with Cloudability or CDI: The feature is on hold . Refer to Data Reprocess for Cloudability - Costing & Planning users .

### Enhanced Coverage Modal across GCP Commitment Portfolio - November 19, 2024

Today, we released the enhanced coverage modal across the GCP Commitment Portfolio.

This enhancement both improves the exiting coverage modal previously released on the GCP Flex-CUDs Commitment Portfolio page and extends this modal across all GCP portfolio pages. We simplified the terminology and broke out the modal into two sections. The coverage percentage calculation section includes whatever information is necessary to calculate the coverage for the specific page. The vendor coverage summary section summarizes coverage values at the vendor level for convenience.

### Apptio Community Transition to IBM TechXchange - November 1, 2024

The best practices for maximizing the IBM TechXchange experience are listed below.

- Use and bookmark this new homepage for the Apptio topic groups.
- Access the topic group that is relevant to your needs; Some of the topic groups with which you are familiar have been combined into new topic groups.

- Apptio : Costing Essentials, Costing Standard (CT-Foundation), Apptio Planning (ITP/ITFMF), Billing ( Billing Standard ), Benchmarking ( Benchmarking ), ServiceNow Integration
- Cloudability : Cloudability Financial Planning, Cloudability TotalCost, Apptio Turbonomic Integration
- https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=55a3712d-1835-4ec2-bcd7-603e88cd9dd2
- Platform : Apptio BI, ATUM, Automated Data Management, DataLink, Frontdoor, TBM Studio
- Apptio for All

- Once you are in your topic group, read and contribute to all the usual content such as quick links, discussions, questions, and blogs.
- Check out these resources on how to navigate and utilize community.
- Start submitting Requests for Enhancements on IBM Ideas . IBM uses a unified ideas portal at ideas.ibm.com for you to raise ideas against all products. As of today, that list has expanded to include the products recently acquired from Apptio. Ideas submitted prior to the acquisition will be made available to product teams and may be added to the portal at a future date to ensure continuity.

Contact the community team at our new email, support@communitysite.ibm.com with any questions or needs.

### Third-Party Vendor & FOCUS Support - October 29, 2024

Today, we launched cost management for third-party cloud vendors natively within Cloudability.

- Ingest Datadog, Databricks, Snowflake and MongoDB billing data via direct connectors and other vendors using FOCUS-compatible exports.
- Allocate these costs back to the business based on their specific rules, leveraging the tag mapping, account groups and business mapping capabilities.
- Analyze this spend and improve team ownership with interactive multi-cloud dashboards and personalized views.
- Drive financial accountability by setting up budgets and event notifications.

![Focus in TCE](../images/focus-2.jpg)

FOCUS ingress

Cloudability customers can now gain flexibility by importing costs and usage data from any data sources or additional vendors that are not yet supported via direct connectors. The billing data needs to be converted into the FOCUS format and uploaded into AWS, Azure or GCP storage accounts. Once the credentialing process is validated, customers will be able to report on this additional spend and allocate it back to the business.

Start Managing your Third-Party Vendor Spend today

You can start your cost management journey by adding credentials for your accounts following the instructions in the Help Center for Datadog , Databricks , MongoDB , Snowflake , and FOCUS ingress . By default, Cloudability will ingest the current month of data after your credentials are validated. If you would like additional months of data ingested, please reach out to the Apptio team.

### Workload Planning - Workload Templates - October 24, 2024

Today, we introduced Workload Planning Templates, which allow users to create workloads that can be easily shared as templates across their organization.

Workload Templates can be used for application customization, to promote approved configurations and resources for new applications with other users or share specific workload examples. These templates are managed by Cloudability Admin users and anyone in the organization can duplicate them so that they can be used for new application planning.

Previously, Workload Planning users could share workloads, but they were not visible across the organization by default. With this release, the FinOps teams, as well as the architect or the engineering teams can easily manage and share approved configurations within Cloudability.

Creating Workload Planning Templates

To create a template, Cloudability Admin users can simply create a workload, add the required resources, and select Save as Template in the Summary step. Users can export a template as well as duplicate it to edit the copy.

### AWS Rightsizing - "Available MBytes" memory collection support - October 23, 2024

Today Cloudability launched AWS rightsizing support for consuming memory utilization metrics via the “Available Mbytes” metric in the CloudWatch agent for AWS Windows machines.

Starting today, customers can use the Available Mbytes metric configuration to provide Cloudability with more precise memory data to use in rightsizing recommendations.

Before this release, Cloudability AWS rightsizing only supported consuming AWS memory utilization metrics for Windows machines using the “% Committed Bytes In Use” metric. Both metrics will be supported moving forward.

To enable the “Available Mbytes” memory metrics for consumption, follow these steps:

1. From Cloudability , navigate to the Optimize menu, and then select Rightsizing .
1. Select the AWS tab on the Rightsizing page which defaults to EC2 .

Available memory metrics are displayed on a graph in the details pane of the rightsizing recommendation.

AWS has multiple options available for inclusion of memory metrics in the CloudWatch agent. Although support had already been available to consume memory metrics for Windows machines using the “ % Committed Bytes In Use ” metric, some customers had already configured the “Available Mbytes” metric and therefore were not seeing memory metrics in their rightsizing recommendations. In additional to providing more flexibility for customers, “Available Mbytes” is actually a more precise memory metric because it directly represents how much RAM is free as opposed to the “ % Committed Bytes In Use ” metric that represents both physical memory and virtual memory and therefore has the potential to be the lesser accurate assessment.

### Compute Group Rightsizing – Top count reduction filtering option - October 22, 2024

Earlier, the Top Count Reduction option when selected would filter recommendations displaying an instance count reduction, if they exist, for the current instance type. The other recommendation options for an instance, if they exist, will display in the details pane as usual after the top recommendation. This allows an easy and quick way to show cost savings achieved by reducing the number of instances in a compute group without making other changes.

Where to find this new functionality

1. In the Cloudability primary navigation menu, navigate to Optimize and select Rightsizing .
1. Select the AWS or GCP tab on the Rightsizing page and navigate to the compute group sub-tab ( EC2 ASG or GCE MIG ).
1. Select the Options drop-down menu, and select Top Count Reduction to filter the recommendations.

More information about this release

There was already functionality available for customers to filter compute group recommendations so that only ones with count reductions were displayed. However, this still required more thought and effort to switch instance types when the recommendations called for it. This new feature filters recommendations to present only those instances where the instance type remains unchanged but an instance count reduction is suggested as the leading recommendation. This enables clients to swiftly identify and capitalize on "low hanging fruit" savings, which necessitate only a reduction in the compute group's instance count. These recommendations are also displayed as the top recommendation for ease of use.

### Additional OS Type Support for Virtual Machines in Workload Planning - October 21, 2024

Today, we released the support of new OS types in Workload Planning across cloud providers. With this enhancement, users can get estimates and VM recommendations based on the following 11 operating systems:

- Red Hat Enterprise Linux
- Red Hat Enterprise Linux with HA
- Red Hat Enterprise Linux with SQL Server Web
- Red Hat Enterprise Linux with SQL Server Standard
- Red Hat Enterprise Linux with SQL Server Enterprise
- Red Hat Enterprise Linux for SAP
- SUSE Linux Enterprise Server
- Windows Server with SQL Server Standard
- Windows Server with SQL Server Web
- Windows Server with SQL Server Enterprise
- Ubuntu Pro

Before this release, Workload Planning only supported Windows and Linux OS options limiting the results for Compute recommendations. With the ability to visualize VM resources across more OS types, users are now able to find more cost-effective options for their workloads comparing across multiple vendors.

### Daily Granularity Support for Resource Inventory data - October 14, 2024

Today, we introduced daily granularity support for Resource Inventory data for Cloudability. Previously, Resource Inventory supported only monthly aggregated data for all its measures (Dimensions and Metrics).

With this release, users will be able to view daily Resource Inventory data for a specific date range using the date picker in the application. (Minimum of 1 day and Maximum of 31 days per report)

### Introducing Billing Admin Permission in Cloudability - October 9, 2024

Today, we introduced a new Front Door permission called " OrgCurrencyFeatureAccess " for Cloudability. This permission allows users access the Currency tab under the managed profile.

With this permission, users can set the default currency for the organization. Currently, this permission is set from the Active Admin portal. Moving it to the Front Door will help us centralize all our permissions there.

### Introducing Cloudability in Middle East Region - September 30, 2024

How this feature can help you

This release addresses the unique needs of our Middle-East region based clients, ensuring their data remains within the regional boundaries. By localizing our services, we aim to empower organizations to bolster their compliance efforts and align with the guidelines regarding cloud cost management data.

More information about the release

The launch of hosting Cloudability in the Middle East region holds great significance for our customers operating within this region. It provides a reliable and compliant cloud cost management solution that prioritizes data residency, enhances data privacy, and aligns with data protection guidelines.

### Commitment Expiration Alerts Added for all supported Commitment Types - September 27, 2024

Today, Cloudability commitment-based discounts announces support for expiration alerts for all previously unsupported commitment types, including AWS Savings Plans , Azures Saving Plans , GCP Compute Engine CUDs , and GCP Compute Engine Flexible CUDs .

Additionally, the email template was updated to support vendor-agnostic terminology and additional fields to enhance the alert.

### Cloudability - Fine Grained Permissions for Views - September 26, 2024

Today, we are implementing two enhancements with this release.

- Adding a new permission in Front Door called ViewsFeatureCreateOwnViewsAccess that would allow a user assigned to this permission to create/update/delete views that are created by them with read only access to views created by others.
- Previously a non admin user (custom role) assigned with ViewsFeatureFullAccess was not able to edit views created by others. With this release, users with this role will be able to update/ delete any views added in their Cloudability organization.

The impact to the existing customers would be that any user role in their organization be it an admin level role or custom role with the permission ViewsFeatureFullAccess will now be able to edit or delete any Views created by anyone in their organization. If they want to constraint this access, then those users will have to be assigned with a custom role ViewsFeatureCreateOwnViewsAccess permission. If both ViewsFeatureFullAccess and ViewsFeatureCreateOwnViewsAccess are assigned to the same role, then ViewsFeatureFullAccess being the higher privilege gets precedence.

### Cloudability Container Insights: Introducing support for Dashboard sharing - September 19, 2024

Key Highlights

- Share Custom Dashboards: Users can now share their custom dashboards internally with their entire organization or specific team members, allowing for broader distribution of insights.

- Dashboard Permissions: Fine-tune access control by assigning one of the following roles: Editor: Can modify the dashboard and manage sharing permissions. Viewer: Has view-only access, with no ability to edit or share the dashboard.

- Starring and Favorites: Users can mark dashboards as favorites, making them easily accessible from a dropdown list. Starred dashboards appear at the top of the list, sorted alphabetically for quick access.

- Improved Collaboration: Facilitate seamless teamwork by enabling colleagues to contribute to shared dashboards, whether through editing or viewing. This ensures that everyone has access to the most up-to-date insights. While Viewers cannot filter or move widgets on the dashboard, they can use the "Save As Dashboard" option to create a new dashboard based on the original, allowing them to explore the data and customize it to their needs.

How to Get Started

1. Create a Dashboard: Build a custom dashboard by adding key metrics and widgets that meet your needs.

1. Share: Use the dashboard sharing option to grant access to the entire organization or specific team members, assigning appropriate roles.

1. Manage Permissions: Control and update who can view, edit, or manage the dashboard using intuitive settings.

![share dashboard containers](../images/container-cost-allocation-2.jpg)

This feature simplifies the sharing of critical container metrics, making insights more accessible and actionable across teams. By enhancing collaboration, teams can drive better decision-making and ensure everyone is aligned on key container data.

### Resource Name dimension added for GCP Resource Level Billing - September 17, 2024

What’s new in this release

This dimension represents the name that is assigned to GCP resources, such as VM instance name, disk name, or a database name. This detail matches with what users see in the GCP console when interacting with resources and aligns with the Global Resource Name column within GCP Resource Level Billing. This is the first of several releases that will serve as foundational updates to our support for commitment-based discounts.

Benefits to users

Cost attribution for resources : Users can immediately associate costs with their infrastructure.

User-friendly reports and dashboards : Users will have more clarity in reporting, removing the need to parse out unnecessary details like full API paths.

### Consolidated Commitment Portfolio and Enhancements - September 12, 2024

What’s new in this release

- Consolidated Commitment Portfolio : The "Reservation Portfolio" and "RI Planner" pages are updated to "Commitment Portfolio" and "Commitment Recommendations" respectively to reflect vendor-agnostic nomenclature. Additionally, support for spend-based commitments are now consolidated under vendor in the single portfolio page with the commitment pages reorganized together under Optimize .
- AWS & Azure Savings Plans Portfolio Enhancements : The table and KPIs are updated, and the details panel is added to match their reserved instance counterparts.
- GCP Portfolio Enhancements : “All Commitments” and “All Compute” pages are now added to convey performance at an aggregate level. Updated KPIs on the resource-based Compute CUDs portfolio page now match GCP Compute Flex CUDs. Finally, grouped and ungrouped tables convey ownership and how sharing impacts performance.

This is the first of several releases that will serve as foundational updates to our support for commitment-based discounts. For more information about commitments, see Getting started with Commitment Portfolio . Join in the discussion in our Community announcement .

### RIS Column support for Business Dimensions - September 5, 2024

With this release, resource inventory users have the ability to add business dimensions as a column in the Cloudability UI for their inventory reports.

This would help them compare their inventory data along with the business dimensions created in their organization.

### Cloudability Container Insights - Introducing the Efficiency Score (Usage) KPI - September 3, 2024

What is Efficiency Score (Usage)

Efficiency Score (Usage) is calculated by comparing the cost of actively consumed resources (usage) to the total cost of reserved resources (provisioned or allocated). This score helps teams assess how effectively reserved resources are being utilized and highlights inefficiencies such as over-provisioning, or underutilization. A higher score indicates better resource efficiency, while a lower score reveals areas for potential optimization.

This KPI is designed to provide teams with deeper insights into their resource utilization, supporting decisions around resource allocation, rightsizing, and optimization strategies.

### Cloudability for IBM Cloud – Cost Management (Beta) - August 30, 2024

How this feature can help you

This release enables IBM Cloud customers to:

- Allocate IBM Cloud costs back to business based on specific rules, leveraging Cloudability business dimensions automatically.
- Analyze their IBM Cloud spend and improve team ownership by leveraging resource-level analytics, interactive multi-cloud dashboards, and personalized views.
- Drive financial accountability by setting up IBM Cloud budgets and event notifications.

How to manage your IBM Cloud spend

IBM Cloud customers can start their cost management journey by adding credentials for their account . Cloudability will ingest IBM Cloud data of the current month once your credentials are validated. For additional data ingestion, reach out to the Apptio team. Check the API documentation for programmatic access to manage IBM Cloud credentials. Join the conversation on the Apptio Community for more information.

You will not be charged for IBM Cloud managed cloud spend during the Deta period. However, the spend managed by IBM Cloud in Cloudability will be included in your Monitored Costs post GA launch and will be subject to your contracted Monitored Cost Limit. Currently, the GA launch is scheduled for November 15, 2024 and subject to change to a later date.

### GCP Rightsizing – Detailed level billing support - August 28, 2024

With this release, Cloudability has launched support for detailed level billing in GCP Rightsizing which enables several new elements of functionality not available earlier.

Starting today, users having GCP detailed level billing enabled will notice that GCP Rightsizing now has:

- An “Effective” cost basis option for Compute recommendations
- Support for Views that are based on tag mappings, business mappings, and account groups
- Support for Filtering based on tag/business mappings
- Viewable resource tag mappings from the details pane of the recommendation
- Exports that contain resource tag mappings

Before this release, Cloudability GCP Rightsizing did not have a way to access the granular data needed in order to provide these CSP feature parity support items.

This functionality was already available for customers in the applicable areas of rightsizing for AWS and Azure but was not available for GCP. The same problems incurred with AWS and Azure rightsizing without these features are now solved here for GCP as well. Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current resource type over the reporting period. Support for Views and Filtering based on tag mappings, business mappings, and account groups provide users with the ability to create and view a more customized experience and data set. Viewable resource tag mappings allow users to see which tag mappings are associated with a resource in order to make a more informed decision on a recommendation. Exports that contain resource tag mappings also provide users with this additional information which can then be used in any capacity in which the exports are used by the customer.

How to enable GCP detailed level billing

To set up GCP detailed level billing, see Add a new account credential for Detailed Billing .

Also note that support for GCP detailed level billing does not currently include GKE cluster cost data.

Where to find this new functionality

1. From Cloudability primary navigation menu, navigate to the Optimize menu item and select Rightsizing .
1. Select the GCP tab on the Rightsizing page. Additional functionality provided in this release will be available here.

### UI Enhancements for Resource Inventory - August 26, 2024

With this release, we have standardized the Resource Inventory UI specific to the elements as part of the overall platform standardization and accessibility compliance.

These elements are as below.

1. Display style of the AWS and Azure tabs at the top to be consistent with other modules in Cloudability.
1. Display style of service and month dropdown and the placeholder texts to be consistent with other modules in Cloudability.
1. Font size and thickness.
1. Size and display style of the export and measures icons on the top right of the Inventory grid.
1. Data loading experience.
1. Display style for the Show / Hide measures (dimensions /metrics) icons.

### Cloudability Container Insights 2.0 Enhancements - August 16, 2024

Global Filter for Label Key/ Value Pairs

We’ve introduced a new global filter option within the Container Insights UI dashboard, allowing you to filter your cost and usage data based on specific label key/ value pairs. This enhancement offers a more detailed view of your containerized workloads by enabling filtering according to labels such as app, env, or any other custom labels you use within your environments.

Key Features

- Label Key filter: Select from available label keys to narrow down your cost data view to specific workloads or environments.
- Label Value filter: Refine your filter further by specifying label values, providing precise cost allocation insights.

To use this feature, you must provide at least one label value for filtering. You can also select multiple values to suit your needs. Our goal is to empower you to leverage the labels within your environments to build intuitive dashboards, enabling deeper insights into your container costs.

Customizable Table Widgets

Building on our existing capabilities for custom KPI and chart widgets, we've now introduced custom table widgets within the Container Cost Allocation dashboard, enhancing your ability to tailor cost visibility to your specific needs.

This feature allows you to modify and configure table widgets to present data that best suits your use cases.

Key Features:

- Table Selection: Display cost and usage data by Cluster, Label, Node, or Namespace, providing flexibility in how you view and manage your Kubernetes resources.
- Filter Conditions: Customize your table by applying filters based on various measures such as Cluster, Namespace, Workload, Container, Node, or specific labels like app, env, project, and more. This helps you focus on the most relevant data for your analysis.
- Edit Widget Functionality: Edit existing table widgets easily to adjust the displayed data or filter criteria, ensuring your dashboard reflects the most up-to-date and relevant information.
- Export Options: After customizing your widget, you can export the data for further analysis or reporting.

### Workload Planning – GPU support for Virtual Machines - July 16, 2024

Before this release, Workload Planning only supported few GPU instances across vendors and did not offer visibility into GPU-specific requirements. Users are now not only able to compare costs across vendors, but also visualize configuration details such as the number of GPU s, GPU Memory and GPU Model (where provided by cloud service providers) helping them find the most cost-effective GPU resource for their workloads.

### Support for AWS Cost and Usage report (CUR) 2.0 - July 16, 2024

This enhances the data format supported for AWS Cost and Usage reporting with a couple of options now:

- AWS Legacy CUR
- AWS Standard Data export/ CUR 2.0

Before this release, Cloudability used to support only AWS CUR export which is now renamed as Legacy CUR export by AWS.

Existing customers on AWS legacy CUR can continue with the legacy CUR without any impact on the data ingestion or availability of data within Cloudability.

How to enable it

Customers would need to configure the CUR 2.0/ Standard Data export in the AWS Console.

Customer should configure the below in AWS Console:

- Standard Data export

- CUR 2.0 Include Resource ID s Time Granularity as Hourly Column selection - All (All columns will be selected by default) Compression type and file format gzip - text/ csv File Versioning as Overwrite existing data export file

Once the above settings are specified, follow the steps below in Cloudability

1. Navigate to Settings > Vendor Credentials > AWS .
1. Select and edit the Master Payer account.
1. Add the New S3 bucket name , Cost and Usage report prefix , Cost and Usage report name in Cloudability.
1. Save and download the CFT template.
1. Run the CFT template.
1. Verify Credentials.

### GCP Custom Virtual Machine type support (Windows OS) for Workload Planning - July 11, 2024

Today, we are pleased to announce the introduction of cost estimates for GCP custom VMs with “Windows" OS in Workload Planning , supporting the N4, N2, N2D, E2 and N1 machine types.

This is an extension of the GCP Custom Virtual Machine Type Support release, announced on June 14, 2024.

### View Only Permissions for Budgets module in Cloudability - July 11, 2024

Today, we are pleased to introduce a new user permission in Front Door called BudgetsFeatureViewOnlyAccess which allow users (who are assigned this permission) to view and subscribe to budgets created in their org.

This permission does not allow users to create new budgets or modify ( Edit / Delete ) existing budgets.

### Cloudability Container Insights 2.0 - July 11, 2024

The new UI is the default landing page for the Container Insights feature. However, you can easily toggle between two experiences by clicking the button referenced in the screenshots below.

We are not deprecating the Container Insights 1.0 immediately. You will have the option to toggle between the two versions for a certain period to allow you get comfortable with the new interface. We will provide proactive communication about the future deprecation date for Container Insights 1.0.

Features Introduced

1. Customizable Dashboards We've added customizable dashboards, that will allow you to create visualizations, and monitor key performance indicators (KPIs) that matter to you. Capabilities included: Default Dashboard: Includes pre-configured widgets for quick insights into total cluster cost, idle cost, and other essential metrics. Each user has its own default dashboard. Efficiency Score: A new metric to assess resource allocation efficiency. Enhanced Visualization: Includes KPIs, trendlines, top X widgets, timeseries charts, and table widgets for a comprehensive view of your container footprint. Customization Features: Cloud vendor filter support for dashboard-level filtering Multi-select functionality for cluster selection This release supports custom dashboard creation, along with various custom widgets types. You can also delete and add custom widgets in the default dashboard, and set them as your custom dashboards.
1. Treemap View The Treemap View provides a hierarchical visualization for clusters, enabling deeper analysis down to the container level: Hierarchical Visualization: Allows drilling down from clusters to namespaces, workloads and containers. Efficiency Score Visualization: Integrates efficiency scores within the Treemap view for quick assessments. Both Dashboards and the Treemap View support global filters for date, clusters, and cost basis. Widgets are organized with KPIs at the top and tables at the bottom for optimal visibility. Detailed Drill-Down Capability Our enhanced drill-down functionality allows seamless navigation: From the dashboard, navigate to the table widget, and select a cluster to view its namespaces in the Treemap View. Select a namespace in a Treemap to explore constituent workloads. Clicking a workload reveals the containers within that workload. At each level of granularity, you can understand the different cost components, and efficiency score. Additional Information For in-depth container details within a workload: Click a container to view the nodes it is operating on. Updates to the details panel provide relevant information for each container grouping, ensuring you have access to the most logical details. New Cost Column: Miscellaneous Cost As part of this release, we are introducing a new column on the Container Insights page called the 'Miscellaneous Cost' column, available in the Table widget. This column will reflect cluster-specific costs, and will initially be null for all Cloud Service Providers (CSPs). We will make this available for GCP first, with plans to expand support to other CSPs in the near future. These costs encompass additional expenses associated with containerized applications that extend beyond nodes, volumes, and data transfer. They include various services and resources necessary for cluster operations, providing a comprehensive view of all costs related to running containerized applications.
1. Cost Efficiency Score The Cost Efficiency Score is a KPI that measures the overall cost-effectiveness of resource allocation within a containerized environment. It compares the utilized cost against what is deemed the fair share or total cost. Understanding this score involves examining three main types of costs: fair share cost, utilization cost, and idle cost. Fair Share Cost / Total Cost Fair share cost represents the proportion of the total node cost attributed to a container based on its allocated percentage of each resource (CPU, Memory, GPU). This is calculated by multiplying the node cost for each resource by the fair share percentage of that resource allocated to the container. The total fair share cost for a container is the sum of these amounts for all resources. Utilization Cost Utilization cost reflects the actual cost of resources used by a container. It is calculated by multiplying the node cost of each resource by the utilization percentage of that resource on the node. Like fair share cost, the total utilization cost for a container is the aggregate of utilization costs for all resources. Idle Cost Idle cost is derived by subtracting the utilization cost from the fair share cost. It represents the cost of resources that are allocated but not utilized, indicating inefficiency. Cost Efficiency Score Calculation The Cost Efficiency Score is calculated by comparing utilized cost to fair share cost, encapsulating the efficiency of resource usage across all resources within a container, namespace, workload, or cluster. This score helps identify inefficiencies and potential areas for optimization, such as cluster or node rightsizing or improving workload pod affinity constraints. A lower Cost Efficiency Score indicates greater inefficiency, suggesting more significant opportunities for cost savings and optimization within the environment.

Please reach out to support if you have questions around this feature or feedback.

### Container Cost Allocation now supports Kubernetes Version 1.30 - July 8, 2024

Today, we are pleased to announce that Container Cost Allocation is now officially supported on Kubernetes Version 1.30 across all providers.

This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes 1.30.

![CCA X Kuberenetes](../images/container-kubernetes1.3.jpg)

### Expansion of Tag and Label Mappings - July 4, 2024

We’ve increased the number of available tag and label mappings in Cloudability by 20.

This means customers can now have up to 50 reporting dimensions in the platform that are specific to mapped tags or labels. This will particularly help customers who are multi-cloud, and have many tag or label keys in their environment. Cloudability administrators can add these additional mappings in the “Tag & Label Mapping” feature.

### Taggable Resources Enhancement - July 4, 2024

Today, we have introduced a significant enhancement for taggable resources in Cloudability. Historically, Tag Explorer broadly defined "taggable spend" as any cost item that had a Resource ID. This led to some cost items being categorized as taggable even though the underlying usage was untaggable. With this release, Tag Explorer now has in-built awareness on which specific AWS and Azure services support tagging, leading to accurate categorization for the Taggable Spend and Untaggable Spend tabs.

If you would like to have this applied for any previous months to support historical tag analysis, please request a reprocess from your customer success team.

### Workload Planning – OCI Burstable VM support - July 1, 2024

What's new in this release

Earlier, Workload Planning was providing recommendations for Virtual Machines, without the option to select burstable instances, which was available in the OCI Cost Estimator. With this release, users can now choose a baseline CPU utilization of either 12.5% or 50% for burstable instances, representing a fraction of each CPU core. The baseline indicates the minimum CPUs that can be utilized continuously.

For each baseline, Workload Planning provides the associated cost estimate: opting for a baseline of 12.5% offers up to 87.5% in savings, while a baseline of 50% provides up to 50% in savings.

There are four types of OCI Virtual Machines that support burstable configurations: VM.Standard3.Flex , VM.Standard.E3.Flex , VM.Standard.E4.Flex , and VM.Standard.E5.Flex .

Important Update

We recently released support for the launch dates for a few services in Resource Inventory (EBS snapshots, RDS instances, S3 buckets, Redshift snapshots). However, with the launch date of EBS snapshot, we have run into a performance issue in Cloudability 's cost pipeline owing to which we have decided to roll back the launch dates of EBS snapshots in Resource Inventory. We shall re-launch this capability once we have an alternative stable solution available. Please note that the launch dates of services other than EBS snapshots will still be available for consumption.

### Resource Inventory support for Views created with Business Dimensions - June 26, 2024

Today, we launched Resource Inventory support for views created using business dimensions.

More information about this release

As such, we would also remove the existing privileged access to Resource Inventory through the Front Door permission called AWSResourceInventoryFullAccess and enable this feature for all users in the customer org because the admin user can now define data boundaries for resource inventory data via views.

Also, we have now removed the privileged permission in Front Door that is tied to Resource Inventory feature ( AWSResourceInventoryFullAccess ). This would make the feature available to all users within an org irrespective of any permission entitlement, similar to modules like Reports, True Cost Explorer etc.

As such, we would also remove the existing privileged access to Resource Inventory through the Front Door permission called AWSResourceInventoryFullAccess and enable this feature for all users in the customer org because the admin user can now define data boundaries for resource inventory data via views.

We have now removed the privileged permission in Front Door that is tied to Resource Inventory feature ( AWSResourceInventoryFullAccess ). This would make the feature available to all users within an org irrespective of any permission entitlement, similar to modules like Reports, True Cost Explorer etc.

### Enhanced Vendor Credentials User Experience - June 24, 2024

What's new in this release

With this release, you can:

- Quickly identify the datasources available in Cloudability.
- Have a UI which is scalable, considering current integrations and future expansions.
- Have access to an Accessibility compliant A11y UI.
- Experience better performance on the Vendor Credentials UI loading times.
- Use new filtering and search capabilities on individual Vendor Credentials columns.
- Expand and collapse all accounts at a master payer/billing account level.
- Sort the details based on individual columns.
- Have better readability as we have improved the contrast ratios.

1. In Cloudability , navigate to Settings > Vendor Credentials .
1. To add a new data source, click Add Datasource . This will show all the data sources available to a customer.
1. Select a datasource you would like to credential.
1. Now, the Add account while credentialing overlay is displayed from the right-hand side.
1. Once credentialed, you will be able to view a Tab for the datasource. Note: The credentialing steps for each datasource remains the same.
1. Within the Tab, you will be able to Search and Filter on individual columns.
1. Click “…” to perform various actions as before. We have added text along with the icons: View Details Edit Account Re-verify Account Archive Delete
1. The parent accounts (master payer and billing accounts among others) will collapse by default. Click individual accounts to view the next level of sub accounts (linked accounts and subscriptions or projects among others) or use the newly introduced Expand all/Collapse all icons.
1. The Vendor Credentials UI now supports lazy loading providing better performance on UI load times.

### Custom Virtual Machine Type Support for Workload Planning – June 14, 2024

What's new in this release

Earlier, Workload Planning was only supporting predefined machine types for GCP, which have a preset number of vCPUs and amount of memory, and are charged at a set price. With this release, Workload Planning provides recommendations for standard and custom VMs, based on the vCPU and memory input. It allows you to choose the processing power and amount of memory without changing machine types. If a combination of vCPU and memory doesn’t exist, Workload Planning will prioritize the vCPU requirement, and look for the nearest memory amount.

This release only supports the “Free” OS, listed as “Linux” in Workload Planning , while the custom VMs with “Windows” OS will be supported in the future release.

### RIS Support of Launch Date Dimension for More Services - June 14, 2024

With this release, Resource Inventory would support launch date dimension for the following AWS services:

1. EBS Snapshots
1. RDS Instances
1. Redshift Snapshots
1. S3 Buckets s3:ListAllMyBuckets redshift:DescribeClusterSnapshots

More information about this release

The existing Cloudability users need to add these two new permissions to get the launch date dimensions for S3 and Redshift:

It is recommended to assign these permissions to Cloudability IAM role via your AWS console by navigating to IAM > Access Management > Roles > Cloudability Role (or your customized role created for Cloudability ) and assign the above two permissions to Cloudability MonitorResourcesPolicy under the Permissions tab.

For new users, these permissions would already be included in the AWS credentialing script.

### Fine Grained View Only Permissions for Organize and Budgets Modules in Cloudability - June 14, 2024

What's new in this release

The three new permissions are:

| Permission Name | Description |
| --- | --- |
| AccountGroupManagementFeatureViewOnlyAccess | Enable users, assigned to a role with this permission, to view accounts and account groups under Cloudability "Account Groups" feature menu item but cannot edit them |
| BusinessMappingsFeatureViewOnlyAccess | Enable users, assigned to a role with this permission, to view business mappings and their definitions under Cloudability "Business Mappings" feature menu item, but cannot edit them |
| TagsAndLabelsFeatureViewOnlyAccess | Enable users assigned to a role with this permission to view all Cloudability dimensions and their mapped tag keys , and Kubernetes labels under Cloudability "Tags" feature menu item, but cannot edit them |

### Export Columns Displayed in Resource Inventory UI – June 13, 2024

With this release, you will have an additional export option (at the top right of the inventory grid) along with exporting full inventory data, where you can export the inventory data for only those columns displayed in the UI. Previously, it was not possible to have an export (to CSV) of only the selected columns in the resource inventory UI.

### Rightsizing Preferences – Storage/S3 Class Exclusion Support – May 30, 2024

What's new in this release

Before this release, Cloudability only provided class filtering for object storage rightsizing recommendations at the page level and only for the top recommendations given, with no way to filter globally or on an individual recommendation basis.

Starting today, you can quickly and easily start filtering rightsizing recommendations for object storage/S3 at a global level to hide recommendations for unwanted object storage classes.

To enable this feature, follow the steps below:

1. Starting from the Cloudability primary navigation menu, navigate to the Settings menu item, and select Rightsizing Preferences .
1. Select the Object storage Preferences tab on the page, and check “Exclude recommendations where the recommended storage class contains the following values”.
1. Under this option, there will be text boxes where you can enter additional values which will then exclude any object storage recommendations where the class contains these values. Note: Changes to these settings may take up to 24 hours to take effect.

### Cloudability Usage Family Enhancements – May 28, 2024

This change will lead to a reduction in the amount of unmapped line items (mapped as 'Other'), address previously identified inaccuracies, and improve existing mappings. Additionally, more services across all CSPs are now mapped. Changes reflect for cost line items from May 1, 2024, and automatically for any reprocessed months.

Below are examples of what could change as a result:

- You might see Usage family API Request change to IO for some services such as AWS Sagemaker. The change mostly affects read/write operations.
- Specific to AWS, you might see changes from IO to Data Transfer. This is to align with the underlying units (BytesTransferred) for which you are charged.

### Usability Enhancements to Tags and Labels Page – May 23, 2024

With this release, we launched two enhancements:

1. Earlier, when you searched, and added a particular tag key to a Cloudability dimension, the search text and the search results used to disappear, making it difficult to multi select a bunch of tag keys from the same search text. Now, you can retain the search text, and search results even after adding a tag key.
1. Earlier, Tag key names with long strings were getting cut off making it challenging to read its full name. Now, we have adjusted the row height to display the full tag key name, and also added a tool tip to read it better.

### Addition of New KPIs for Total Resources and Total Snapshots for EC2 in Resource Inventory – May 17, 2024

With this release, Resource Inventory will support two new KPIs for EC2 which will provide you with more fine-grained data visibility. They are:

1. Total Resources (total number of EC2 resources that includes both EC2 instances and snapshots)
1. Total Snapshots (total number of EC2 snapshots).

### Custom Pricing Support for GCP Compute Spend CUDs – May 17, 2024

What's new in this release

The toggle button between custom pricing and retail pricing is now available enabling easy switching between the two as and when needed.

To enable this feature, follow the steps below:

1. Navigate to Cloudability > Optimize > Reserved Instance Planner > GCP > Commitment Type = Compute Engine Flexible-CUDs
1. Navigate to Cloudability > Insights > Reservation Portfolio > GCP > Commitment Type = Compute Engine Flexible-CUDs Or, Toggle the Cost Basis picker between Retail and Custom .

More information about this release:

This new feature adds more flexibility to calculate and estimate cloud spending costs using concepts of Cloudability with the added advantage of deciding beforehand which pricing model suits you best.

### Normalizing Inconsistent Azure Region Names - May 17, 2024

Earlier, customers experienced inconsistencies where the same Azure regions had different names (For example, "EastUS" and "US East" for the same region). This release will resolve and prevent the need for additional mapping tables to be created on the customer’s end. This will normalize Azure region names that will provide customers with the required granularity for reporting.

For example: Following this change, instead of returning "Hong Kong" or "HongKong (East Asia)" as the region, the report would return EastAsia::Eastasia.

### Snooze/ Ignore Rightsizing Recommendations in Cloudability – May 14, 2024

Today, we launched a new rightsizing feature that allows you to hide (snooze) rightsizing recommendations for specific resources for a customizable period. Starting today, you can snooze specific rightsizing recommendations to enhance efficiency while reviewing, and actioning rightsizing recommendations.

This feature enhances efficiency by reducing the number of desired recommendations provided, as well as by removing any confusion associated with continuing to display recommendations that have already been determined as non-actionable for the time being.

Steps to enable Snooze Rightsizing Recommendations

1. Go to Cloudability primary navigation menu, navigate to the Optimize menu item, and select Rightsizing .
1. Select the desired Rightsizing vendor and service page.

### OCI - Supporting instance type, instance category and instance family – May 11, 2024

Prior to this release, you would rely on “item description” dimension to report on OCI instances. However, this approach posed challenges in generating reports seamlessly and identifying cost spikes easily. With this release, you can now leverage these 3 new dimensions to report on your OCI spend, as well as better understand and categorize compute instances.

This enhancement will require you to reprocess data to ensure that the new dimensions are applied accurately to your past records.

### Azure MCA - Azure Cost Management APIs Support – May 9, 2024

This release brings in the support for the Azure Cost Management APIs in Cloudability Credentials for Azure MCA customers in addition to using Azure exports. You can now utilize these APIs in Cloudability to get both actual and amortized cost, using the Cost Management APIs.

Steps to credential an Azure MCA account using Azure Cost Management APIs

1. Go to Cloudability credentialing page, and select Azure.
1. Click Add Credential.
1. Select Microsoft Customer Agreement (MCA) as Azure account type.
1. Enter Azure Billing Account ID , Azure Tenant ID , and Subscription ID .
1. Enter NA in other fields.
1. Click Generate Setup Script .
1. Download and install PowerShell script in Azure.
1. Click Verify Credential in Cloudability UI. The green tick indicates that the Account addition using Azure Cost Management APIs was successful.

For the existing MCA customers with azure exports using azure storage, nothing needs to be done. In case of azure exports using azure storage, we‘ll continue fetching the Azure Cost Management files from the configured location.

### Workload Planning GA – May 7, 2024

How this feature can help you

With this GA release, Cloudability Admins gain enhanced control over Workload Planning’s recommendations through the introduction of new Workload Planning Preferences. Here, Admins can set default options for workload lease type (for example: On Demand, Spot), commitments, and input more discounts or uplifts. Additionally, Workload Planning permissions have been improved, enabling Cloudability Admins to oversee workloads created by users across their organization, promoting transparency and facilitating seamless information sharing among teams.

Cloudability Workload Planning represents an industry-first capability, which allows users to define cost-effective workloads with all necessary resources while considering deployment options across multiple cloud providers. This fosters greater efficiency and alignment between financial, and technical teams.

Workload Planning Preferences

These new controls introduced as a part of GA are accessible to Cloudability Admins by default. It empowers FinOps teams to centrally define, and restrict options for Workload Planning . Any of these settings are optional, and not required to use Workload Planning .

1. Go to Cloudability Settings > Workload Planning Preferences.
1. Remove the availability of a specific CSP by leveraging the Allow Service Provider option.
1. Define lease type preferences and commitment default options for your users. You also have the option to lock the commitment selection for users.
1. Incorporate any additional discount/uplift to your workload costs. Note that this is added on top of any custom pricing, which is already factored in Workload Planning .
1. Click Save to apply the change(s) immediately. The updated preferences will impact the existing and new workloads. Workload Planning Permissions Cloudability Admins have access to Workload Planning and Workload Planning Preferences via their WorkloadPlacementFullAccess permission. They can create and manage their workloads, view workloads created by all users from their organization (without editing right), and update Workload Planning Preferences. They can edit others’ workloads when they are directly shared with them with editing rights. Non-admins can create and edit their own workloads by default through WorkloadPlanningFeatureCanAccess permission. They can also view and possibly edit the workloads shared with them, depending on the permission granted by the workload owner. We have created an additional permission: WorkloadPlanningPreferencesViewOnly . It can be added to a custom role to view Workload Planning Preferences, which will help users understand the feature setup better. Custom Pricing Support Workload Planning always shows costs inclusive of any custom pricing (e.g., for EDP) for AWS, Azure and OCI. If organizations don’t have a custom pricing agreement with a specific vendor, then we default to “retail” pricing. For GCP, you can enable the export of custom pricing data from their GCP billing account to get custom pricing in Workload Planning . More about this release Visit Get Recommendations for Workload Planning , and Workload Planning Preferences for more information or join the discussion on Apptio Community .

### Minimum Usage Adjustment Method for GCP Compute Flex-CUDs – May 6, 2024

Today, we released a new commitment recommendation adjustment method for GCP Compute Flex-CUDs, Minimum Usage. With this release, you can adjust the recommendation to the spend on the minimum usage hour. This includes the ability to exclude the lowest 1 and 5 percentile of usage hours.

### Support for Azure Cost Management Data Exports to Azure Storage with File Partitioning – May 6, 2024

Starting today, Cloudability will support Azure Cost Management Data exports to azure storage with partitioning enabled for Azure customers. This would be applicable for both types of exports:

- Cost and usage details (actual)
- Cost and usage details (amortized) How this feature can help you Recently, Azure has upgraded the azure storage experience for customers and made the partitioning on export(s) as default which splits the exported file into multiple files, based on the size of dataset. Before this release, Cloudability didn't support cost management export files with partition which caused issues on data ingestion for Azure customers on newly created exports. This is no longer an issue as Cloudability has brought in support for Azure files with partition enabled. Note: This is a backend change and does not involve any changes or updates on the Cloudability UI. Azure cost ingestion for the customers with older exports will continue without them making any changes. Note: Customers who had enabled file partitioning while creating cost management exports should create a new export before adding credential in Cloudability.

### Rightsizing Recommendations for AWS Lambda functions in Cloudability – April 19, 2024

Before this release, rightsizing recommendations for AWS Lambda functions were not available in Cloudability. Providing these recommendations directly within Cloudability provides users with a more extensive, independent recommendation source to further optimize their AWS spends.

How to enable Rightsizing Recommendations for AWS Lambda

To enable this feature, follow the steps below:

1. Enable Lambda Insights enhanced monitoring to allow Cloudability to retrieve memory metrics for your lambda functions.
1. Create or download the updated AWS credential template in Cloudability and then upload the new credential template to the AWS Management Console.
1. From the Cloudability primary navigation menu, navigate to the Optimize menu item, and select Rightsizing .
1. Select the AWS tab on the Rightsizing page, and under the available AWS services select the Lambda tab. Any existing Lambda rightsizing recommendations will be displayed here.

These recommendations, as well as their underlying data, will now be available in all areas of Cloudability where rightsizing data for other AWS services is surfaced.

### Categorization of Dimensions and Metrics in Resource Inventory UI – April 3, 2024

We have added headers in the Table Settings (left slide out nav) in Resource Inventory UI that will separate out the dimensions and metrics into two different sections.

With this release, dimensions would appear at the top, while metrics at the bottom when scrolled down in the Table Settings.

### Introducing Cloudability in APAC Region – April 2, 2024

How this feature can help you

This release addresses the unique needs of our APAC-based clients, ensuring their data remains within the APAC boundaries. By localizing our services, we aim to empower organizations to bolster their compliance efforts and align with the guidelines regarding cloud cost management data.

More information about the release

The launch of hosting Cloudability in the APAC region holds great significance for our customers operating within this region. It provides a reliable and compliant cloud cost management solution that prioritizes data residency, enhances data privacy, and aligns with data protection guidelines.

Customers, based in the APAC region, interested in migrating from the US to the APAC region can reach out to their respective Account managers or Customer Success team.

No additional setup or installation is required for customers who are directly onboarding to Cloudability in the APAC.

### Commitment-based Discount Support for GCP Compute Engine Flexible Committed Use Discounts – March 28, 2024

Starting today, users gain access to two new pages:

- From the Commitment Portfolio page, users can gain performance insights, set expiration alerts, and manage their portfolio of Flexible CUDs.

- From the Commitment Recommendations page, users can receive and adjust optimal recommendations to evaluate future commitment purchases.

How this feature can help you

With this release, we have reconfigured and introduced a new set of KPI’s and commitment meta data across the portfolio and recommendations pages. This information will help you better manage and understand the performance of your current commitments. For customers who are undercommented due to uncertainty in applying financial risk to commitment decisions, our enhancements to the Commitment Recommendations page will give you confidence to make more aggressive commitments to increase net savings.

More information about the release

Over the upcoming releases, we will continue to build out additional functionality to assist you in understanding the tradeoffs between different commitment terms, types, and strategies. We will reorganize the information architecture across the Commitment-based Discount functionality and we will look to support the majority of GCP spend-based commitment types.

The Reservation Portfolio and Reserved Instance Planner pages will become the Commitment Portfolio and Commitment Recommendations pages and be reorganized alongside each other under Optimize soon.

### Container Cost Allocation for Kubernetes Version 1.29 – March 26, 2024

Container Cost Allocation is now officially supported on Kubernetes version 1.29 across all providers.

This feature allows customers to gain detailed insights into their container resource usage and associated costs for clusters running on Kubernetes Version 1.29.

### OCI Support in Workload Planning – Enhancements – March 26, 2024

Today, we released two enhancements to the 'OCI support in Workload Planning' feature:

• You can now select 'Capacity Reservation' pricing for your OCI Virtual Machines.

How this feature can help you

Prior to this release, users who wished to model out workloads for OCI in Workload Planning could only leverage On-Demand or Spot (preemptible) pricing. With this update, you can now select 'Capacity Reservation' as a lease type option when adding a resource to your workload, similar to the option available in the OCI Cost Estimator . It's important to note that 'Capacity Reservation' is only supported for Virtual Machines and provides an additional 15% discount, which is forfeited upon utilization. For further details about OCI Capacity Reservation, please refer to the OCI Documentation .

As a reminder, any 'custom pricing' or 'custom discount' for OCI is by default factored in the resource price displayed in Workload Planning.

Capacity Reservation

You can now select 'Capacity Reservation' as a preferred lease type for OCI in the common information; the tool tip has been updated accordingly. When you choose this lease type, it will be the default selection for Virtual Machines recommendations.

You get visibility for Volume Performance Unit (into OCI Block storage VPU) amounts in the 'Attached Storage' recommendation screen. This information is not available for other cloud vendors.

### Container Utilization Metrics Enhancements in Cloudability – March 4, 2024

We have made enhancements to our utilization metrics on the Cloudability container insights page.

This update aligns the displayed memory metrics with those used in allocation calculations for improved consistency and corrects the file system usage for EKS to ensure accurate reporting. To clarify, these enhancements will not impact the cost or the cost allocation methodology and are designed to provide a more accurate reflection of utilization metrics on the container insights page.

### Enhancement to Cost (List) Metric in Cloudability – February 23, 2024

The Cost (List) metric functionality has been enhanced. Previously, certain private and bundled rate discounts appeared as credits in the metric which resulted in incorrect values. However, Cost (List) metric was designed to provide users with the on-demand cost for each line item, without including information about discounts and credits. This enhancement resolves the issue.

### Update to Azure Permissions on the UI - February 23, 2024

Today we launched a couple of updates on the list of Azure permissions visible in Cloudability.

• Starting today, Azure users will have Enrollment Reader role permission for Azure EA accounts and Billing Account Reader role permission for Azure MCA accounts on the UI. Before this release, users were shown only Enrollment Reader role permission for all Azure accounts.

• For Customers using Azure custom role we have added the below permissions display on the UI. These were part of the permissions we take while credentialing azure subscriptions but were not visible on the UI.

### Increase Cap on Maximum Kubernetes Labels in Tags & Labels Feature – January 31, 2024

We have increased the maximum number of Kubernetes labels available in our Tags and Labels feature from 10 to 20. With this enhancement, you can incorporate a greater number of Kubernetes labels, facilitating improved organization of synthetic tag dimensions tailored to their specific use cases.

### Workload Planning: Resource Duplication – January 23, 2024

How this feature can help you

Before this release, users faced the challenge of manually entering their requirements multiple times when evaluating different options for their cloud resources or comparing costs across various regions. Now, you can effortlessly clone your resources and adjust requirements. This will also allowing you to explore diverse configurations for your cloud resources with ease and precision.

How to enable resource duplication within a workload

1. Create a workload and add a resource.
1. Select the ‘Duplicate Resource’ icon to clone your resource.
1. Update the name for the resource duplicate and change the requirements. Note: You can now have resources in different regions within a given workload. You can update the resource region in “Search resource type (optional)” feature.

Use case example: Duplicating resources to compare AWS EC2 costs between two regions

1. Create a workload and add a resource. Use the “search resource type” option to get a cost estimate for t4g.2xlarge in us-west 1.
1. Duplicate the resource and rename it.
1. Update the region to us-west-2 for your duplicated resource.
1. 

### Container Cluster Rightsizing – January 19, 2024

This release adds rightsizing recommendations for Kubernetes clusters across AWS, Azure and GCP.

How this feature can help you

Cloudability users have previously been able to leverage rightsizing recommendations to optimize Kubernetes at the workload level – tuning container request and limit settings. This launch adds a new set of recommendations, this time at the cluster level. The feature evaluates vendor-defined groups that back each cluster: ASG Node Groups for AWS, Node Pools for Azure, and GCP. The recommendations are built around understanding the historical resource usage of these groups, focusing on CPU and memory utilization. For each cluster, the tool then recommends the most cost-effective instance type and count that will meet the resource requirements for every hour across the reporting period.

For Cloudability , to generate these cluster-level recommendations we ingest your VM util data via the regular AWS, Azure and GCP credentials. In short, if you are already setup for VM rightsizing recommendations, then these cluster recommendations will already be available.

- You can review all clusters and savings summary information in the list view. The detailed view for each cluster includes utilization charts to aid in decision-making.
- It offers multiple recommendations per cluster, with combinations of instance type and count at various risk levels, catering to different operational comfort zones.
- This launch does not include recommendations for groups consisting of spot instances.
- For this launch, each recommendation consists of a single instance type, prioritizing uniformity and simplicity.

### AWS cleanup of CAR and DBR permissions – January 18, 2024

Support for AWS Detailed Billing Report (DBR)and Cost Allocation Report (CAR) is no longer available in Cloudability , however in the permissions view we were showing the permissions related to DBR and CAR until now with a red "x". With this release we have removed the DBR and CAR permissions display from the UI.

How this feature can help you

This ensures AWS customers get a cleaner view of relevant permissions related to the AWS Cost and usage reports.

### Setting Default Cost Metrics for Cloudability Modules – January 17, 2024

How this feature can help you

Each module in Cloudability supports a specific set of cost metrics like such as Cost (Total), Cost (List), and Cost (Amortized) among others. Previously, Cost (Total) used to be the default cost metric displayed in these modules. Now, this features allows you to set your org's preferred cost metric as the default cost metric for each module. It will appear under Profile > Organization Settings in Cloudability for Cloudability Admin user roles only.

The cost metric set for each module will get applied as the default metric for all users across the entire Cloudability org.

### Cloudability introduces support for Oracle Cloud Infrastructure (OCI) in Workload Planning - January 16, 2024

Today we launched Oracle Cloud Infrastructure (OCI) support in Workload Planning. Starting today, users can seamlessly estimate the costs of new workloads deployed to OCI, enabling them to make informed provisioning decisions. What’s more, they can now effortlessly compare cloud resource pricing across AWS, Azure, GCP and OCI. Before this release, users had to use each vendor’s pricing calculator for the same.

![OCI support in WP](../images/workload-planning-oci-1.jpg)

More information about the release

The key highlights of this release include:

- Effortless OCI Workload Modeling : You can now seamlessly model out OCI workloads with resource recommendations spanning various service types* such as Virtual Machine, Attached Storage, Object Storage, and Load Balancer.
- Custom Pricing Support : Cost estimates in Workload Planning are inclusive of any custom pricing allowing you to plan more realistically.
- Cross-Cloud Resource Comparison : You can identify the most cost-effective solution easily by comparing resource requirements and cost estimates across major cloud providers – AWS, Azure, GCP, and OCI.

Managed Database is not yet supported for OCI.

### Cloudability Enhancement: Service Name Update for F5 Rules for AWS WAF Product - January 11, 2024

In this release, we have corrected the service name designation for “F5 Rules for AWS WAF”.

How this feature can help you

Previously, our solution incorrectly mapped the marketplace charge for “F5 Rules for AWS WAF” to ‘AWS WAF’ as the service name. This has now been amended to accurately reflect the charges under ‘AWS Marketplace’ service name. As part of this enhancement, we have also addressed additional edge cases where marketplace charges were not being mapped correctly to AWS Marketplace service name.

### Improved Cost (Total) Metric in Cloudability for AWS - January 5, 2024

How this feature can help you

The enhancement will help you improve the clarity of the cost metrics and simplify some of the reconciliation efforts.

More information about the release

Although, the Cost (Total) metric always aimed at delivering an unadulterated representation of the invoice cost – the “LineItem/UnblendedCost” column in the CUR file. However, there was one exception to this, implemented at the time to support a consistent transition between the DBR and CUR files. Logic was applied to these two item types:

- For usage covered by an RI – use “reservation/RecurringFeeForUsage”, instead of “LineItem/UnblendedCost”.
- For recurring RI line items – use “reservation/UnusedRecurringFee”, instead of “LineItem/UnblendedCost”.

This ensured that the usage line items had the consumed RI value assigned to them, instead of a zero value. It means, it moved cost from the monthly recurring lines to the usage lines. This helped in maintaining consistent behavior with the older, now deprecated, DBR file but had the downside of Cost (Total) not being a pure “pass through” cash metric. With Cloudability not supporting DBR anymore, these special rules for the Cost (Total) metric have been removed and the enhanced metric is reflected in the lineItem/UnblendedCost column .

These changes will take effect from January 2024 onwards. They will also apply to December 2023, if AWS has not yet finalized your billing. Additionally, the changes will be retroactive in the event of any billing reprocessing.

If you have any questions or require further assistance or need historical data reprocessed under the new method, please reach out to your account team or support.

### Support for Custom Pricing for GCP Rightsizing - January 3, 2024

How this feature can help you

This provides the capability to apply the contractual discounts received from your GCP to GCP rightsizing recommendations. This also provides you with a more accurate representation of the cost savings achieved by optimizing your resources. This will improve the accuracy of the rightsizing recommendations by bringing attention to cost saving opportunities while identifying resources that can be resized to better match your underlying workloads.

More information about the release

You are required to provide Cloudability with access to your custom pricing data to enable this feature. Once this setup has been successfully completed, the new customer specific GCP pricing will be automatically applied to the GCP rightsizing recommendations and functionality. The primary GCP rightsizing functionality is located by navigating to Optimize > Rightsizing > GCP . GCP resource level costs will be available in Cloudability under Reports and Dashboards by selecting the resource id column.

---

## What's new in Cloudability

<!-- sub-header -->
- **breadcrumb:** What's new in Cloudability > What's new in Cloudability
- **source_path:** SSVCLNQ/release-notes-standard/whats-new.html
- **original_file:** cloudability-whats-new-in.md
- **images:** []

### Cloudability Governance Adds Azure Support – July 1, 2026

Today we're excited to reach General Availability in Azure support for Cloudability Governance.

Customers who predominantly or partially operate on Microsoft Azure cloud can now experience the power of Cloudability Governance.

This capability extends our proactive cost insights and policy enforcement directly into the engineering workflow for Azure customers, ensuring that infrastructure changes are both cost-efficient and compliant before they are deployed

### Configurable Anomaly Detection- All Alerts Tab – June 29, 2026

Today, Cloudability Anomaly Detection introduces the All Alerts tab, enabling Cloudability Admins to view all anomaly alert subscriptions across their organization from a single, self-service location. This provides a centralized, read-only view of every alert subscription, including the subscriber, alert threshold, notification method, share type, and creation details, eliminating the need to raise a support ticket.

### Cloudability container insights supports OpenShift version 4.21 - June 25, 2026

Cloudability Container Insights now supports OpenShift 4.21. This update ensures continued compatibility with the latest OpenShift releases across major cloud providers, enabling customers to maintain full container cost visibility as they adopt newer versions of OpenShift.

### Cloudability Advanced Containers - Container Allocation and Assets Experience within Cloudability User Experience - June 24, 2026

Cloudability has released an enhanced containers insights experience by providing the powerful container allocations experience of Cloudability Advanced Containers (powered by Kubecost), now directly available in the Cloudability experience for customers with both Cloudability and Cloudability Advanced Containers.

This release includes support for dashboard, multiple/single aggregation, shared cost configuration, and moreIn addition, Kubecost's assets experience is also available within Cloudability. Users can use this to view and drill down into assets such as Node, Disk, Network, LoadBalancer, ClusterManagement, etc. This brings more of Cloudability Advanced Containers (powered by Kubecost) natively into Cloudability, eliminating the need to switch applications and streamlining workflows.

### Configurable Anomaly Detection – June 23, 2026

Today, Cloudability Anomaly Detection delivers Configurable Anomaly Dimensions, enabling Admins to select up to 4 Tags and Business Mapping dimensions most relevant to their organization. This ensures cost spikes are surfaced against dimensions that matter to their teams, rather than system-defined defaults. Configurable Anomaly Dimensions are scoped to Admin-level configuration only.

### Vendor Credentials - Granular GCS Bucket Permissions – June 3, 2026

As part of IAM improvements in GCP, we have refined the Cloudability GCP onboarding script to use bucket-specific Google Cloud Storage permissions instead of broader project-level storage permissions.

With this update, GCP Storage permissions are being moved from CloudabilityRole_Billing to a new custom project-level role, CloudabilityRole_Bucket. This role is designed to support access only to the required GCS bucket resources.

This change improves security by limiting storage access to specific buckets rather than allowing broader project-wide bucket access, in line with the principle of least privilege.

The below permissions have been redistributed to the new CloudabilityRole_Bucket.

- storage.buckets.get
- storage.buckets.getIamPolicy
- storage.multipartUploads.abort
- storage.multipartUploads.create
- storage.multipartUploads.list
- storage.multipartUploads.listParts
- storage.objects.create
- storage.objects.delete
- storage.objects.get
- storage.objects.list
- storage.objects.update

### Cloudability Advanced Containers Announces Partial View Support - June 2, 2026

Today, Cloudability Advanced Containers delivers Partial View Support, enabling organizations to scope the Advanced Containers experience to a specific subset of cloud accounts. This supports multi-tenant deployments and access-controlled environments where different users or teams should only see cost data relevant to their accounts.

Partial View Support is scoped to account-based views only . Views must be defined by cloud account membership using AccountGroups, Account IDs/Names, or vendor — other view types such as label- or tag-based views are not supported in this release.

With this release:

- A View Picker is now available in the Advanced Containers UI, allowing users to select and switch between configured views. The selected view persists in the URL and browser storage, making it easy to bookmark and share scoped views.
- All cost data — allocations, assets, and autocomplete results — is automatically filtered to the accounts associated with the active view.
- The active view is preserved when navigating between the embedded and standalone Advanced Containers experiences.
- Pages and widgets that do not support view-based filtering display a clear message rather than showing unscoped data.

### Cloudability Advanced Containers Announces Shared Credentials - June 2, 2026

Today, Cloudability Advanced Containers (CAC) delivers Shared Credentials, eliminating the need to configure cloud billing integrations separately within the Kubecost experience. Cloud cost credentials managed in Cloudability are now automatically recognized by Advanced Containers, giving customers a single place to manage their cloud integrations.

With this release:

- Cloud integrations configured in Cloudability are automatically reflected in Advanced Containers — no duplicate setup required.
- The Cloud Integrations settings page now shows credentials sourced from Cloudability, with a direct link to the Cloudability Credentials Service for any credential management.
- Cloud cost data is ingested automatically by the Cloudability pipeline, ensuring accuracy in CAC.
- Updated Cloud Cost Status API provides real-time visibility into the state of cloud cost ingestion per configured account.
- When Cloudability Advanced Containers is in use, cloud costs are handled by Cloudability and duplicate areas in Advanced Containers standalone such as cloud costs, cloud cost reports, cloud cost budgets, and collections are removed.

### CFP Intelligent Forecasting BETA - June 1, 2026

Today, we released Intelligent Forecasting capability for CFP. This new experience helps teams keep CFP plans current by refreshing existing forecast lines with projections based on the latest actuals, while giving users greater visibility and control over how those projections are generated.

CFP Intelligent Forecasting brings the same model-driven forecasting experience used in the Enhanced Forecast page into CFP plans. Users can open an individual forecast line, review historical actuals, view projections from multiple forecast models, visually compare those projections against current plan values, and apply the model that best reflects expected future spend.

Key Features

- Interactive forecast review – view an inline mini-graph showing actual spend history and updated projections directly within the forecast line table
- Improved forecast accuracy – use the Intelligent Forecasting engine to evaluate multiple models and recommend the best fit for each forecast line
- Model comparison and control – compare alternate model results and apply a different model when the recommended model does not reflect expected future spend
- Plan-value comparison – visually compare model-generated projections against existing plan amounts
- Re-forecast support – apply selected model results to update historical periods with actuals and future periods with new forecast estimates

Scope

This release supports interactive re-forecasting for individual forecast lines within CFP plans. Users can access Intelligent Forecasting from a forecast line (by clicking the expand icon to reveal the forecast mini-chart), review the latest actuals and projections, compare recommended and alternate model outputs, compare projected values against current plan values, and apply a selected model to update forecast values in the plan.

What’s Coming Next

At GA, CFP Intelligent Forecasting will add support for saving model selections and bulk re-forecasting making it easier for users to update forecasts based on latest actuals as part of a regular monthly update cycle.

Availability and Enablement

The CFP Intelligent Forecasting is available to all CFP customers. Intelligent Forecasting requires Update Actuals functionality, so the Update Actuals feature must be enabled before Intelligent Forecasting can be used.

Both Update Actuals and Intelligent Forecasting can be enabled from the Advanced tab on the Plan Preferences page, located under Settings in the Cloudability left navigation panel. Intelligent Forecasting is automatically enabled for customers that had enabled Update Actuals during the initial rollout period.

Intelligent Forecasting

### Cloudability Commitments Announces AWS Support for the Enhanced Commitment Manager Overview Page – June 1, 2026

On Monday June 1st, the Cloudability Commitments team released the Enhanced Commitment Manager Overview Page. This new page replaces the existing Commitment Manager through delivering parity functionality and enhancing it to work seamlessly as the landing page across Cloudability Commitment functionality. With this release, the new overview page, simply called Commitment Manager in the left-hand navigation menu, supports AWS services where we support a commitment type: All Compute, RDS, Redshift, Elasticache, and OpenSearch.

- · Chart look and feel is similar to the recommendation details page chart. This chart was recently enhanced with the AWS Support for Commitment Management 2.0 release.
- Enhanced KPIs, including Savings Rate and Coverage. KPIs on Overview page are same as shown on Portfolio and Recommendations.
- Simplified analysis period selection.
- KPI granularity supports Week, Month, and Total.
- KPI Comparison toggle.
- Chart's Cost Type support: True Cost, On-demand Equivalent (ODE).

- Daily report granularity.
- Cost/Savings Views: The Cost/Savings toggle is now gone. This information is now represented in a single chart.
- Recommendation Toggle: Moved to the header bar under the Recommendation Type dropdown.
- Navigation links to Portfolio and Recommendations pages.

- Daily Report Selection: The reporting range across the page is now month based. This simplifies the page and tailors it toward the primary use case, which is a high level overview of your performance and opportunities.
- Chart breakout by service: Aggregate reporting across services remains supported but cost is no longer explicitly broken out by service.
- Recommendation criteria selection: The Recommendation now assumes the Optimal Recommendation.
- The previous Commitment Manager page has been deprecated in favor of this new page. The old page is no longer support and cannot be restored.

For more information please see our help documentation under Using the Commitment Manager Overview to Align the Organization on Commitment Strategy .

### Cloudability Governance Adds Azure Support (Public Preview) – May 29, 2026

Today we're excited to introduce Azure support for Cloudability Governance.

Customers who predominantly or partially operate on Microsoft Azure cloud can now experience the capability of Cloudability Governance.

This expansion allows Azure-heavy enterprises to finally utilize the automated, proactive governance and cost-prevention features of Cloudability Governance rather than relying solely on reactive post-billing tools.

### Azure MCA credentialing - Auto Assigning Billing Account Reader role – May 25, 2026

This release automates assignment of the Billing Account Reader role to the Cloudability service principal for Azure MCA accounts, helping customers onboard faster.

Before this release, customers had to assign this role manually.

### User Experience improvements in Cloudability Rightsizing - May 28, 2026

- Service selection changed from tabs to menu . As more services are added to Rightsizing, we've replaced the tab-based service selector with a more efficient menu, similar to the Commitments page.
- Removed duplicate service type label from dashboard area . The service type is now displayed only in the service picker, eliminating redundant information and freeing up valuable screen space.
- Cost Basis changed from radio buttons to . The cost basis selector has been converted to a menu, similar to the Commitment Manager interface, providing a more consistent user experience. For services that only support a single cost basis, this field is read-only.
- Timeline renamed to "Analysis Period" with selector . The timeline selector has been renamed to "Analysis Period" to align with terminology used in Commitment Manager. The selector has been changed from radio buttons to a menu to conserve screen space. For services that only support a single analysis period, this field is read-only.

### Azure MCA credentialing - Auto Assigning Billing Account Reader role – May 25, 2026

This release automates assignment of the Billing Account Reader role to the Cloudability service principal for Azure MCA accounts, helping customers onboard faster.

Before this release, customers had to assign this role manually.

### Calculated Metrics in Dashboards and Reports – May 21, 2026

We're excited to introduce Calculated Metrics for Cloudability Dashboards and Reports. This powerful capability enables you to define sophisticated unit economics and KPIs from a centralized hub, providing enhanced visibility into cloud spend and operational efficiency through custom, reusable metrics.

Centralized Metric Management: Create, edit, and delete calculated metrics from a single hub within the Business Mappings product area. Define metrics once and reuse them across all dashboards and reports, eliminating redundant configuration and ensuring consistency.

Flexible Formula Creation: Build custom formulas using numeric constants, basic arithmetic operators, and existing metrics. Support for flexible formulas enable sophisticated analysis tailored to your business needs, including unit economics like cost per Resource or cost per Cluster.

Role-Based Permissions: Enhanced access controls ensure proper governance with three permission levels: Admin (full access to create, edit, and delete all metrics), Edit (create and modify own metrics), and View (read-only access).

### Cloudability Commitments Adds Portfolio Support for Microsoft Foundry Provisioned Throughput – May 19, 2026

Today, we delivered support for Microsoft Foundry Provisioned Throughput (PTU) . The thirteenth Azure commitment type supported, Foundry PTUs provide a discount on AI services in exchange for a one-month or one-year commitment to hourly usage. This commitment type is categorized as a resource-based commitment, and as such, requires selection specific usage parameters: Region, Deployment Type, and Payment Option. With this release, only the portfolio supports this commitment type. We will consider building recommendations in the future.

For more information, visit the commitment management help documentation. (edited)

### Import and Export Business Mapping Definitions via UI – May 15, 2026

- Export: Users can now export individual Business Mapping definition directly from the UI into a JSON file, allowing easy sharing or backup of BM configuration.
- Import: Users can now also import BM definition into an existing BM. The imported JSON file populates the UI with new values, allowing users to review and validate the changes.

### Cloudability Commitments Announces AWS Support for Commitment Management 2.0 – May 13, 2026

- Enhanced KPIs, including Savings Rate and Coverage
- Aggregate ‘all’ pages when applicable across the portfolio
- Coverage modal support
- Revamped recommendation details page
- Custom recommendation adjustment feature

This release helps users build a business case for a commitment strategy aligned with best practice. Specifically users can now customize Cloudability's recommendation to support sensitivity analysis for both long term strategy and the next incremental purchase. This allows users to mix term, leverage spend and resource based commitment types, and ladder up and down based on future usage assumptions.

Additionally, this functionality begins to connect the bespoke commitment pages to reporting which provides the transparency our customers require to leverage our application across commitment management chargeback/show back use cases.

How do I get Help?

Our help content was rewritten to support these major enhancements. The content starts with Cloud Cost Optimization in Cloudability . Tactically, Using Commitment Portfolio to Understand Historical Performance and Using Commitment Recommendations to Analyze Savings Opportunities provide directions for how to leverage the new portfolio and recommendations pages.

What’s Next?

This functionality was previously completed for GCP commitments at the end of 2024. We will now turn our attention to providing parity capabilities for Azure.

### Cloudability Commitments Announces AWS Commitment Recommendation Improvements – May 13, 2026

Today, the Cloudability Commitments team delivered significant enhancements our AWS Commitment Recommendations. This release can be viewed as a sub-release to Cloudability Commitments Announces AWS Support for Commitment Management 2.0 – May 13, 2026 . We are calling it out separately to bring attention to the nuance around the recommendation improvements. Users can expect the following improvements:

Introduction of Cost-based Coverage Approach - With the introduction of the Coverage KPI to AWS, we are using actual cost data rather than allocated usage hours. This will differ from the reserved coverage rate metric in reporting as coverage there is derived via usage hours. Across Commitment Portfolio and Recommendations, coverage is driven directly by cost, specifically, the portion of your on-demand equivalent spend that was covered by a commitment in a given period.This change makes coverage more meaningful for financial decision-making. Usage hours are difficult to compare across instance types and don't directly correspond to what you're spending or saving. Cost-based coverage does. With AWS Cost Explorer calculating Reserved Instance coverage in usage hours, Cloudability's cost-based approach gives you a more financially accurate view, one that reflects the actual dollar impact of your commitments rather than an hours-based proxy that can vary significantly across instance families and sizes. For Savings Plans, we believe we are now aligned with how AWS natively calculates coverage.

Recommendation driven by existing commitments across analysis period - Previously, Commitment Recommendations considered only today's commitment coverage when generating our recommendations. We now will use whatever coverage was present across the analysis period selected. While this does have the drawback of potentially being less accurate, for example if a commitment was purchased or expired during the analysis period, it now makes how the recommendation is created more straightforward. When you go to the recommendation details page, you will now see a chart that is simply in terms of cost. The proper way to now use this is feature is to view usage over the analysis period and re-select an analysis period that best represents the future. In many cases, this would require users to adjust the analysis period down to just a week or two, down from the default full month. This change is expected to have a minor impact on customers' recommended amounts post release. We believe this is an improvement because the chart now accurately represents, "What if I had owned this recommendation overt the course of the analysis period selected."

Include / Exclude Existing Saving Plans for Reserved Instance Recommendations - We now include the ability to ignore existing Savings Plans for EC2 Reserved Instance Recommendations. Due to the fungible nature of Savings Plans, they are often variably allocated by AWS. As a result, hours where savings plans were allocated to a given Instance Family/Region/Account/OS combination would cause significant variability to our recommendations given minor difference in analysis period. This feature allows you to ignore the Savings Plans since if variable usage would potentially be applied elsewhere in the event the Reserved Instance existed. This provides our users flexibility to continue to take advantage of the higher commitment savings rate of Reserved Instances.

Include / Exclude Linked Accounts - We now support the ability to generate individual recommendations per linked account across a payer. When sharing is turned on, we continue to aggregate all linked accounts within a payer account when analyzing usage. This represents how AWS distributes RIs and will offer the best savings. What is different is when sharing is off, and the user selects a payer account, they will now see a recommendation for each account rather than only a recommendation for the usage under the payer account.

How do I get Help?

Our help content was rewritten to support this enhancements. The content starts with Cloud Cost Optimization in Cloudability .

### Dashboard Tabs in Cloudability Dashboards – May 12, 2026

- Users can drag&drop Tabs to change their order
- Users can duplicate entire Tabs to copy them between Dashboards
- Users can drag&drop a Widget to move it to a different Tab
- When copying Widgets, users can choose which Tab to copy to

### Cloudability Commitments Announces Support for Column Preference Across Commitments– May 12, 2026

Today, the Cloudability Commitments team delivered a minor improvement to it's table. For tables across portfolio and recommendations for AWS and GCP, we now persist the show/Hide column selection in your machine's local storage. As a result your column selection will now persist across sessions. Notably, each commitment page has a different set of columns and order saved as the default. For more information, please view Commitment Table Basics in our Help Center.

### Commitment Recommendations Details Chart Enhancements – May 11, 2026

Today, the Cloudability Commitments team formally announces a handful of improvements to the recommendations details page. This is formally part of the Commitment Management 2.0 release. It is getting a standalone post here because this change is applicable to both AWS and GCP.

Assumed ODE Selection : A toggle for assumed ODE (on-demand equivalent) selection has been added to the Recommendation Details page, allowing users to ignore the assumed ODE for a simpler cost chart. Turning the toggle off shrinks the y-axis and puts more focus on cost.

Split Commitment Capability : Users can now split commitments from the Recommendation Details page, viewing current commitments either summed together or broken out individually. This benefits an analysis of a recommendation whose coverage usage could be covered by a different commitment type.

Updated Chart Tooltip : The chart tooltip has been redesigned to support scrolling and aggregates cost in a format resembling a financial statement, communicating hourly data alongside summarized totals for improved readability and at-a-glance analysis.

Total Cost Removed from Chart Type Dropdown : Total Cost is no longer available as a chart type since totals are now accessible through the updated tooltip. Toggle controls have been updated accordingly, addressing user feedback that the previous selection was confusing.

Recommendation Type Renamed : The top-level Custom recommendation type is now Modified, and the Adjusted Recommendation type is now Custom. These changes resolve naming conflicts created by the renamed cost basis list. For more information, see Using Commitment Recommendations to Analyze Savings Opportunities .

### Cloudability Commitments Announces Miscellaneous Minor GCP Commitment Enhancements – May 11, 2026

- Enhanced Account Selection for Large Number of Accounts across Portfolio and Recommendations: Customers can have thousands of accounts. We now fold the linked accounts up to the payer account. This is especially useful for commitments since they are typically bought/shared at the payer account level. Users no longer need to endlessly scroll or know exactly what account to search for.
- Analysis Period Cost on Portfolio: We now support the total cost for the analysis period alongside the remaining cost. Customers might want to compare this number with what they see in reporting. You no longer need to add this column by hand or export the table into a csv to sum.
- Portfolio (PSR) and Commitment (CSR) Savings Rates on the Portfolio: The CSR and PSR are distinctly different. The CSR is the weighted savings rate of your commitments across the analysis period. The PSR is the saving rate of your portfolio. CSR = Savings / On-Demand Equivalent of Commitment Cost. PSR = Savings / Committable Spend. Seeing these two values side by side helps draw the distinction between the two KPIs. For more information, see Commitment Key Performance Indicators .

### Cloudability adds support for Azure Blob Storage tier recommendations – May 11, 2026

Today, we added support for Azure Blob Storage tier recommendations. Cloudability users can now optimize Azure storage costs by receiving intelligent recommendations for container-level access tier configurations, including Hot, Cool, Cold, Archive, and Smart Tier options.

For each container, Cloudability analyzes storage usage, access patterns, and operational costs to identify tier misconfigurations. Recommendations calculate total monthly costs across all available tiers, including early deletion fees and retrieval costs, to suggest the optimal configuration that minimizes costs while maintaining performance requirements.

These recommendations follow the same format as existing AWS S3 and Google Cloud Storage tier optimization recommendations and are visible on the Rightsizing Explorer page. The feature supports both traditional tier transitions and Azure Smart Tier automatic optimization, providing flexibility for different storage management strategies.

For more information, see Azure Blob Storage rightsizing .

Customers must add 'Microsoft.Storage/storageAccounts/read' permissions for all elements of this feature to work as expected.

### Enhanced Forecasting - May 4, 2026

We released the Enhanced Forecast page – a new and improved cloud forecasting experience for Cloudability.

The Enhanced Forecast page is a major upgrade to the legacy Forecast experience, delivering the same core forecasting functionality with significantly more flexibility, transparency, and control. Users can choose their own forecast drivers, analyze full forecast line-item detail, benefit from more accurate Intelligent Forecasting, visually compare model results, and connect forecasts to budget workflows.

New and Enhanced Functionality (over legacy Forecast page)

- User-selectable spend drivers – choose your own dimensions, instead of the fixed drivers used by the legacy Forecast page
- Full forecast line-item detail – review all forecast line items, not just the top 20
- Improved forecast accuracy – uses the Intelligent Forecast Engine to evaluate multiple models and automatically select the best fit, instead of relying on a single fixed model
- Interactive model comparison and control – review model details, visually compare alternate model results, and apply a different model when needed
- Pivot-style detail analysis – group, summarize, sort, and filter forecast line-item details directly in the table

Learn more about Enhanced Forecast

### Logging and Monitoring in Workload Planning - April 29, 2026

This release introduces support for Logging and Monitoring services across AWS, Azure, and OCI. For GCP, Workload Planning currently supports Logging only. This is similar to how users can already create estimates for services such as Virtual Machines and Databases.

Users can select the appropriate service from the Service Type drop-down: Logging and Monitoring for AWS, Azure, and OCI, and Logging for GCP. After entering the required capacity and, optionally, defining their specific configuration, Workload Planning will generate pricing options tailored to their requirements.

### User Experience improvements in Cloudability Dashboards - April 28, 2026

- Persist widget filters configuration when switching widget types. When changing a Widget type (e.g. from a Chart to a Table), the interface will now retain the filters configuration so that the filters configuration does not need to be recreated separately for each type of Widget.
- The “Other” row in table widgets is now displayed separately from the remaining values to clearly distinct it from the actual results.
- Date-based filters can now be configured using a user-friendly calendar input . With this change, users will not need to type in the values for date format filters. Instead, users will be able to pick a date using a built-in calendar selector.
- Copy and paste filters to/from clipboard. Users will now be able to easily move a filters configuration between different Widgets and save a filter set to reuse it later.
- Export chart as a .png image. Charts can now be exported and saved as an image in PNG format.
- Search and filter in a table widget . All Table widgets can now be filtered using a single text-based search field that is applied across all visible columns.
- Export as PDF . The entire Dashboard can now be exported in PDF format to enable easier collaboration with other users.

### Subscribe to Reports with comparison date range - April 28, 2026

This release introduces an improvement to Cloudability Reports subscription functionality. With this change, users will be able to subscribe to Reports that use “Compare date” functionality, in the same way as they are currently able to subscribe to Reports with a single date.

### Cloudability Optimization Dashboard’s COIN Explorer Supports Conditional Formatting - April 20, 2026

Cloudability has added support for conditional formatting in the COIN Explorer found in the Optimization Dashboard. In the Rightsizing preferences section, users can set thresholds for COIN score conditional formatting. The settings include a green/yellow threshold as well as a yellow/red threshold.

COIN (Cost Optimization Index Number) provides a standardized metric for organizations to review optimization opportunities in the context of the spend in that area of their business so they know where to focus and prioritize. Many organizations go as far as treating it like a leaderboard to compare the efficiency of teams across their organization.

Accompanying this release, several updates were made to the optimization dashboard around COIN and realized savings to improve accuracy.

### Support for Google Cloud Storage Tier Recommendations - April 14, 2026

Cloudability has added support for Google Cloud Storage tier recommendations. Cloudability users can now optimize GCS costs by receiving recommendations for bucket-level storage class configurations, including Standard, Nearline, Coldline, Archive, and Autoclass options. For each bucket, Cloudability analyzes storage usage, access patterns, and operational costs over a minimum of 30 days to identify storage class misconfigurations.

These recommendations follow the same format as existing AWS S3 tier optimization recommendations and will be visible in the Rightsizing Explorer page. Customers with Resource Level Billing enabled for GCP will automatically begin receiving these recommendations.

Customers must add 'storage.buckets.list' permissions for all elements of this feature to work as expected.

### GCP Compute Rightsizing Now Includes License Costs - April 14, 2026

Cloudability has enhanced GCP compute rightsizing recommendations to include operating system and software license costs in savings calculations. Cloudability users can now receive more accurate rightsizing recommendations that account for the full cost of running GCP instances, including Windows Server, SQL Server, Red Hat Enterprise Linux, SUSE Linux Enterprise, and Ubuntu Pro licenses.

Previously, GCP rightsizing recommendations only considered compute costs (CPU, memory, and storage), which could lead to incomplete savings estimates for instances running licensed operating systems or software. With this enhancement, recommendations now calculate both compute and license costs for source instances and recommended targets, ensuring that license requirements and minimum core counts are respected when suggesting alternative instance types.

These enhanced recommendations will be visible in the Rightsizing Explorer page and maintain the same format as existing GCP compute recommendations. Customers with GCP instances running licensed operating systems will automatically see more accurate savings estimates that reflect total cost of ownership.

### Business Mappings View Only Permission Enhancements - April 14, 2026

We released an improvement to view-only permissions in Business Mappings area. With this change, users with view-only access will no longer see action buttons (Edit, Delete, Create, etc.) in Business Dimensions, Hierarchical Dimensions, and Business Metrics. Additionally, we unified the viewing experience across all Business Mappings areas. View-only users can now consistently access details in Business Dimensions, Hierarchical Dimensions and Business Metrics.

### Ability to rename Hierarchical Business Dimension - April 9, 2026

We've launched the ability to rename Hierarchical Business Dimensions in Business Mappings. With this change, users can now edit the name of their Hierarchical Business Dimensions directly within the interface, which provides grater flexibility in organizing their structures.

### Cloudability Rightsizing Introduces Savings Thresholds for Block Storage - April 7, 2026

Cloudability Rightsizing added support for an expanded functionality in Rightsizing preferences to provide a minimum savings amount for Block Storage. This threshold, (defined for a 30-day recommendation, and prorated for 10-day recommendations), allows organizations to define the minimum savings amount for their block storage recommendations (AWS EBS, Azure Disk, and GCP Persistent Disk) and filter out any recommendations that don’t meet that threshold.

This release allows organizations to focus on the most impactful recommendations, similar to the existing functionality that was established for Compute Rightsizing recommendations.

### Cloudability Governance Support for GitHub Enterprise Server - April 7, 2026

Adding support for GitHub Enterprise Server extends Cloudability Governance into self-hosted, highly regulated environments, enabling enterprises to bring FinOps policy checks , cost estimation , and recommendations directly into their existing, on-premise GitHub-based workflows. This enhancement lets platform and FinOps teams apply the same guardrails and approval workflows they use with GitHub.com to repositories hosted on their own infrastructure, aligning cost and compliance controls with existing governance frameworks for GitHub Enterprise .

### Cloudability x ServiceNow CMDB Integration for Business Dimensions - April 1, 2026

Today, we are launching Cloudability x ServiceNow CMDB Integration for Business Dimensions .

The Cloudability x ServiceNow CMDB Integration enables automated synchronization between ServiceNow CMDB and IBM Cloudability Business Mappings, allowing organizations to use ServiceNow as the single source of truth for business structure and cost allocation logic in Cloudability.

This integration eliminates the need for manual or API-driven updates to Cloudability business mappings by automatically reflecting CMDB changes from ServiceNow into Cloudability. The integration can only be installed on certified ServiceNow versions; unsupported versions will block installation entirely.

Key Highlights:

- Automated Business Mapping: Business mappings in Cloudability are automatically created and maintained based on ServiceNow CMDB data.
- Centralized Governance: ServiceNow CMDB acts as the authoritative source for organizational, application, and cost-center data used for cloud cost allocation.
- Near Real-Time Synchronization: Updates in ServiceNow CMDB are automatically reflected in Cloudability without manual intervention.
- Native ServiceNow App: The integration is delivered as a certified application available in the ServiceNow Store.

ServiceNow integration is available in ServiceNow store under the following link: https://store.servicenow.com/store/app/c3864d3d4784fe1482f632c4f16d43c8

### Vendor Credentials - Ability to archive uncredentialed accounts - April 1, 2026

This release introduces the ability to archive uncredentialed accounts directly from the Vendor Credentials screen.

Previously, uncredentialed accounts had to be credentialed first before they could be archived. With this update, accounts in an uncredentialed status can now be archived directly using the ellipsis ( ⋯ ) menu , eliminating the need for credentialing.

Overall archive actions are now available directly from the Vendor Credentials screen for all accounts irrespective of the status.

### Anomaly Detection - Anomaly Feedback - March 30, 2026

We’ve launched Anomaly Feedback Starting today, you can provide quick feedback on detected anomalies using a simple thumbs up or thumbs down . This helps us understand whether the anomalies being flagged are actually useful. Previously, there was no direct or structured way to share feedback, which limited our ability to refine detection quality based on real user input.

### Bulk Import in WLP - March 30, 2026

This release introduces a major enhancement to the Bulk Import feature in Workload Planning (WLP). It allows customers to upload a structured file with up to 500 resources in a single operation across all service types, regions, and CSPs.

This feature helps customers perform workload planning more efficiently by eliminating the need to add resources manually or in smaller batches. Users can now import up to 500 resources at once, receive recommendations instantly, and accelerate their cloud planning process.

### Export the Accounts status in Vendor Credentials - March 19, 2026

This release adds support for exporting the vendor credentials status in csv format. This feature helps our customers to quickly review the status of accounts when the number of accounts are large in number.

Each of the credentialed data sources with account status can be exported in cs format. Each datasource will have its individual export.

### Snowflake Warehouse Cost Insights & Tag Support - March 19, 2026

With this update, teams can attribute costs more precisely, and surface key cost drivers using Cloudability’s dashboards and Business Dimensions. Previously, Cloudability provided visibility only at the service level, meaning customers could not see the cost of individual warehouses nor use Snowflake tags for cost allocation. Cloudability now delivers deeper insights directly within existing workflows, enabling more effective cost governance and informed decision making.

How does it work?

- For customers with existing access: No action is required.
- For customers already using Snowflake credentials in Cloudability:
- Organizations that did not previously recredential will need to do so to activate these enhancements. The process remains unchanged: simply follow the steps in our Help Center and run the updated template provided in the UI.
- For customers new to Snowflake in Cloudability:
- Complete the standard credentialing process described in the Connect Snowflake

### Resource Inventory Saved Reports: Improved date range handling - March 17, 2026

Previously, opening a Resource Inventory (RIS) saved report with a non-rolling date range and exceeding the supported three-month window failed to load and displayed an error message.

With this update, such reports load successfully instead of failing. If the saved date range exceeds the supported limit, Cloudability automatically resets it to the default 7-day range and displays a flash notification informing users that the date range was adjusted.

This improvement ensures saved reports remain accessible even when their stored date ranges fall outside the supported limit.

### Dashboards 2.0 - March 16, 2026

Today, we are launching Dashboards 2.0 - a major front-end revamp of the entire Cloudability Dashboards experience. This upgrade aims to modernize the technology used in Dashboards, unlock new Dashboards functionality and accelerate the future feature development. Dashboards 2.0 address several usability issues and optimize the overall design of the Dashboards framework.

- There are no functional changes between Dashboards 2.0 and previous version of Dashboards. All the functionality will remain the same.
- There will be slight visual differences that do not impact the product behavior.

Dashboards v2 is now enabled in all regions.

### Support for OCI in Resource Inventory - March 16, 2026

We’re excited to announce support for Oracle Cloud Infrastructure (OCI) in the Resource Inventory feature. With this release, you can now view cost, utilization, and resource-level metadata for OCI Compute (Virtual Machine) services in the same single-pane-of-glass experience you already use for other hyperscalers.

OCI Compute service support includes all the existing capabilities available in Resource Inventory today. To enable this feature for your Cloudability organization, please contact your TAM, CSM, or Apptio account representative. Within 3–4 business days of enablement, complete OCI inventory data for Compute resources will be available in Cloudability.

For more details, see OCI Resource Inventory .

### Cloudability Adds Support for Dynamic COIN Reporting - March 6, 2026

Cloudability added a new tab to the Optimization Dashboard allowing users to report on resource optimization opportunities and contextualize those opportunities with the underlying spend in the form of a COIN Score (Cost Optimization Index Number).

COIN scores can be leveraged to better understand and contextualize opportunities as well as to normalize optimization opportunities across different teams and organizations to act as a leaderboard or way of measuring efficiency.

In the newly released COIN Explorer, users can add or remove fields to understand COIN scores at the desired granularity as well as export this data as needed.

### Cloudability Rightsizing Adds Support for Azure Available Memory Bytes Metric – March 4, 2026

Today, we delivered enhanced memory metrics for Azure compute rightsizing recommendations. Cloudability now leverages Azure's standard Available Memory Bytes metric as a fallback when custom memory utilization data is unavailable. This enhancement ensures more Azure instances receive comprehensive rightsizing recommendations without requiring customers to configure custom metrics.

Previously, Azure instances without custom memory metrics could not receive memory-based rightsizing recommendations, limiting optimization opportunities. With this release, Cloudability automatically calculates memory utilization from Azure's built-in Available Memory Bytes metric, expanding the coverage of rightsizing recommendations across your Azure compute resources.

This improvement may result in updated recommendations and savings estimates for Azure instances that previously lacked memory data. No action is required from customers—the enhancement automatically applies to all Azure compute recommendations. Customers who already have custom memory metrics configured will see no change in their recommendations.

For more information, visit the rightsizing recommendations help documentation .

### Cloudability Commitments Adds Support for Azure App Service Reserved Instances – February 23, 2026

Today, we delivered support for Azure App Service Reserved Instances . The twelfth Azure commitment type supported, Azure App Service Reserved Stances provide a discount on compute in exchange for a one- or three-year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Tier, Instance, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

### User-friendly Business Mapping names in data exports - February 19, 2026

With this release, Cloudability Dashboards and Reports launched a new functionality, that will return the user-friendly names of Business Metrics, Business Dimensions, Account Groups and Tags&Labels when exporting CSV data from a Report, Dashboard or Explore. Previously, Business Metrics and Dimensions were exported using a column ID (e.g. "category12"), instead of the user-friendly label. The default behavior of API-based exports will NOT change . However, users will be able to add "useDimensionNames=true" option in the request to opt-in to this feature when using API. Existing API integrations will NOT be impacted, and users will be able to use the user-friendly names of Business Mappings if they want by adding the flag to their API requests.

### Cloudability Anomaly Ignore Alerts - February 19, 2026

Today we launched Anomaly Ignore Alerts. Starting today, users can temporarily ignore anomaly alerts directly from the alert configuration page to reduce noise during expected cost events and ensure only meaningful, actionable alerts are surfaced.

Key capabilities include:

1. Ignore alerts at the individual anomaly alert level
1. Support ignore functionality for shared alerts
1. Select preset ignore duration (7, 14, or 30 days)
1. Define a custom date range for ignoring alerts.
1. Edit the ignore duration (extend or shorten as needed)
1. Schedule ignore for a future time period
1. Ignore alerts in bulk using the Bulk Anomaly Alert Ignore option
1. Automatically resume alerts once the ignore period ends

### Cloudability Commitments Announces Support for GCP’s New Spend CUD Program – February 16, 2026

Today, IBM Cloudability announces support for GCP’s New Spend CUD Program.

Background

In early 2025, GCP announced significant changes to how their spend-based commitments would be billed, impacting 13 of their 17 commitment types .

On July 15, 2025, GCP enabled early migration to the new spend-based CUDs program. Between July 2025 and early February 2026, users could voluntarily opt into the new billing model. During the first week of February, GCP began force-migrating customers, completing the process on Friday, February 6. A brief overview of the program is available here: Simpler billing, clearer savings: A FinOps guide to updated spend-based CUDs .

We had been recommending that users delay migration because it was a breaking change across reporting, commitment portfolio, and commitment recommendations.

Support for the new billing paradigm

With this announcement, the new billing paradigm is now supported across both reporting and commitment functionality. Commitment portfolio and recommendations have been restored to near parity with the previous billing model. For reporting, we've delivered an improved experience compared to what existed prior.

At a high level, reporting on commitment cost and waste is now more straightforward and follows the paradigm already established for AWS and Azure. Additionally, we can now report on this data at a per-CUD level. Under the previous paradigm, this was not possible and represented a common pain point for users looking to apply granular chargeback or showback logic.

These changes are live in production for all users. For users who voluntarily migrated prior to the forced migration in February, a refetch of previous month data may be required. For more information, see Supplemental Guide to GCP CUD

### Cloudability Support for Azure Foundry (Brand Update) – February 13, 2026

With this release, we have updated the Service Name dimension in Cloudability to align with Microsoft’s rebranding of Azure Cognitive Services to Azure Foundry.

The existing Service Name “Azure Cognitive Services” will now be represented as two distinct Service Names:

| Before | After |
| --- | --- |
| Azure Cognitive Services | Azure Foundry Models Azure |
|  | Azure Foundry Tools |

- Foundry Models – Core inferencing engines (Azure OpenAI, Phi, DeepSeek, Llama)
- Foundry Tools – Pre-built AI capabilities (Speech, Language, Document Intelligence)

- All new data will automatically reflect the updated Service Names
- Historical data will reflect the new names upon reprocessing

### View assignment visibility for User and Entra ID Groups – February 11, 2026

We’ve improved group management by adding visibility into where User Groups and Entra ID Groups are used across Views. Previously, if a Group was used in View assignment, the system blocked it's deletion and admins had no easy way to identify which Views were using the Group. This often required manually checking multiple Views.

With this enhancement, admins can now see a read-only list of all Views where a group is assigned, directly from the User Group or Entra ID Group definition page. The list displays the View names and clearly indicates when a group is not used in any View, helping streamline group cleanup and reduce manual effort.

For more information, visit the Manage User Groups and Manage Entra ID Groups help documentation.

### Auto Sync scheduling for Entra ID Groups – February 5, 2026

Today, we’ve added auto-sync scheduling for Entra ID Groups to improve usability and reduce administrative effort. Previously, Cloudability admins had to manually sync Entra ID Groups using the “Sync Entra ID Group” action, which could result in missed updates as Entra ID group memberships change frequently.

With this enhancement, Cloudability admins can now configure daily, weekly, or monthly auto-sync schedule using defined filter criteria. Entra ID Groups are automatically synced based on the selected schedule and criteria, ensuring Cloudability remains consistently aligned with Entra ID, without manual intervention.

For more information, visit the Manage Entra ID Groups help documentation.

### Cloudability Optimization Dashboard adds Effective Cost Basis for Resource Recommendations - February 2, 2026

Today, Cloudability added the effective cost basis as an option for the recommendations surfaced in the Optimization Dashboard (Beta). The effective cost basis allows for a more meaningful COIN calculation by comparing the amortized cost of the services to the effective cost savings calculated by Cloudability’s Rightsizing recommendations. This preference can be found in the Rightsizing Preferences > Dashboard section along with the other preferences and settings that impact the Optimization Dashboard.

### Cloudability Commitments Update Surrounding Upcoming Support for GCP’s New Spend CUD Program - January 30, 2026

On January 16th, we provide an initial announcement about GCP's mandatory migration to the New Spend CUD Program. The following information is an update on what we can share at this time.

- If you have not voluntarily migrated, GCP will migrate it's customers to the new billing model next week:February 2nd - 5th, 2026.

- We plan to release iterative support as we become confident in our release. Cloudability Reporting, Commitment Portfolio, and Commitment Recommendations will likely be released in a staged manner.
- We expect to release support during the week of February 9th - 13th, 2026. We are hopeful that customers can expect full functionality starting Monday, February 16th.
- No action is required from you—we expect to support the new program automatically when your migration occurs.

- For customers who have already migrated, we need to re-fetch data dating back to the month you had voluntarily opted into the new program. We request that you reach out to your account teams to provide that month in preparation for our backend release.
- For customers who will undergo the mandatory migration next week, we may require a re-fetch of February to have complete history. We will provide an update next week.
- Note that for both cohorts, we will support the new program moving forward post our infrastructure release. This re-fetch is a one time requirement and only necessary for the months between when we release backend support and the migration occurred.

### Commitment Support for Azure Database for MySQL Reserved Capacity – January 23, 2026

Today, we delivered support for Azure Database for MySQL Reserved Capacity . The eleventh Azure commitment type supported, Azure Database for MySQL commitments provide a discount on compute in exchange for a one- or three-year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Deployment Option, Instance, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

### Cloudability Rightsizing Support for Azure Virtual Machine Scale Sets - January 22, 2026

Cloudability has added Azure Virtual Machine Scale Sets support in Rightsizing. Cloudability users can now receive recommendations to rightsize their scaling behavior by modifying the types of instances used in the ScaleSet to achieve a better cost outcome without impacting the performance of the application.

Customers may need to update their permissions to leverage this release, including the management:Reader permission or following three permissions:

1. Microsoft.Compute/virtualMachineScaleSets/read
1. Microsoft.Compute/virtualMachineScaleSets/virtualMachines/read
1. Microsoft.Compute/virtualMachineScaleSets/extensions/read

Prior to this release, users with Azure compute recommendations may have seen individual instance recommendations for instances that were part of scale sets. These instances will now be treated as part of the scale set instead of individually, so some customers may see their recommendations for Azure Compute instances change with this release to avoid double counting.

These recommendations will also be visible in the Rightsizing Explorer page and can also be linked to Rightsizing ROI tickets like other recommendation types.

### Advanced Containers Powered By Kubecost – January 22, 2026

Advanced Containers powered by Kubecost is a paid add-on for Cloudability that provides access to the full Kubecost feature set directly within the Cloudability experience.

Advanced Containers extends existing Cloudability container insights with advanced Kubernetes cost visibility, optimization, and automation capabilities.

With Advanced Containers, you can:

- Access the full power of Kubecost, including granular Kubernetes cost allocation down to the pod and container level.
- Monitor and optimize GPU workloads, including GPU cost visibility and rightsizing insights.
- Enable automated Kubernetes optimization, including actionable and automated CPU and memory rightsizing.
- View real-time Kubernetes costs, rather than delayed or batch-processed container spend.
- Monitor and allocate costs for on-premises Kubernetes clusters, in addition to cloud-hosted environments.

Advanced Containers is available as a paid add-on to Cloudability and requires deploying the Kubecost agent to monitored Kubernetes clusters.

For setup instructions and additional details, see the Cloudability Advanced Containers documentation.

### Cloudability Commitments Announces Upcoming Support for GCP’s New Spend CUD Program - January 16, 2026

Google Cloud Platform (GCP) has shifted the mandatory migration date for the New Spend CUD Program from January 26th to a multi-day window: February 2nd - 5th, 2026.

- During the migration day, GCP has communicated that users will not be able to purchase new CUDs for at least a short time as the migration to the new billing program completes.
- When Cloudability begins to support the Spend CUD program, it will require at least a day, but no longer than 48 hours for our systems to refresh.
- No action is required from you—we expect to support the new program automatically when your migration occurs

GCP sent a Mandatory Service Announcement (MSA) on December 11th, 2025 with your specific migration date. You can also find this date on the Billing Overview page in your GCP Console. Note that Cloudability does not have access to individual customer migration dates.

Already migrated to the new Spend CUD program? If you opted into the new Spend CUD program early, we apologize for the delay in support. Full functionality will be restored when the formal migration window begins in early February. For any further questions or concerns, please reach out to your account team.

### Cloudability Governance is now Generally Available – January 15, 2026

This new capability brings proactive cost insights and policy enforcement directly into the engineering workflow, ensuring that infrastructure changes are both cost efficient and compliant before they are deployed.

Cloudability Governance is now available for DevOps engineers , Platform Admins , and FinOps teams who manage AWS resources and use Terraform - whether through Terraform Community , HCP Terraform or Terraform Enterprise – for their infrastructure as code solution. This feature is designed for teams that host their code repositories on GitHub.com , including GitHub Enterprise Cloud .

Previously, FinOps practices were often introduced too late in the development lifecycle, leading to misalignment between Finance and Engineering. This delay forced costly rework, as teams relied on manual reviews or post-deployment audits to catch cost inefficiencies and policy violations– resulting in overspending, compliance risks, and unexpected remediation tasks for engineers.

Cloudability Governance integrates with GitHub and Terraform to bring FinOps policy enforcement and cost visibility into the CI/CD pipeline. Key capabilities include:

- Pre-deployment Cost Estimation : Real-time AWS cost estimates, including custom pricing and EA discounts, directly in GitHub and Terraform workflows.

- Get Cost Optimized Resource Selection : Recommendations for lower-cost EC2 and RDS alternatives with similar configurations.

- Policy Enforcement at IaC Level : Enforce mandatory tags, block legacy resources, and set budget thresholds.

- Compliance Monitoring : Centralized dashboard to track adherence to FinOps policies.

- PR Management : Identify and review non-compliant pull requests with built-in approval workflows.

- Run Task Integration with HCP Terraform : Seamlessly integrate Cloudability Governance as a Run Task in HCP Terraform workspaces. This allows policy checks to be automatically triggered during the plan phase of a Terraform run, enabling advisory or mandatory enforcement before infrastructure is provisioned.

This feature shifts cloud cost management from reactive to proactive—helping teams prevent overspending and policy violations before infrastructure is deployed.

For more information about the feature, please review Cloudability Governance documentation .

### Support for Effective Cost Basis in Rightsizing Explorer - January 14, 2026

Cloudability has added support for effective cost basis in Rightsizing Explorer. Cloudability users can now view rightsizing recommendations by either on-demand or effective cost when reviewing rightsizing opportunities in Explorer.

### Cloudability Rightsizing Adds Support for AWS Unattached ElasticIP Addresses - January 9, 2026

Cloudability has added AWS ElasticIP addresses support in Rightsizing. Cloudability users can now receive recommendations to terminate unattached ElasticIP addresses as part of their broader workload and resource optimization initiatives

No new permissions are needed for these recommendations, customers may begin to see these recommendations populated immediately. These recommendations will also be visible in the Rightsizing Explorer page and can also be linked to Rightsizing ROI tickets like other recommendation types.

---
