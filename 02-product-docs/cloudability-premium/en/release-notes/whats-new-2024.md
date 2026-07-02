---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "release-notes"
title: "Cloudability: What's new in 2024"
breadcrumb:
  - "Cloudability Premium"
  - "What's new in Cloudability"
source_path: "release-notes/whats-new-2024.html"
images:
  - "images/cca-kubernetes129.jpg"
  - "images/cld_sustainability_metrics.jpg"
  - "images/container-cost-allocation-1.jpg"
  - "images/container-cost-allocation-2.jpg"
  - "images/container-kubernetes1.3.jpg"
  - "images/container_1.jpg"
  - "images/container_2.jpg"
  - "images/covergae-modal-commitmnet-portfolio.jpg"
  - "images/cur-1.jpg"
  - "images/cur-3.jpg"
  - "images/data-reprocess-1.jpg"
  - "images/focus-2.jpg"
  - "images/ibm_cloud_billing.jpg"
  - "images/kube_1.31.jpg"
  - "images/ms_azure_edited.jpg"
  - "images/oci2.jpg"
  - "images/oci3.jpg"
  - "images/oci_1.jpg"
  - "images/pod-level_visibility.jpg"
  - "images/vc1.jpg"
  - "images/vc2.jpg"
  - "images/vc3.jpg"
  - "images/vc4.jpg"
  - "images/vc5.jpg"
  - "images/vc6.jpg"
  - "images/workload-planning-gpu-1.jpg"
  - "images/workload-planning-gpu-2.jpg"
  - "images/workload-planning-oci-1.jpg"
  - "images/wp11.jpg"
  - "images/wp12.jpg"
  - "images/wp13.jpg"
  - "images/wp2.jpg"
  - "images/wp_1.jpg"
  - "images/wp_2a.jpg"
  - "images/wp_3.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability: What's new in 2024

## Statistical Filtering of Resource Inventory UI – 25 December, 2024

With this release, we introduced a new option in the Resource Inventory UI (both AWS and Azure)
which allows you to choose and display a subset of Resource Inventory data. From the inventory data
generated for a specific service and time period, you can now choose to display a subset of that
data, whether it is the top x number or the top x percentage of resources based on your preferred
cost or utilization metric.

For example: Resource Inventory displays 1000 records for EC2 service for a period of seven
days. You can further filter this display by choosing to view only top 25% of these resources, based
on Cost (Total). Applying this filter would then return the top 250 resources based on Cost (Total),
sorted from highest to the lowest.

## Public API Support for Resource Inventory - 24 December, 2024

Today, we rolled out support for public API end points for both AWS and Azure Inventory data
which are currently available through the Cloudability UI. This release addresses the needs of those
customers who want to pull the data programmatically. Previously, these data could only be accessed
from the Cloudability UI.

## vCPU Hours Metric in Cloudability - December 20, 2024

Today, we are excited to announce the expansion of the vCPU Hours metric in to include support
for Google Cloud Platform (GCP). Building on the launch of this metric for AWS earlier this year,
users can now gain deeper insights into their GCP resource utilization as well.

vCPU Hours metric provides enhanced visibility into resource utilization, enabling more precise
cost attribution and informed capacity planning. By calculating the total running time of vCPUs
across resources, it empowers you with the understanding and capability to optimize workloads
effectively.

We are working to extend support for the vCPU Hours metric to Azure, Oracle Cloud Infrastructure
(OCI), and IBM Cloud in 2025 and 2026.

## Commitment Support for GCP Cloud SQL CUDs - December 19, 2024

Today, we delivered support for GCP Cloud SQL CUDs.

This is the third GCP commitment type we support along with Compute Engine CUDs and Compute
Engine Flex-CUDs. GCP Cloud SQL CUDs are a spend-based commitment where you commitment to a $ amount
you wish to cover in exchange for a discount on on-demand prices. They work similarly to GCE CUD
types in that they stack with custom negotiated pricing. Note that the Cloud SQL discount can also
be negotiated and is frequently made less advantageous when large custom discounts are negotiated.

## Enhanced GCP Commitment Recommendations User Interface - December 19, 2024

Today, Cloudability introduced an enhanced user interface experience across GCP Commitment
Recommendations.

The user experience was an improvement from the existing Compute CUDs implementation in the form
of the Enhanced GCP Commitment Recommendations User Interface.

In addition, GCP only delivered the Compute Flex-CUDs earlier. We have included support for
Resource-based Compute CUDs as well which carries a much higher savings rate in our new and enhanced
user interface experience.

## Shared Cost Allocation for Kubernetes Constructs - Container Insights UI - December 18, 2024

Today, we introduced  Shared Cost Allocation  in the Container Insights
UI. This new feature transforms how shared infrastructure costs, such as system proxies and
monitoring tools, are tracked and allocated within Kubernetes environments.

Key Highlights

- Granular Visibility  : Allocate shared costs to specific Kubernetes
  namespaces, providing transparency for application owners and cost centers
- New Metrics  : View allocated shared costs in the UI with metrics such as
   Shared Cost  ,  Network Shared  , and 
  Memory Shared  among others
- Flexible Rules  : Define and manage shared cost allocation rules for
  organization-wide or cluster-specific configurations

Start Date  : Shared costs will be calculated only from the feature launch
date. Queries before this date will display empty results in the Shared Cost column.

Rule Behavior  :

- Rules apply to future dates (in UTC) and are not retroactive
- Updates or deletions take effect on their scheduled date
- Multiple rules work in a union relationship across namespace

For detailed configuration steps and clarifications, refer to Help Center.

Note: This feature ensures a precise cost allocation, helping you improve showback and chargeback
accuracy for shared resources.

## Container Cost Allocation Now Supports Kubernetes 1.31 Version - December 18, 2024

Container Cost Allocation is now officially supported on Kubernetes version 1.31 across all
providers. This feature allows customers to gain detailed insights into their container resource
usage and associated costs for clusters running on Kubernetes 1.31.

![Containers CA screenshot](../../../../03-media/cloudability-premium/images/kube_1.31.jpg)

## Cloudability Container Insights: Introducing Granular Pod-Level Visibility - December 17, 2024

With this release, Cloudability now provides detailed pod-level cost and usage insights within
your Container Insights feature. This enhancement allows you to drill down through a comprehensive
hierarchical visualization, offering unprecedented granularity in container cost analysis.

Key Capabilities

- Granular cost tracking  : Gain visibility into cost and usage metrics at pod
  level
- Hierarchical navigation  : Seamlessly explore from Cluster → Namespace →
  Workloads → Pods and containers
- Detailed insights  : Understand cost allocation and resource utilization
  with unprecedented depth

![Pod level Screenshot](../../../../03-media/cloudability-premium/images/pod-level_visibility.jpg)

This release will surface the pod-level visibility from the date of release and will not reflect
historical time periods.

## Cloudability for IBM Cloud – Cost Management (GA) - December 13, 2024

Today, Apptio announces the GA launch of IBM Cloud integration into Cloudability. This release
provides FinOps practitioners with seamless and native access to IBM Cloud cost with direct usage
data within Cloudability.

How this feature can help you

This release enables IBM Cloud customers to:

- Allocate IBM Cloud costs back to business based on specific rules, leveraging Cloudability
  business dimensions automatically.
- Analyze their IBM Cloud spend and improve team ownership by leveraging resource-level analytics,
  interactive multi-cloud dashboards, and personalized views.
- Drive financial accountability by setting up IBM Cloud budgets and event notifications.

![True Cost Explorer](../../../../03-media/cloudability-premium/images/ibm_cloud_billing.jpg)

How to manage your IBM Cloud spend

IBM Cloud customers can start their cost management journey by adding credentials for their
account.
Cloudability will ingest IBM Cloud data of the current month once your credentials are validated.
For additional historical data ingestion, complete  [these steps](https://cloud.ibm.com/docs/account?topic=account-exporting-your-usage&interface=ui#access-historical-data "(Opens in a new tab or window)")  and then reach out to the Apptio Support team. Check the
 [API
documentation](../api-v3/getting_started_with_the_cloudability.html)  for programmatic access to manage IBM Cloud credentials. Join the conversation
on the  [Apptio Community](https://community.apptio.com/communities/apptioproducts?communitykey=f67c7e7c-be1c-4053-9845-2376da697342 "(Opens in a new tab or window)")  for more information.

More information about this release

In this release, we’ve also added additional custom tags specific to IBM Cloud, which can be
used as additional dimension for reporting:

- Resource Group Name: cldy:ibm:resourcegroupname
- Resource Group ID: cldy:ibm:resourcegroupid
- ClusterID: cldy:ibm:clusterid
- Plan ID: cldy:ibm:planid
- Consumer ID: cldy:ibm:consumerid
- Instance Name as ‘Resource Name’

With this GA launch, the spend managed by IBM Cloud in Cloudability will be included in your
Monitored Costs, and will be subject to your contracted Monitored Cost Limit.

## Shared vendor credentials between Cloudability Premium and Turbonomic - December 10, 2024

Today, CSP (AWS, Azure and GCP) and APM (Datadog, New Relic) accounts created in Cloudability as
a part of its Premium package will now be shared with Turbonomic . With this release, Cloudability
Premium customers do not need to configure the same cloud accounts in Cloudability and Turbonomic
tools saving significant configuration time.

Subsequent releases of Cloudability Premium build on this release to share and exchange data.
Provisioning clusters flow in Cloudability is undergoing a minor change which now allows two
different agent installation scripts to be downloaded – Cloudability and Turbonomic agents on the
cluster being provisioned in Cloudability.

Features

Cloudability Administrators can now can request additional permissions required for Turbonomic
to integrate with Cloudability. as a part of Cloudability Premium

deployment. When adding CSP accounts (AWS, Azure or GCP), additional permissions are sought that
Turbonomic requires to connect the same CSP accounts as a part of billing reports (basic
credentials), utilisation reports (advanced credentials) or can opt to provide additional
permissions for Turbonomic to execute actions or automate them via policies.

In the case of existing Cloudability customers upgrading to Cloudability Premium , all the
existing CSP accounts need to be edited, additional permissions granted and re-verified in order to
have the same cloud accounts continue to collect and process data.

In the case of APM accounts (Datadog, New Relic), additional inputs need to be provided (and
re-verified in case of existing Cloudability customers upgrading to Cloudability Premium ).

While provisioning clusters in Cloudability , administrators will get an option to download
Cloudability and Turbonomic Kubernetes agent installation scripts. Both agents need to be running
for Kubernetes cost allocation (from Cloudability ) and cost optimization recommendations (from
Turbonomic ) to run seamlessly.

How this feature can help you

The same CSP accounts and APM accounts need to be configured in both Cloudability and Turbonomic
for these two products to collect, ingest and process billing and utilization data from these
sources. To save configuration time, we allow the CSP and APM account configuration once in
Cloudability which both the products can leverage and save configuration time for the
administrators. Once the accounts are configured and verified in Cloudability, these account
configurations are shared with Turbonomic that allows Turbonomic probes to run seamlessly.

Similarly, while provisioning Kubernetes clusters, Cloudability administrator is presented with
option to download both Cloudability and Kubernetes installation scripts with installation
instructions. Once both are installed, only then both cost allocation and cost optimization features
work for Kubernetes clusters in Premium deployments.

## AWS S3 Rightsizing - Glacier Instant Retrieval Storage Class Support - November 26, 2024

Today, Cloudability launched support for AWS S3 Glacier Instant Retrieval rightsizing
recommendations. Customers will now start receiving rightsizing recommendations for the Glacier
Instant Retrieval storage class along with the rest of the currently supported S3 classes.

Before this release, recommendations for this S3 class were not supported.

Where to find the new functionality

No additional setup is required to start receiving these recommendations as long as Cloudability
is correctly Connected to Amazon Web Services.

For using the new feature, follow the steps:

1. From Cloudability home, navigate to Optimize menu and select Rightsizing.
2. Select the AWS tab on the Rightsizing page and select the S3 sub-tab. Rightsizing
   recommendations for Glacier Instant Retrieval will be present in the list of recommendations if they
   exist and are not being filtered out.

How this feature can help you

Amazon S3 offers a range of storage classes you can choose from, based on the performance, data
access, resiliency, and cost requirements of your workloads. In order to provide rightsizing
recommendations for the lowest cost storage across different access patterns, recommendations will
now be provided for the Glacier Instant Retrieval storage class in additional to the other classes
currently supported by Cloudability. The Glacier Instant Retrieval storage class is typically used
for archive data that needs immediate access.

## Cloud Sustainability Metrics - November 25, 2024

Today, Cloudability launched multi-cloud cloud sustainability metrics in limited availability\*.
Starting today, you can quickly and easily view these metrics to get insights into their public
cloud carbon emissions.

Where to find these metrics

These new metrics are available within Cloudability reports and dashboards and Apptio BI.

- Estimated Carbon Emissions (MTCO2e): This metric captures the estimated carbon emissions in
  metric tons of carbon dioxide equivalents.
- Power Consumed (kWh): This metric captures the power consumed in kilo watt hours.

These metrics are available at a resource level for the supported services.

| AWS | Azure | GCP | OCI |
| --- | --- | --- | --- |
| EC2 | Compute (non GPU) | GCE | Compute (non GPU) |
| EBS | Managed Disk | Persistent Disk |  |
| RDS | Azure Database | Cloud SQL |  |

These metrics can also be clubbed with the various Cost metrics available to get a view of
both carbon and cost together for a resource or other dimensions such as vendor, region and service
among others.

You should be able to use this with your existing configurations of views,
business mappings, account groups or tag mappings. These are also available via exports and
Cloudability APIs.

Steps to use these metrics

We have configured a default dashboard within Cloudability to get started under 
All Dashboards  called  Sample Cloud Sustainability Dashboard  .

For using the cloud sustainability metrics:

1. Navigate to Cloudability Home.
2. Click New report/ Add Widget.
3. Under Cloudability metrics section, scroll to Sustainability category.
4. Select metrics.

![Cloud Sustainibility Metrics](../../../../03-media/cloudability-premium/images/cld_sustainability_metrics.jpg)

\*Limited availability: It indicates that all features and functions are available, however they
are being released only for a segment of customers currently. This will be scaled up to all the
customers in the coming months.

Note:

These metrics are available only to customers having Cloudability Enterprise, Cloudability
Standard and Cloudability Premium SKU’s.

## Self-service Data Reprocess - November 22, 2024

Today, we announce the general availability of the Self-Service Data Reprocess feature for our
Cloudability customers.

This feature allows you to reprocess your data, without relying on
Support or Customer Success teams. Compared to the request-based process, this feature offers faster
turnaround time, eliminates manual steps, enhances transparency for user requests, and improves the
overall experience.

With this release, we have also addressed a critical issue where the
reprocessed data was not immediately reflected in Reports after job completion, causing delays in
viewing updated information. Now, after the job is completed you can query the reprocessed data in
Reports immediately. Additionally, the  Job Status  tab displays the job
completion time and the  Reason  field.

During the initial rollout, we received
feedback on some user experience and product gaps from customers exporting their Cloud Data from
Cloudability (or via CDI) to Costing & Planning . Therefore, we decided to put this feature on
hold for customers using Cloudability or CDI to Costing & Planning integration, however it will
be available to customers who only have Cloudability. We are actively working on enhancing the
experience and expect to launch the improved feature early next year. Cloudability customers with
Costing & Planning who had access during the initial rollout will continue to retain that access

The feature is not enabled by default as this is an Opt-in feature. Reach out to Support
Team to get access to the feature.

More information about the feature

The feature, when enabled, can be accessed by navigating to   Organize
  >   Data Reprocess in Cloudability

![Data Reprocess](../../../../03-media/cloudability-premium/images/data-reprocess-1.jpg)

For Cloudability only customers, this is a two-step process for Reprocess where you can select
the  Period  and submit the job. You can also monitor the status of the job
in the  Job Status  tab. For detailed steps, refer to
[Data Reprocess for Cloudability users](../product/data_reprocess.html#data_reprocess__Data).

For Costing & Planning customers with  Cloudability or CDI:  The feature is on
hold  . Refer to 
[Data Reprocess for Cloudability - Costing & Planning users](../product/data_reprocess.html#data_reprocess__Data2) .

## Enhanced Coverage Modal across GCP Commitment Portfolio - November 19, 2024

Today, we released the enhanced coverage modal across the GCP Commitment Portfolio.

This enhancement both improves the exiting coverage modal previously released on the GCP
Flex-CUDs Commitment Portfolio page and extends this modal across all GCP portfolio pages. We
simplified the terminology and broke out the modal into two sections. The coverage percentage
calculation section includes whatever information is necessary to calculate the coverage for the
specific page. The vendor coverage summary section summarizes coverage values at the vendor level
for convenience.

![GCP coverage](../../../../03-media/cloudability-premium/images/covergae-modal-commitmnet-portfolio.jpg)

## Apptio Community Transition to IBM TechXchange - November 1, 2024

Today, Apptio Community has fully transitioned to IBM TechXchange.

The best practices
for maximizing the IBM TechXchange experience are listed below.

- Use and bookmark  [this new homepage](https://community.ibm.com/community/user/apptio/home "(Opens in a new tab or window)")  for the Apptio topic groups.
- Access the topic group that is relevant to your needs; Some of the topic groups with which you
  are familiar have been combined into new topic groups.

The following topic groups are available:

- [Apptio](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=4100dfb8-fc23-4203-83c7-019253cf7c0b "(Opens in a new tab or window)")  : Costing Essentials, Costing Standard (CT-Foundation), Apptio Planning (ITP/ITFMF), Billing (Billing Standard),
  Benchmarking (Benchmarking), ServiceNow Integration
- [Cloudability](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=15c0e07d-35c0-49de-a84b-019253d13376 "(Opens in a new tab or window)")  : Cloudability Financial Planning, Cloudability TotalCost,
  Apptio Turbonomic Integration
- [https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=55a3712d-1835-4ec2-bcd7-603e88cd9dd2](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=55a3712d-1835-4ec2-bcd7-603e88cd9dd2 "(Opens in a new tab or window)")
- [Platform](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8 "(Opens in a new tab or window)")  : Apptio BI, ATUM, Automated Data Management, DataLink,
  Frontdoor, TBM Studio
- [Apptio for All](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=2e85ed45-9b8a-486c-bd55-019253d466eb "(Opens in a new tab or window)")

- Once you are in your topic group, read and contribute to all the usual content such as quick
  links, discussions, questions, and blogs.
- Check out  [these
  resources](https://community.ibm.com/community/user/participate/resources "(Opens in a new tab or window)")  on how to navigate and utilize community.
- Start submitting Requests for Enhancements on  [IBM Ideas](https://login.ibm.com/idaas/mtfim/sps/idaas/login?client_id=nwnjmzc5njetmzlkyi00&target=https%3a%2f%2flogin.ibm.com%2foidc%2fendpoint%2fdefault%2fauthorize%3fqsid%3dc75ff073-50e8-4426-8979-7e4b6b992e80%26client_id%3dnwnjmzc5njetmzlkyi00 "(Opens in a new tab or window)")  .

  - IBM uses a unified ideas portal at   [ideas.ibm.com](https://ideas.ibm.com/ "(Opens in a new tab or window)")   for you to raise ideas against all products. As of today,
    that list has expanded to include the products recently acquired from Apptio. Ideas submitted prior
    to the acquisition will be made available to product teams and may be added to the portal at a
    future date to ensure continuity.

Contact the community team at our new email,   [support@communitysite.ibm.com](mailto:support@communitysite.ibm.com "(Opens in a new tab or window)") 
with any questions or needs.

## Third-Party Vendor & FOCUS Support - October 29, 2024

Today, we launched cost management for third-party cloud vendors natively within Cloudability.

This represents a significant enhancement to Cloudability, simplifying how FinOps practitioners
manage cost for vendors like Datadog, Databricks and Snowflake. Having this cost and usage data
natively in the Cloudability platform makes it available to capabilities like Business Mapping,
Views and Dashboards. Depending on the vendor, this data can either be ingested using a direct
connector or via the industry adopted FOCUS schema.

This release enables Cloudability customers
to:

- Ingest Datadog, Databricks, Snowflake and MongoDB billing data via direct connectors and other
  vendors using FOCUS-compatible exports.
- Allocate these costs back to the business based on their specific rules, leveraging the tag
  mapping, account groups and business mapping capabilities.
- Analyze this spend and improve team ownership with interactive multi-cloud dashboards and
  personalized views.
- Drive financial accountability by setting up budgets and event notifications.

![Focus in TCE](../../../../03-media/cloudability-premium/images/focus-2.jpg)

FOCUS ingress

Cloudability customers can now gain flexibility by
importing costs and usage data from any data sources or additional vendors that are not yet
supported via direct connectors. The billing data needs to be converted into the FOCUS format and
uploaded into AWS, Azure or GCP storage accounts. Once the credentialing process is validated,
customers will be able to report on this additional spend and allocate it back to the business.

Start Managing your Third-Party Vendor Spend today

You can start your cost management journey by adding credentials for your accounts following the
instructions in the Help Center for  [Datadog](../admin/connect-datadog-cost-usage_data.html)  ,  [Databricks](../admin/connect-databricks.html)  ,  [MongoDB](../admin/connect-mongodb.html)  ,  [Snowflake](../admin/connect-snowflake.html)  , and  [FOCUS ingress](../admin/connect-custom-data-focus-ingress.html) . By default, Cloudability will ingest the current month of data after your credentials are
validated. If you would like additional months of data ingested, please reach out to the Apptio
team.

## Workload Planning - Workload Templates - October 24, 2024

Today, we introduced Workload Planning Templates, which allow users to create workloads that can
be easily shared as templates across their organization.

Workload Templates can be used for application customization, to promote approved configurations
and resources for new applications with other users or share specific workload examples. These
templates are managed by Cloudability Admin users and anyone in the organization can duplicate them
so that they can be used for new application planning.

Previously, Workload Planning users could share workloads, but they were not visible across the
organization by default. With this release, the FinOps teams, as well as the architect or the
engineering teams can easily manage and share approved configurations within Cloudability.

Creating Workload Planning Templates

To create a template, Cloudability Admin users can simply create a workload, add the required
resources, and select  Save as Template  in the  Summary
 step. Users can export a template as well as duplicate it to edit the copy.

## AWS Rightsizing - "Available MBytes" memory collection support - October 23, 2024

Today Cloudability launched AWS rightsizing support for consuming memory utilization metrics via
the “Available Mbytes” metric in the CloudWatch agent for AWS Windows machines.

Starting today, customers can use the  Available Mbytes  metric
configuration to provide Cloudability with more precise memory data to use in rightsizing
recommendations.

Before this release, Cloudability AWS rightsizing only supported consuming AWS memory
utilization metrics for Windows machines using the “% Committed Bytes In Use” metric. Both metrics
will be supported moving forward.

More information about this release 

To enable the “Available Mbytes” memory metrics for consumption, follow these steps:

1. From Cloudability , navigate to the  Optimize  menu, and then select
    Rightsizing  .
2. Select the  AWS  tab on the Rightsizing page which defaults to
    EC2  .

Available memory metrics are displayed on a graph in the details pane of the rightsizing
recommendation.

AWS has multiple options available for inclusion of memory metrics in the CloudWatch agent.
Although support had already been available to consume memory metrics for Windows machines using the
“  % Committed Bytes In Use  ” metric, some customers had already configured
the “Available Mbytes” metric and therefore were not seeing memory metrics in their rightsizing
recommendations. In additional to providing more flexibility for customers, “Available Mbytes” is
actually a more precise memory metric because it directly represents how much RAM is free as opposed
to the “  % Committed Bytes In Use  ” metric that represents both physical
memory and virtual memory and therefore has the potential to be the lesser accurate assessment.

## Compute Group Rightsizing – Top count reduction filtering option - October 22, 2024

Today, Cloudability launched a new page-level filtering option for compute group rightsizing
pages (AWS EC2 ASG, GCP GCE MIG) that provides a new method of filtering recommendations.

Earlier, the Top Count Reduction option when selected would filter recommendations displaying an
instance count reduction, if they exist, for the current instance type. The other recommendation
options for an instance, if they exist, will display in the details pane as usual after the top
recommendation. This allows an easy and quick way to show cost savings achieved by reducing the
number of instances in a compute group without making other changes.

Where to find this new functionality

1. In the Cloudability primary navigation menu, navigate to  Optimize  and
   select  Rightsizing  .
2. Select the  AWS  or  GCP  tab on the 
   Rightsizing  page and navigate to the compute group sub-tab (  EC2 ASG
    or  GCE MIG  ).
3. Select the  Options  drop-down menu, and select  Top Count
   Reduction  to filter the recommendations.

More information about this release

There was already functionality available for customers to filter compute group recommendations
so that only ones with count reductions were displayed. However, this still required more thought
and effort to switch instance types when the recommendations called for it. This new feature filters
recommendations to present only those instances where the instance type remains unchanged but an
instance count reduction is suggested as the leading recommendation. This enables clients to swiftly
identify and capitalize on "low hanging fruit" savings, which necessitate only a reduction in the
compute group's instance count. These recommendations are also displayed as the top recommendation
for ease of use.

## Additional OS Type Support for Virtual Machines in Workload Planning - October 21, 2024

Today, we released the support of new OS types in Workload Planning across cloud providers. With
this enhancement, users can get estimates and VM recommendations based on the following 11 operating
systems:

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

Before this release, Workload Planning only supported  Windows  and
 Linux  OS options limiting the results for  Compute 
recommendations. With the ability to visualize VM resources across more OS types, users are now able
to find more cost-effective options for their workloads comparing across multiple vendors.

## Daily Granularity Support for Resource Inventory data - October 14, 2024

Today, we introduced daily granularity support for Resource Inventory data for Cloudability.
Previously, Resource Inventory supported only monthly aggregated data for all its measures
(Dimensions and Metrics).

With this release, users will be able to view daily Resource Inventory data for a specific date
range using the date picker in the application. (Minimum of 1 day and Maximum of 31 days per report)

## Introducing Billing Admin Permission in Cloudability - October 9, 2024

Today, we introduced a new Front Door permission called "  OrgCurrencyFeatureAccess
 " for Cloudability. This permission allows users access the  Currency
 tab under the managed profile.

With this permission, users can set the default currency for the organization. Currently, this
permission is set from the Active Admin portal. Moving it to the Front Door will help us centralize
all our permissions there.

Note: The billing admin permission in the Active Admin portal is available until January 31, 2025,
after which it will be deprecated.

## Introducing  Cloudability  in Middle East Region - September 30, 2024

Today, we introduced the hosting of  Cloudability , our cloud cost management platform, within
the Middle East region, located in UAE data center.

How this feature can help you

This release addresses the unique needs of our Middle-East region based clients, ensuring their
data remains within the regional boundaries. By localizing our services, we aim to empower
organizations to bolster their compliance efforts and align with the guidelines regarding cloud cost
management data.

More information about the release

The launch of hosting  Cloudability in the Middle East region holds great significance for our
customers operating within this region. It provides a reliable and compliant cloud cost management
solution that prioritizes data residency, enhances data privacy, and aligns with data protection
guidelines.

Note: Customers, based in the Middle East region, interested in migrating from the US/ EU to the
Middle East region can reach out to their respective Account managers or Customer Success team. No
additional setup or installation is required for customers who are directly onboarding to 
Cloudability  in the Middle East region.

## Commitment Expiration Alerts Added for all supported Commitment Types - September 27, 2024

Today, Cloudability commitment-based discounts announces support for expiration alerts for all
previously unsupported commitment types, including  AWS Savings Plans  ,
 Azures Saving Plans  ,  GCP Compute Engine CUDs  ,
and  GCP Compute Engine Flexible CUDs  .

Additionally, the email template was updated to support vendor-agnostic terminology and
additional fields to enhance the alert.

## Cloudability - Fine Grained Permissions for Views - September 26, 2024

Today, we are implementing two enhancements with this release.

- Adding a new permission in Front Door called  ViewsFeatureCreateOwnViewsAccess
   that would allow a user assigned to this permission to create/update/delete views that
  are created by them with read only access to views created by others.
- Previously a non admin user (custom role) assigned with  ViewsFeatureFullAccess
   was not able to edit views created by others. With this release, users with this role
  will be able to update/ delete any views added in their Cloudability organization.

The impact to the existing customers would be that any user role in their organization be it an
admin level role or custom role with the permission  ViewsFeatureFullAccess 
will now be able to edit or delete any Views created by anyone in their organization. If they want
to constraint this access, then those users will have to be assigned with a custom role 
ViewsFeatureCreateOwnViewsAccess  permission. If both  ViewsFeatureFullAccess
 and  ViewsFeatureCreateOwnViewsAccess  are assigned to the same
role, then  ViewsFeatureFullAccess  being the higher privilege gets
precedence.

## Cloudability Container Insights: Introducing support for Dashboard sharing - September 19, 2024

Today, we are excited to announce the release of the Dashboard Sharing feature for Container
Insights 2.0, designed to enhance collaboration and streamline access to critical container metrics
across your organization.

Key Highlights

- Share Custom Dashboards:  Users can now share their custom dashboards
  internally with their entire organization or specific team members, allowing for broader
  distribution of insights.

- Dashboard Permissions:  Fine-tune access control by assigning one of the
  following roles:

  - Editor: Can modify the dashboard and manage sharing permissions.
  - Viewer: Has view-only access, with no ability to edit or share the dashboard.

Permissions are easily managed and tracked in real-time, providing transparency over who can
access and modify each dashboard. The Owner of the dashboard retains full control, including the
ability to edit, share, and delete the dashboard.

- Starring and Favorites:  Users can mark dashboards as favorites, making them
  easily accessible from a dropdown list. Starred dashboards appear at the top of the list, sorted
  alphabetically for quick access.

- Improved Collaboration:  Facilitate seamless teamwork by enabling colleagues
  to contribute to shared dashboards, whether through editing or viewing. This ensures that everyone
  has access to the most up-to-date insights. While Viewers cannot filter or move widgets on the
  dashboard, they can use the "Save As Dashboard" option to create a new dashboard based on the
  original, allowing them to explore the data and customize it to their needs.

How to Get Started

1. Create a Dashboard:  Build a custom dashboard by adding key metrics and
   widgets that meet your needs.

1. Share:  Use the dashboard sharing option to grant access to the entire
   organization or specific team members, assigning appropriate roles.

![CCA screenshot](../../../../03-media/cloudability-premium/images/container-cost-allocation-1.jpg)

1. Manage Permissions:  Control and update who can view, edit, or manage the
   dashboard using intuitive settings.

![share dashboard containers](../../../../03-media/cloudability-premium/images/container-cost-allocation-2.jpg)

This feature simplifies the sharing of critical container metrics, making insights more
accessible and actionable across teams. By enhancing collaboration, teams can drive better
decision-making and ensure everyone is aligned on key container data.

## Resource Name dimension added for GCP Resource Level Billing - September 17, 2024

Today, we launched a new reporting dimension  Resource Name  across
Cloudability analytics. This launch is currently for GCP but will be updated for Azure and OCI soon.

What’s new in this release

This dimension represents the name that is assigned to GCP resources, such as VM instance name,
disk name, or a database name. This detail matches with what users see in the GCP console when
interacting with resources and aligns with the  Global Resource Name  column
within GCP Resource Level Billing. This is the first of several releases that will serve as
foundational updates to our support for commitment-based discounts.

Benefits to users

Cost attribution for resources  : Users can immediately associate costs with
their infrastructure.

User-friendly reports and dashboards  : Users will have more clarity in
reporting, removing the need to parse out unnecessary details like full API paths.

## Consolidated Commitment Portfolio and Enhancements - September 12, 2024

Today, we released three enhancements to the commitment portfolio, spanning across each of the
three supported vendors.

What’s new in this release

- Consolidated Commitment Portfolio  : The "Reservation Portfolio" and "RI
  Planner" pages are updated to "Commitment Portfolio" and "Commitment Recommendations" respectively
  to reflect vendor-agnostic nomenclature. Additionally, support for spend-based commitments are now
  consolidated under vendor in the single portfolio page with the commitment pages reorganized
  together under  Optimize  .
- AWS & Azure Savings Plans Portfolio Enhancements  : The table and KPIs
  are updated, and the details panel is added to match their reserved instance counterparts.
- GCP Portfolio Enhancements  : “All Commitments” and “All Compute” pages are
  now added to convey performance at an aggregate level. Updated KPIs on the resource-based Compute
  CUDs portfolio page now match GCP Compute Flex CUDs. Finally, grouped and ungrouped tables convey
  ownership and how sharing impacts performance.

This is the first of several releases that will serve as foundational updates to our support for
commitment-based discounts. For more information about commitments, see  [Getting started with Commitment Portfolio](../product/commitment-portfolio.html)  .
Join in the discussion in our  [Community announcement](https://community.apptio.com/login?returnurl=https%3a%2f%2fcommunity.apptio.com%2fviewdocument%2fnotice-upcoming-launch-consolidate%3fcommunitykey%3df67c7e7c-be1c-4053-9845-2376da697342%26tab%3dlibrarydocuments "(Opens in a new tab or window)")  .

## RIS Column support for Business Dimensions - September 5, 2024

With this release, resource inventory users have the ability to add business dimensions as a
column in the Cloudability UI for their inventory reports.

This would help them compare their inventory data along with the business dimensions created in
their organization.

## Cloudability Container Insights - Introducing the Efficiency Score (Usage) KPI - September 3, 2024

With this release, Cloudability has introduced a new KPI metric,  Efficiency Score
(Usage)  , which offers a clear and actionable view of cost efficiency across all
resources within a container, namespace, workload, cluster, and more. This metric is available as a
predefined option that users can easily add to their dashboards by selecting it from the predefined
widget category under the  Add Widget  section.

What is Efficiency Score (Usage)

Efficiency Score (Usage) is calculated by comparing the cost of actively consumed resources
(usage) to the total cost of reserved resources (provisioned or allocated). This score helps teams
assess how effectively reserved resources are being utilized and highlights inefficiencies such as
over-provisioning, or underutilization. A higher score indicates better resource efficiency, while a
lower score reveals areas for potential optimization.

This KPI is designed to provide teams with deeper insights into their resource utilization,
supporting decisions around resource allocation, rightsizing, and optimization strategies.

## Cloudability for IBM Cloud – Cost Management (Beta) - August 30, 2024

Today, Apptio announces the launch of IBM Cloud integration into Cloudability. This release
provides FinOps practitioners with seamless and native access to IBM Cloud cost with direct usage
data within Cloudability.

How this feature can help you

This release enables IBM Cloud customers to:

- Allocate IBM Cloud costs back to business based on specific rules, leveraging Cloudability
  business dimensions automatically.
- Analyze their IBM Cloud spend and improve team ownership by leveraging resource-level analytics,
  interactive multi-cloud dashboards, and personalized views.
- Drive financial accountability by setting up IBM Cloud budgets and event notifications.

![IBM Cloud dashboard](../../../../03-media/cloudability-premium/images/ibm_cloud_billing.jpg)

How to manage your IBM Cloud spend

IBM Cloud customers can start their cost management journey by adding credentials for their
account
.
Cloudability will ingest IBM Cloud data of the current month once your credentials are validated.
For additional data ingestion, reach out to the Apptio team. Check the  [API documentation](../api-v3/getting_started_with_the_cloudability.html) for programmatic access to manage IBM Cloud credentials. Join the conversation on the  [Apptio Community](https://community.apptio.com/blogs/alok-jain/2024/08/26/cloudability-for-ibm-cloud-cost-management-faq "(Opens in a new tab or window)")  for more information.

 More information about this release 

You will not be charged for IBM Cloud managed cloud spend during the Deta period. However, the
spend managed by IBM Cloud in Cloudability will be included in your Monitored Costs post GA launch
and will be subject to your contracted Monitored Cost Limit. Currently, the GA launch is scheduled
for November 15, 2024 and subject to change to a later date.

## GCP Rightsizing – Detailed level billing support - August 28, 2024

With this release, Cloudability has launched support for detailed level billing in GCP
Rightsizing which enables several new elements of functionality not available earlier.

Starting today, users having GCP detailed level billing enabled will notice that GCP Rightsizing
now has:

- An “Effective” cost basis option for Compute recommendations
- Support for Views that are based on tag mappings, business mappings, and account groups
- Support for Filtering based on tag/business mappings
- Viewable resource tag mappings from the details pane of the recommendation
- Exports that contain resource tag mappings

Before this release, Cloudability GCP Rightsizing did not have a way to access the granular data
needed in order to provide these CSP feature parity support items.

This functionality was already available for customers in the applicable areas of rightsizing
for AWS and Azure but was not available for GCP. The same problems incurred with AWS and Azure
rightsizing without these features are now solved here for GCP as well. Effective cost basis takes
into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate
the cost for the current resource type over the reporting period. Support for Views and Filtering
based on tag mappings, business mappings, and account groups provide users with the ability to
create and view a more customized experience and data set. Viewable resource tag mappings allow
users to see which tag mappings are associated with a resource in order to make a more informed
decision on a recommendation. Exports that contain resource tag mappings also provide users with
this additional information which can then be used in any capacity in which the exports are used by
the customer.

How to enable GCP detailed level billing

To set up GCP detailed level billing, see  [Add a new account credential for Detailed
Billing](../admin/connect-google-cloud.html)  .

Also note that support for GCP detailed level billing does not currently include GKE cluster cost data.

Where to find this new functionality

1. From Cloudability primary navigation menu, navigate to the  Optimize 
   menu item and select  Rightsizing  .
2. Select the  GCP  tab on the Rightsizing page. Additional functionality
   provided in this release will be available here.

## UI Enhancements for Resource Inventory - August 26, 2024

With this release, we have standardized the Resource Inventory UI specific to the elements as
part of the overall platform standardization and accessibility compliance.

These elements are as below.

1. Display style of the AWS and Azure tabs at the top to be consistent with other modules in
   Cloudability.
2. Display style of service and month dropdown and the placeholder texts to be consistent with
   other modules in Cloudability.
3. Font size and thickness.
4. Size and display style of the export and measures icons on the top right of the 
   Inventory  grid.
5. Data loading experience.
6. Display style for the  Show  /  Hide  measures
   (dimensions /metrics) icons.

## Cloudability Container Insights 2.0 Enhancements - August 16, 2024

Global Filter for Label Key/ Value Pairs

We’ve introduced a new global filter option within the Container Insights UI dashboard, allowing
you to filter your cost and usage data based on specific label key/ value pairs. This enhancement
offers a more detailed view of your containerized workloads by enabling filtering according to
labels such as app, env, or any other custom labels you use within your environments.

Key Features

- Label Key filter: Select from available label keys to narrow down your cost data view to
  specific workloads or environments.
- Label Value filter: Refine your filter further by specifying label values, providing precise
  cost allocation insights.

To use this feature, you must provide at least one label value for filtering. You can also
select multiple values to suit your needs. Our goal is to empower you to leverage the labels within
your environments to build intuitive dashboards, enabling deeper insights into your container costs.

![CCA filtering](../../../../03-media/cloudability-premium/images/container_1.jpg)

Customizable Table Widgets

Building on our existing capabilities for custom KPI and chart widgets, we've now introduced
custom table widgets within the Container Cost Allocation dashboard, enhancing your ability to
tailor cost visibility to your specific needs.

This feature allows you to modify and configure table widgets to present data that best suits
your use cases.

Key Features:

- Table Selection: Display cost and usage data by Cluster, Label, Node, or Namespace, providing
  flexibility in how you view and manage your Kubernetes resources.
- Filter Conditions: Customize your table by applying filters based on various measures such as
  Cluster, Namespace, Workload, Container, Node, or specific labels like app, env, project, and more.
  This helps you focus on the most relevant data for your analysis.
- Edit Widget Functionality: Edit existing table widgets easily to adjust the displayed data or
  filter criteria, ensuring your dashboard reflects the most up-to-date and relevant information.
- Export Options: After customizing your widget, you can export the data for further analysis or
  reporting.

![CCA Cluster](../../../../03-media/cloudability-premium/images/container_2.jpg)

## Workload Planning – GPU support for Virtual Machines - July 16, 2024

Today, we released the support of GPU configuration for Virtual Machines in Workload Planning .
With this enhancement, users can effortlessly specify the number of GPUs required for their
workloads and they receive cost estimates and resource recommendations for GPU resources across AWS,
Azure, GCP and OCI.

Before this release, Workload Planning only supported few GPU instances across vendors and did
not offer visibility into GPU-specific requirements. Users are now not only able to compare costs
across vendors, but also visualize configuration details such as the number of  GPU
 s,  GPU Memory  and  GPU Model  (where
provided by cloud service providers) helping them find the most cost-effective GPU resource for
their workloads.

![WP GPU support](../../../../03-media/cloudability-premium/images/workload-planning-gpu-1.jpg)

![WP VM Reco](../../../../03-media/cloudability-premium/images/workload-planning-gpu-2.jpg)

## Support for AWS Cost and Usage report (CUR) 2.0 - July 16, 2024

Today we launched support for AWS Cost and Usage report (CUR) 2.0/ Standard data export in
Cloudability. Starting today, Cloudability users can use AWS CUR 2.0 to ingest their AWS Cost and
usage data.

This enhances the data format supported for AWS Cost and Usage reporting with a couple of
options now:

- AWS Legacy CUR
- AWS Standard Data export/ CUR 2.0

Before this release, Cloudability used to support only  AWS CUR  export
which is now renamed as  Legacy CUR  export by AWS.

Existing customers on AWS legacy CUR can continue with the legacy CUR without any impact on the
data ingestion or availability of data within Cloudability.

How to enable it

Customers would need to configure the CUR 2.0/ Standard Data export in the AWS Console.

Customer should configure the below in AWS Console:

- Standard Data export

- CUR 2.0

  - Include  Resource ID  s
  - Time Granularity  as  Hourly
  - Column selection  -  All  (All columns will be
    selected by default)
  - Compression type  and file format gzip  - text/ csv
  - File Versioning  as  Overwrite existing data export file

Note: Parquet format is not supported with CUR 2.0.

Once the above settings are specified, follow the steps below in Cloudability

1. Navigate to  Settings  >  Vendor Credentials 
   >  AWS  .
2. Select and edit the  Master Payer  account.
3. Add the  New S3  bucket name ,  Cost and Usage report prefix
    ,  Cost and Usage report name  in Cloudability.
4. Save and download the CFT template.
5. Run the CFT template.
6. Verify Credentials.

![Create export screenshot](../../../../03-media/cloudability-premium/images/cur-1.jpg)

![Data Export Screenshot](../../../../03-media/cloudability-premium/images/cur-3.jpg)

## GCP Custom Virtual Machine type support (Windows OS) for Workload Planning - July 11, 2024

Today, we are pleased to announce the introduction of cost estimates for GCP custom VMs with
“Windows" OS in Workload Planning , supporting the N4, N2, N2D, E2 and N1 machine types.

This is an extension of the  [GCP Custom Virtual Machine Type Support](#gcp_custom_virtual_machine_type_support_for_workload_planning_%E2%80%93_june_14,_2024_ "(Opens in a new tab or window)")  release, announced on June 14,
2024.

## View Only Permissions for Budgets module in Cloudability - July 11, 2024

Today, we are pleased to introduce a new user permission in Front Door called 
BudgetsFeatureViewOnlyAccess  which allow users (who are assigned this permission) to
view and subscribe to budgets created in their org.

This permission does not allow users to create new budgets or modify (  Edit
 /  Delete  ) existing budgets.

## Cloudability Container Insights 2.0 - July 11, 2024

Today, we are excited to announce a set of important enhancements to  Cloudability
Container Insights  . Container Insights 2.0 introduces several improvements aimed at
providing comprehensive insights into containerized workloads within Kubernetes and OpenShift
clusters. This release features an updated layout and new capabilities, such as the efficiency
score, and expanded drill-down functionality.

The new UI is the default landing page for the  Container Insights 
feature. However, you can easily toggle between two experiences by clicking the button referenced in
the screenshots below.

![CCA Screenshot](../../../../03-media/cloudability-premium/images/container_1.jpg)

![More CCA](../../../../03-media/cloudability-premium/images/container_2.jpg)

Note:

We are not deprecating the Container Insights 1.0 immediately. You will have the option to
toggle between the two versions for a certain period to allow you get comfortable with the new
interface. We will provide proactive communication about the future deprecation date for Container
Insights 1.0.

Features Introduced

1. Customizable Dashboards 

   We've added customizable dashboards, that
   will allow you to create visualizations, and monitor key performance indicators (KPIs) that matter
   to you.

   Capabilities included:

   - Default Dashboard:  Includes pre-configured widgets for quick insights into
     total cluster cost, idle cost, and other essential metrics. Each user has its own default dashboard.
   - Efficiency Score:  A new metric to assess resource allocation efficiency.
   - Enhanced Visualization:  Includes KPIs, trendlines, top X widgets,
     timeseries charts, and table widgets for a comprehensive view of your container footprint.
   - Customization Features:

     Cloud vendor filter support for dashboard-level filtering

     Multi-select functionality for cluster selectionThis release supports custom dashboard creation, along with various custom widgets types. You
   can also delete and add custom widgets in the default dashboard, and set them as your custom
   dashboards.
2. Treemap View 

   The Treemap View provides a hierarchical visualization
   for clusters, enabling deeper analysis down to the container level:

   - Hierarchical Visualization:  Allows drilling down from clusters to
     namespaces, workloads and containers.
   - Efficiency Score Visualization:  Integrates efficiency scores within the
     Treemap view for quick assessments.

   Both  Dashboards  and the  Treemap View 
   support global filters for date, clusters, and cost basis.   
    Widgets are organized with
   KPIs at the top and tables at the bottom for optimal visibility.

   Detailed Drill-Down Capability

   Our enhanced drill-down functionality allows seamless navigation:

   - From the dashboard, navigate to the table widget, and select a cluster to view its namespaces in
     the Treemap View.
   - Select a namespace in a Treemap to explore constituent workloads.
   - Clicking a workload reveals the containers within that workload.

     At each level of
     granularity, you can understand the different cost components, and efficiency score.

     Additional Information

     For in-depth container details within a workload:

     - Click a container to view the nodes it is operating on.
     - Updates to the details panel provide relevant information for each container grouping, ensuring
       you have access to the most logical details. New Cost Column: Miscellaneous Cost 

     As part of this release, we are introducing a new column on the Container Insights page called
     the 'Miscellaneous Cost' column, available in the Table widget. This column will reflect
     cluster-specific costs, and will initially be null for all Cloud Service Providers (CSPs). We will
     make this available for GCP first, with plans to expand support to other CSPs in the near future.
     These costs encompass additional expenses associated with containerized applications that extend
     beyond nodes, volumes, and data transfer. They include various services and resources necessary for
     cluster operations, providing a comprehensive view of all costs related to running containerized
     applications.
3. Cost Efficiency Score 

   The Cost Efficiency Score is a KPI that measures the overall cost-effectiveness of resource
   allocation within a containerized environment. It compares the utilized cost against what is deemed
   the fair share or total cost. Understanding this score involves examining three main types of costs:
   fair share cost, utilization cost, and idle cost.

    Fair Share Cost / Total Cost 

   Fair share cost represents the proportion of the total node cost attributed to a container based
   on its allocated percentage of each resource (CPU, Memory, GPU). This is calculated by multiplying
   the node cost for each resource by the fair share percentage of that resource allocated to the
   container. The total fair share cost for a container is the sum of these amounts for all resources.

    Utilization Cost 

   Utilization cost reflects the actual cost of resources used by a container. It is calculated by
   multiplying the node cost of each resource by the utilization percentage of that resource on the
   node. Like fair share cost, the total utilization cost for a container is the aggregate of
   utilization costs for all resources.

   Idle Cost

   Idle cost is derived by subtracting the utilization cost from the fair share cost. It
   represents the cost of resources that are allocated but not utilized, indicating inefficiency.

   Cost Efficiency Score Calculation

   The Cost Efficiency Score is calculated by comparing utilized cost to fair share cost,
   encapsulating the efficiency of resource usage across all resources within a container, namespace,
   workload, or cluster. This score helps identify inefficiencies and potential areas for optimization,
   such as cluster or node rightsizing or improving workload pod affinity constraints.

   A lower Cost
   Efficiency Score indicates greater inefficiency, suggesting more significant opportunities for cost
   savings and optimization within the environment.

Note:

Please reach out to support if you have questions around this feature or feedback.

## Container Cost Allocation now supports Kubernetes Version 1.30 - July 8, 2024

Today, we are pleased to announce that Container Cost Allocation is now officially
supported on Kubernetes Version 1.30 across all providers.

This feature allows customers to
gain detailed insights into their container resource usage and associated costs for clusters running
on Kubernetes 1.30.

![CCA X Kuberenetes](../../../../03-media/cloudability-premium/images/container-kubernetes1.3.jpg)

## Expansion of Tag and Label Mappings - July 4, 2024

We’ve increased the number of available tag and label mappings in Cloudability by 20.

This means customers can now have up to 50 reporting dimensions in the platform that are
specific to mapped tags or labels. This will particularly help customers who are multi-cloud, and
have many tag or label keys in their environment. Cloudability administrators can add these
additional mappings in the “Tag & Label Mapping” feature.

## Taggable Resources Enhancement - July 4, 2024

Today, we have introduced a significant enhancement for taggable resources in Cloudability.
Historically, Tag Explorer broadly defined "taggable spend" as any cost item that had a Resource ID.
This led to some cost items being categorized as taggable even though the underlying usage was
untaggable. With this release, Tag Explorer now has in-built awareness on which specific AWS and
Azure services support tagging, leading to accurate categorization for the Taggable Spend and
Untaggable Spend tabs.

If you would like to have this applied for any previous months to support historical tag
analysis, please request a reprocess from your customer success team.

## Workload Planning – OCI Burstable VM support - July 1, 2024

With this release, Workload Planning now supports recommendations for OCI burstable virtual
machines, enabling users to leverage burst capabilities, which provide a cost-effective solution for
workloads with variable CPU usage patterns.

What's new in this release

Earlier, Workload Planning was providing recommendations for Virtual Machines, without the
option to select burstable instances, which was available in the OCI Cost Estimator. With this
release, users can now choose a baseline CPU utilization of either 12.5% or 50% for burstable
instances, representing a fraction of each CPU core. The baseline indicates the minimum CPUs that
can be utilized continuously.

For each baseline, Workload Planning provides the associated cost estimate: opting for a
baseline of 12.5% offers up to 87.5% in savings, while a baseline of 50% provides up to 50% in
savings.

Note:

There are four types of OCI Virtual Machines that support burstable configurations: 
VM.Standard3.Flex  ,  VM.Standard.E3.Flex  , 
VM.Standard.E4.Flex  , and  VM.Standard.E5.Flex  .

Important Update

We recently released support for the launch dates for a few services in Resource Inventory (EBS
snapshots, RDS instances, S3 buckets, Redshift snapshots). However, with the launch date of EBS
snapshot, we have run into a performance issue in Cloudability 's cost pipeline owing to which we
have decided to roll back the launch dates of EBS snapshots in Resource Inventory. We shall
re-launch this capability once we have an alternative stable solution available. Please note that
the launch dates of services other than EBS snapshots will still be available for consumption.

## Resource Inventory support for Views created with Business Dimensions - June 26, 2024

Today, we launched Resource Inventory support for views created using business dimensions.

Previously, Resource Inventory was unable to resolve views that are created using Business
Dimensions and whenever user would select a view created using business dimension, a “ 
Restricted View  ” page used to appear. With this release, Resource Inventory will start
resolving views created using business dimensions and effectively be able to honor any Cloudability
view created by the customer.

More information about this release

As such, we would also remove the existing privileged access to Resource Inventory through the
Front Door permission called  AWSResourceInventoryFullAccess  and enable this
feature for all users in the customer org because the admin user can now define data boundaries for
resource inventory data via views.

Also, we have now removed the privileged permission in Front Door that is tied to Resource
Inventory feature (  AWSResourceInventoryFullAccess  ). This would make the
feature available to all users within an org irrespective of any permission entitlement, similar to
modules like Reports, True Cost Explorer etc.

As such, we would also remove the existing privileged access to Resource Inventory through the
Front Door permission called  AWSResourceInventoryFullAccess  and enable this
feature for all users in the customer org because the admin user can now define data boundaries for
resource inventory data via views.

We have now removed the privileged permission in Front Door that is tied to Resource Inventory
feature (  AWSResourceInventoryFullAccess  ). This would make the feature
available to all users within an org irrespective of any permission entitlement, similar to modules
like Reports, True Cost Explorer etc.

## Enhanced Vendor Credentials User Experience - June 24, 2024

Today, we launched updates to  Vendor Credentials  which provide a better
user experience to Cloudability users. As Cloudability is expanding on data sources integrations, we
introduced a UI which is more scalable for new data sources, with better performance, A11y
complaint, and user experience.

What's new in this release

With this release, you can:

- Quickly identify the datasources available in Cloudability.
- Have a UI which is scalable, considering current integrations and future expansions.
- Have access to an Accessibility compliant  A11y  UI.
- Experience better performance on the Vendor Credentials UI loading times.
- Use new filtering and search capabilities on individual Vendor Credentials columns.
- Expand and collapse all accounts at a master payer/billing account level.
- Sort the details based on individual columns.
- Have better readability as we have improved the contrast ratios.

 Steps to view new UX 

1. In Cloudability , navigate to  Settings  >  Vendor
   Credentials  .
2. To add a new data source, click  Add Datasource  . This will show all the
   data sources available to a customer. ![Add datasource screenshot  ](../../../../03-media/cloudability-premium/images/vc1.jpg)
3. Select a  datasource  you would like to credential.![add AWS screenshot](../../../../03-media/cloudability-premium/images/vc2.jpg)
4. Now, the  Add  account while credentialing overlay is displayed from the
   right-hand side.
5. Once credentialed, you will be able to view a  Tab  for the
   datasource.![AWS added screenshot](../../../../03-media/cloudability-premium/images/vc3.jpg)

   Note:

   The credentialing steps for each datasource remains the same.
6. Within the Tab, you will be able to  Search  and  Filter
    on individual columns. ![Filter AWS Screenshot](../../../../03-media/cloudability-premium/images/vc4.jpg)
7. Click “…” to perform various actions as before. We have added text along with the icons:
   - View Details
   - Edit Account
   - Re-verify Account
   - Archive
   - Delete
8. The parent accounts (master payer and billing accounts among others) will collapse by default.
   Click individual accounts to view the next level of sub accounts (linked accounts and subscriptions
   or projects among others) or use the newly introduced Expand all/Collapse all icons. ![Account 1 AWS](../../../../03-media/cloudability-premium/images/vc5.jpg)![Account details aws](../../../../03-media/cloudability-premium/images/vc6.jpg)
9. The Vendor Credentials UI now supports lazy loading providing better performance on UI load
   times.

## Custom Virtual Machine Type Support for Workload Planning – June 14, 2024

With this release, Workload Planning users can now get cost estimates for GCP custom Virtual
Machines, supporting the N4, N2, N2D, E2 and N1 machine types.

What's new in this release

Earlier, Workload Planning was only supporting predefined machine types for GCP, which have a
preset number of vCPUs and amount of memory, and are charged at a set price. With this release,
Workload Planning provides recommendations for standard and custom VMs, based on the vCPU and memory
input. It allows you to choose the processing power and amount of memory without changing machine
types. If a combination of vCPU and memory doesn’t exist, Workload Planning will prioritize the vCPU
requirement, and look for the nearest memory amount.

Note:

This release only supports the “Free” OS, listed as “Linux” in Workload Planning , while the
custom VMs with “Windows” OS will be supported in the future release.

## RIS Support of Launch Date Dimension for More Services - June 14, 2024

With this release, Resource Inventory would support launch date dimension for the following AWS
services:

1. EBS Snapshots
2. RDS Instances
3. Redshift Snapshots
4. S3 Buckets
   1. s3:ListAllMyBuckets
   2. redshift:DescribeClusterSnapshots

More information about this release

The existing Cloudability users need to add these two new permissions to get the launch date
dimensions for S3 and Redshift:

It is recommended to assign these permissions to Cloudability IAM role via your AWS console by
navigating to  IAM  >  Access Management  >
 Roles  > Cloudability  Role (or your customized role created
for  Cloudability ) and assign the above two permissions to Cloudability 
MonitorResourcesPolicy  under the  Permissions  tab.

Note:

For new users, these permissions would already be included in the AWS credentialing script.

## Fine Grained View Only Permissions for Organize and Budgets Modules in Cloudability - June 14, 2024

With this release, we introduced three new permissions in Cloudability Organize module that
would allow users (with assigned permissions) to access, and view data in those respective screens
but not to edit them.

What's new in this release

The three new permissions are:

| Permission Name | Description |
| --- | --- |
| AccountGroupManagementFeatureViewOnlyAccess | Enable users, assigned to a role with this permission, to view accounts and account groups under Cloudability "Account Groups" feature menu item but cannot edit them |
| BusinessMappingsFeatureViewOnlyAccess | Enable users, assigned to a role with this permission, to view business mappings and their definitions under Cloudability "Business Mappings" feature menu item, but cannot edit them |
| TagsAndLabelsFeatureViewOnlyAccess | Enable users assigned to a role with this permission to view all Cloudability dimensions and their mapped tag keys , and Kubernetes labels under Cloudability "Tags" feature menu item, but cannot edit them |

## Export Columns Displayed in Resource Inventory UI – June 13, 2024

With this release, you will have an additional export option (at the top right of the inventory
grid) along with exporting full inventory data, where you can export the inventory data for only
those columns displayed in the UI. Previously, it was not possible to have an export (to CSV) of
only the selected columns in the resource inventory UI.

## Rightsizing Preferences – Storage/S3 Class Exclusion Support – May 30, 2024

Today, Cloudability launched new global settings within the Rightsizing Preferences section that
allows you to exclude object storage/S3 recommendations for specific storage classes based on the
values you entered.

What's new in this release

Before this release, Cloudability only provided class filtering for object storage rightsizing
recommendations at the page level and only for the top recommendations given, with no way to filter
globally or on an individual recommendation basis.

Starting today, you can quickly and easily start filtering rightsizing recommendations for
object storage/S3 at a global level to hide recommendations for unwanted object storage classes.

To enable this feature, follow the steps below:

1. Starting from the Cloudability primary navigation menu, navigate to the Settings menu item, and
   select  Rightsizing Preferences  .
2. Select the Object storage Preferences tab on the page, and check “Exclude recommendations where
   the recommended storage class contains the following values”.
3. Under this option, there will be text boxes where you can enter additional values which will
   then exclude any object storage recommendations where the class contains these values.

   Note:

   Changes to these settings may take up to 24 hours to take effect.

## Cloudability Usage Family Enhancements – May 28, 2024

Today, we launched enhancements to the Cloudability Usage Family. These enhancements apply to
Cloudability cost data from three Cloud Service Providers (CSPs): Amazon Web Services (AWS),
Microsoft Azure, and Google Cloud Platform (GCP). This update improves mapping quality, and provides
a higher coverage for cost line items to be categorized into the appropriate Usage Family..

How this feature can help you 

This change will lead to a reduction in the amount of unmapped line items (mapped as 'Other'),
address previously identified inaccuracies, and improve existing mappings. Additionally, more
services across all CSPs are now mapped. Changes reflect for cost line items from May 1, 2024, and
automatically for any reprocessed months.

Below are examples of what could change as a result:

- You might see Usage family API Request change to IO for some services such as AWS Sagemaker. The
  change mostly affects read/write operations.
- Specific to AWS, you might see changes from IO to Data Transfer. This is to align with the
  underlying units (BytesTransferred) for which you are charged.

## Usability Enhancements to Tags and Labels Page – May 23, 2024

With this release, we launched two enhancements:

1. Earlier, when you searched, and added a particular tag key to a Cloudability dimension, the
   search text and the search results used to disappear, making it difficult to multi select a bunch of
   tag keys from the same search text. Now, you can retain the search text, and search results even
   after adding a tag key.
2. Earlier, Tag key names with long strings were getting cut off making it challenging to read its
   full name. Now, we have adjusted the row height to display the full tag key name, and also added a
   tool tip to read it better.

## Addition of New KPIs for Total Resources and Total Snapshots for EC2 in Resource Inventory – May 17, 2024

With this release,  Resource Inventory  will support two new KPIs for EC2
which will provide you with more fine-grained data visibility. They are:

1. Total Resources (total number of EC2 resources that includes both EC2 instances and snapshots)
2. Total Snapshots (total number of EC2 snapshots).

## Custom Pricing Support for GCP Compute Spend CUDs – May 17, 2024

Today, we released new custom pricing for GCP Compute Flex-CUDs. As part of this new feature,
you will have the ability to toggle between retail (list) and custom (EDP) pricing upon selecting
the cost basis on reservation portfolio and recommendations pages of Cloudability.

What's new in this release

The toggle button between custom pricing and retail pricing is now available enabling easy
switching between the two as and when needed.

To enable this feature, follow the steps below:

1. Navigate to Cloudability >  Optimize  >  Reserved
   Instance Planner  >  GCP  >  Commitment Type =
   Compute Engine Flexible-CUDs
2. Navigate to Cloudability >  Insights  >  Reservation
   Portfolio  >  GCP  >  Commitment Type = Compute
   Engine Flexible-CUDs 

   Or,

   Toggle the Cost Basis picker between 
   Retail  and  Custom  .

More information about this release:

This new feature adds more flexibility to calculate and estimate cloud spending costs using
concepts of Cloudability with the added advantage of deciding beforehand which pricing model suits
you best.

## Normalizing Inconsistent Azure Region Names - May 17, 2024

Today, we launched an enhancement to Azure Region Names for reporting consistency. This
enhancement normalizes Azure Region Names.

How this feature can help you 

Earlier, customers experienced inconsistencies where the same Azure regions had different names
(For example, "EastUS" and "US East" for the same region). This release will resolve and prevent the
need for additional mapping tables to be created on the customer’s end. This will normalize Azure
region names that will provide customers with the required granularity for reporting.

For
example: Following this change, instead of returning "Hong Kong" or "HongKong (East Asia)" as the
region, the report would return EastAsia::Eastasia.

## Snooze/ Ignore Rightsizing Recommendations in Cloudability – May 14, 2024

Today, we launched a new rightsizing feature that allows you to hide (snooze)
rightsizing recommendations for specific resources for a customizable period. Starting today, you
can snooze specific rightsizing recommendations to enhance efficiency while reviewing, and actioning
rightsizing recommendations.

 How this feature can help you 

This
feature enhances efficiency by reducing the number of desired recommendations provided, as well as
by removing any confusion associated with continuing to display recommendations that have already
been determined as non-actionable for the time being.

Steps to enable Snooze Rightsizing Recommendations

1. Go to Cloudability primary navigation menu, navigate to the Optimize menu item, and select
    Rightsizing  .
2. Select the desired Rightsizing vendor and service page.

## OCI - Supporting instance type, instance category and instance family – May 11, 2024

Today we released the support of three dimensions for OCI Compute instances: “instance type”,
“instance category”, and “instance family”. These dimensions provide you with the additional
granularity and flexibility when reporting on your OCI spend and tracking costs across vendors.

More about this release 

Prior to this release, you would rely on “item description” dimension to report on OCI
instances. However, this approach posed challenges in generating reports seamlessly and identifying
cost spikes easily. With this release, you can now leverage these 3 new dimensions to report on your
OCI spend, as well as better understand and categorize compute instances.

Note:

This enhancement will require you to reprocess data to ensure that the new dimensions are
applied accurately to your past records.

## Azure MCA - Azure Cost Management APIs Support – May 9, 2024

This release brings in the support for the Azure Cost Management APIs in Cloudability
Credentials for Azure MCA customers in addition to using Azure exports. You can now utilize these
APIs in Cloudability to get both actual and amortized cost, using the Cost Management APIs.

Steps to credential an Azure MCA account using Azure Cost Management APIs

1. Go to Cloudability credentialing page, and select  Azure.
2. Click  Add  Credential.
3. Select  Microsoft Customer Agreement  (MCA) as Azure account type.
4. Enter  Azure Billing Account ID  ,  Azure Tenant ID
    , and  Subscription ID.
5. Enter  NA  in other fields.
6. Click  Generate Setup Script  .
7. Download and install PowerShell script  in Azure.
8. Click  Verify Credential  in Cloudability UI.

   The green tick
   indicates that the Account addition using Azure Cost Management APIs was successful.

   ![Azure Cost Management](../../../../03-media/cloudability-premium/images/ms_azure_edited.jpg)

For the existing MCA customers with azure exports using azure storage, nothing needs to be done.
In case of azure exports using azure storage, we‘ll continue fetching the Azure Cost Management
files from the configured location.

## Workload Planning GA – May 7, 2024

Today, we are thrilled to announce the General Availability of Cloudability Workload Planning ,
marking a significant milestone following its initial launch in 2023. This feature empowers
FinOps and Engineering teams to estimate costs of new workloads, based on resource requirements, and
custom pricing. When planning a new workload, it helps teams to effortlessly compare cloud resource
pricing and configuration options across AWS, Azure, GCP, and OCI, streamlining decision-making
processes.

How this feature can help you

With this GA release, Cloudability Admins gain enhanced control over Workload Planning’s
recommendations through the introduction of new Workload Planning Preferences. Here, Admins can set
default options for workload lease type (for example: On Demand, Spot), commitments, and input more
discounts or uplifts. Additionally, Workload Planning permissions have been improved, enabling
Cloudability Admins to oversee workloads created by users across their organization, promoting
transparency and facilitating seamless information sharing among teams.

Cloudability Workload Planning represents an industry-first capability, which allows users to
define cost-effective workloads with all necessary resources while considering deployment options
across multiple cloud providers. This fosters greater efficiency and alignment between financial,
and technical teams.

![WP intro](../../../../03-media/cloudability-premium/images/wp_1.jpg)

Workload Planning Preferences

These new controls introduced as a part of GA are accessible to Cloudability Admins by default.
It empowers FinOps teams to centrally define, and restrict options for Workload Planning . Any of
these settings are optional, and not required to use Workload Planning .

1. Go to Cloudability  Settings  >  Workload Planning
   Preferences.
2. Remove the availability of a specific CSP by leveraging the  Allow Service Provider
    option.
3. Define lease type preferences and commitment default options for your users. You also have the
   option to lock the commitment selection for users.
4. Incorporate any additional discount/uplift to your workload costs. Note that this is added on
   top of any custom pricing, which is already factored in Workload Planning .
5. Click  Save  to apply the change(s) immediately. The updated preferences
   will impact the existing and new workloads. ![WP Preferences](../../../../03-media/cloudability-premium/images/wp_2a.jpg)

   Workload Planning Permissions

   Cloudability Admins have access to Workload Planning and Workload Planning Preferences via their
    WorkloadPlacementFullAccess  permission. They can create and manage their
   workloads, view workloads created by all users from their organization (without editing right), and
   update Workload Planning Preferences. They can edit others’ workloads when they are directly shared
   with them with editing rights.

   Non-admins can create and edit their own workloads by default through 
   WorkloadPlanningFeatureCanAccess  permission. They can also view and possibly edit the
   workloads shared with them, depending on the permission granted by the workload owner.

   We have created an additional permission:  WorkloadPlanningPreferencesViewOnly
    . It can be added to a custom role to view Workload Planning Preferences, which will
   help users understand the feature setup better.

   ![WP Permissions](../../../../03-media/cloudability-premium/images/wp_3.jpg)

   Custom Pricing Support

   Workload Planning always shows costs inclusive of any custom pricing (e.g., for EDP) for
   AWS, Azure and OCI. If organizations don’t have a custom pricing agreement with a specific vendor,
   then we default to “retail” pricing.

   For GCP, you can enable the export of custom pricing
   data from their GCP billing account to get custom pricing in Workload Planning .

    More about this release 

   Visit [Get Recommendations for Workload Planning](../product/get-recommendations-for-workload-planning.html) , and [Workload Planning Preferences](../product/workload-planning-preferences.html) for more information or join the discussion
   on  [Apptio Community](https://community.apptio.com/login?returnurl=https%3a%2f%2fcommunity.apptio.com%2fblogs%2fsoline-plichta%2f2024%2f05%2f08%2fcloudability-workload-planning-ga-faq "(Opens in a new tab or window)")  .

## Minimum Usage Adjustment Method for GCP Compute Flex-CUDs – May 6, 2024

Today, we released a new commitment recommendation adjustment method for GCP Compute Flex-CUDs,
Minimum Usage. With this release, you can adjust the recommendation to the spend on the minimum
usage hour. This includes the ability to exclude the lowest 1 and 5 percentile of usage hours.

Note: No additional credentials or permissions are required.

## Support for Azure Cost Management Data Exports to Azure Storage with File Partitioning – May 6, 2024

Starting today, Cloudability will support Azure Cost Management Data exports to azure storage
with partitioning enabled for Azure customers. This would be applicable for both types of exports:

- Cost and usage details (actual)
- Cost and usage details (amortized)

  How this feature can help you

  Recently, Azure has upgraded the azure storage experience for customers and made the
  partitioning on export(s) as default which splits the exported file into multiple files, based on
  the size of dataset.

  Before this release, Cloudability didn't support cost management export files with partition
  which caused issues on data ingestion for Azure customers on newly created exports. This is no
  longer an issue as Cloudability has brought in support for Azure files with partition enabled.

  Note:

  This is a backend change and does not involve any changes or updates on the Cloudability UI.
  Azure cost ingestion for the customers with older exports will continue without them making any
  changes.

  Note:

  Customers who had enabled file partitioning while creating cost management exports should create
  a new export before adding credential in Cloudability.

## Rightsizing Recommendations for AWS Lambda functions in Cloudability – April 19, 2024

Starting today, users can get rightsizing recommendations for AWS Lambda functions providing
cost saving opportunities by identifying resources that can be resized to better match their
underlying workloads.

Before this release, rightsizing recommendations for AWS Lambda functions were not available in
Cloudability. Providing these recommendations directly within Cloudability provides users with a
more extensive, independent recommendation source to further optimize their AWS spends.

How to enable Rightsizing Recommendations for AWS Lambda

To enable this feature, follow the steps below:

1. Enable [Lambda Insights enhanced monitoring](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-insights.html "(Opens in a new tab or window)")  to allow Cloudability to retrieve memory metrics for
   your lambda functions.
2. Create or download the updated AWS credential template in
   Cloudability and then upload the new credential template to the AWS Management Console.
3. From the Cloudability primary navigation menu, navigate to the  Optimize 
   menu item, and select  Rightsizing  .
4. Select the  AWS  tab on the  Rightsizing  page,
   and under the available AWS services select the  Lambda  tab. Any existing
   Lambda rightsizing recommendations will be displayed here.

Note:

These recommendations, as well as their underlying data, will now be available in all areas of
Cloudability where rightsizing data for other AWS services is surfaced.

## Categorization of Dimensions and Metrics in Resource Inventory UI – April 3, 2024

We have added headers in the Table Settings (left slide out nav) in Resource Inventory UI that
will separate out the dimensions and metrics into two different sections.

With this release, dimensions would appear at the top, while metrics at the bottom when scrolled
down in the Table Settings.

## Introducing Cloudability in APAC Region – April 2, 2024

This release introduces the hosting of Cloudability , our cloud cost management platform, within
the APAC region.

How this feature can help you

This release addresses the unique needs of our APAC-based clients, ensuring their data remains
within the APAC boundaries. By localizing our services, we aim to empower organizations to bolster
their compliance efforts and align with the guidelines regarding cloud cost management data.

More information about the release

The launch of hosting Cloudability in the APAC region holds great significance for our customers
operating within this region. It provides a reliable and compliant cloud cost management solution
that prioritizes data residency, enhances data privacy, and aligns with data protection guidelines.

Note:

Customers, based in the APAC region, interested in migrating from the US to the APAC region can
reach out to their respective Account managers or Customer Success team.

Note:

No additional setup or installation is required for customers who are directly onboarding to
Cloudability in the APAC.

## Commitment-based Discount Support for GCP Compute Engine Flexible Committed Use Discounts – March 28, 2024

Today we released Commitment-based Discount Support for GCP Compute Engine Spend-based
Commitments (Flexible CUDs).

Starting today, users gain access to two new pages:

- From the  Commitment Portfolio  page, users can gain performance
  insights, set expiration alerts, and manage their portfolio of Flexible CUDs.

- From the  Commitment Recommendations  page, users can receive and adjust
  optimal recommendations to evaluate future commitment purchases.

How this feature can help you

With this release, we have reconfigured and introduced a new set of KPI’s and commitment meta
data across the portfolio and recommendations pages. This information will help you better manage
and understand the performance of your current commitments. For customers who are undercommented due
to uncertainty in applying financial risk to commitment decisions, our enhancements to the
Commitment Recommendations page will give you confidence to make more aggressive commitments to
increase net savings.

More information about the release

Over the upcoming releases, we will continue to build out additional functionality to assist you
in understanding the tradeoffs between different commitment terms, types, and strategies. We will
reorganize the information architecture across the Commitment-based Discount functionality and we
will look to support the majority of GCP spend-based commitment types.

Note:

The  Reservation Portfolio  and  Reserved Instance Planner
 pages will become the  Commitment Portfolio  and 
Commitment Recommendations  pages and be reorganized alongside each other under
 Optimize  soon.

## Container Cost Allocation for Kubernetes Version 1.29 – March 26, 2024

Container Cost Allocation is now officially supported on Kubernetes version 1.29 across all
providers.

This feature allows customers to gain detailed insights into their container resource usage and
associated costs for clusters running on Kubernetes Version 1.29.

![More CCA K8S enhancements](../../../../03-media/cloudability-premium/images/cca-kubernetes129.jpg)

## OCI Support in Workload Planning – Enhancements – March 26, 2024

Today, we released two enhancements to the 'OCI support in Workload Planning' feature:

• You can now select 'Capacity Reservation' pricing for your OCI Virtual Machines.

• You can gain visibility into Volume Performance Unit (VPU) amounts for your OCI 'Block
Volume'.

How this feature can help you

Prior to this release, users who wished to model out workloads for OCI in Workload Planning
could only leverage On-Demand or Spot (preemptible) pricing. With this update, you can now select
'Capacity Reservation' as a lease type option when adding a resource to your workload, similar to
the option available in the  [OCI Cost Estimator](https://www.oracle.com/cloud/costestimator.html "(Opens in a new tab or window)") 
. It's important to note that 'Capacity Reservation' is only supported for Virtual Machines and
provides an additional 15% discount, which is forfeited upon utilization. For further details about
OCI Capacity Reservation, please refer to the  [OCI Documentation](https://docs.oracle.com/en-us/iaas/content/compute/tasks/reserve-capacity.htm "(Opens in a new tab or window)")  .

As a reminder, any 'custom pricing' or 'custom
discount' for OCI is by default factored in the resource price displayed in Workload Planning.

Capacity Reservation

You can now select 'Capacity Reservation' as a preferred lease type for OCI in the common
information; the tool tip has been updated accordingly. When you choose this lease type, it will be
the default selection for Virtual Machines recommendations.

![OCI capacity reservation screenshot  ](../../../../03-media/cloudability-premium/images/oci_1.jpg)

In the recommendation, you will find 'on-demand', 'capacity reservation' and 'spot'
(preemptible) lease type options, which allow you to compare pricing options before adding a
resource to your workload.

![OCI VM updates](../../../../03-media/cloudability-premium/images/oci2.jpg)

 VPU Amounts 

You get visibility for Volume Performance Unit (into OCI Block storage VPU) amounts in the
'Attached Storage' recommendation screen. This information is not available for other cloud vendors.

![Attached Storage screenshot](../../../../03-media/cloudability-premium/images/oci3.jpg)

## Container Utilization Metrics Enhancements in Cloudability – March 4, 2024

We have made enhancements to our utilization metrics on the Cloudability container insights
page.

This update aligns the displayed memory metrics with those used in allocation calculations for
improved consistency and corrects the file system usage for EKS to ensure accurate reporting. To
clarify, these enhancements will not impact the cost or the cost allocation methodology and are
designed to provide a more accurate reflection of utilization metrics on the container insights
page.

## Enhancement to Cost (List) Metric in Cloudability – February 23, 2024

The Cost (List) metric functionality has been enhanced. Previously, certain private and bundled
rate discounts appeared as credits in the metric which resulted in incorrect values. However, Cost
(List) metric was designed to provide users with the on-demand cost for each line item, without
including information about discounts and credits. This enhancement resolves the issue.

## Update to Azure Permissions on the UI - February 23, 2024

Today we launched a couple of updates on the list of Azure permissions visible in Cloudability.

• Starting today, Azure users will have  Enrollment Reader  role
permission for Azure EA accounts and  Billing Account Reader  role permission
for Azure MCA accounts on the UI. Before this release, users were shown only Enrollment Reader role
permission for all Azure accounts.

• For Customers using Azure custom role we have added the below permissions display on the UI.
These were part of the permissions we take while credentialing azure subscriptions but were not
visible on the UI.

## Increase Cap on Maximum Kubernetes Labels in Tags & Labels Feature – January 31, 2024

We have increased the maximum number of Kubernetes labels available in our Tags and Labels
feature from 10 to 20. With this enhancement, you can incorporate a greater number of Kubernetes
labels, facilitating improved organization of synthetic tag dimensions tailored to their specific
use cases.

## Workload Planning: Resource Duplication – January 23, 2024

Today, we launched Workload Planning - Resource Duplication. Starting today, you can easily
duplicate your resources within a workload. This feature will also help you plan your workloads
faster, enabling an efficient what-if-scenario analysis.

How this feature can help you

Before this release, users faced the challenge of manually entering their requirements
multiple times when evaluating different options for their cloud resources or comparing costs across
various regions. Now, you can effortlessly clone your resources and adjust requirements. This will
also allowing you to explore diverse configurations for your cloud resources with ease and
precision.

How to enable resource duplication within a workload

1. Create a workload and add a resource.
2. Select the ‘Duplicate Resource’ icon to clone your resource. ![WP Resource duplication](../../../../03-media/cloudability-premium/images/wp11.jpg)
3. Update the name for the resource duplicate and change the requirements.

   ![Duplicate resource name](../../../../03-media/cloudability-premium/images/wp12.jpg)

   Note:

   You can now have resources in different regions within a given workload. You can update the
   resource region in “Search resource type (optional)” feature.

 More information about the release 

Use case example: Duplicating resources to compare AWS EC2 costs between two regions

1. Create a workload and add a resource. Use the “search resource type” option to get a cost
   estimate for t4g.2xlarge in us-west 1.![search resource type](../../../../03-media/cloudability-premium/images/wp13.jpg)
2. Duplicate the resource and rename it.
3. Update the region to us-west-2 for your duplicated resource.

   ![update resource type](../../../../03-media/cloudability-premium/images/wp2.jpg)

## Container Cluster Rightsizing – January 19, 2024

This release adds
rightsizing recommendations for Kubernetes clusters across AWS, Azure and GCP.

We are
excited to introduce the latest advancement to our suite of optimization tools – Container Cluster
Rightsizing. Aimed at enabling customers to efficiently balance cost savings with workload
performance, this feature provides a robust solution for sizing the VMs that back Kubernetes
clusters. It is available within Cloudability ’s rightsizing feature, under the 
Containers  tab, and is ready for customers to use today.

How this feature can help you

Cloudability users have previously been able to leverage rightsizing recommendations to optimize
Kubernetes at the workload level – tuning container request and limit settings. This launch adds a
new set of recommendations, this time at the cluster level. The feature evaluates vendor-defined
groups that back each cluster: ASG Node Groups for AWS, Node Pools for Azure, and GCP. The
recommendations are built around understanding the historical resource usage of these groups,
focusing on CPU and memory utilization. For each cluster, the tool then recommends the most
cost-effective instance type and count that will meet the resource requirements for every hour
across the reporting period.

For Cloudability , to generate these cluster-level recommendations we ingest your VM util data
via the regular AWS, Azure and GCP credentials. In short, if you are already setup for VM
rightsizing recommendations, then these cluster recommendations will already be available.

 Key highlights 

- You can review all clusters and savings summary information in the list view. The detailed view
  for each cluster includes utilization charts to aid in decision-making.
- It offers multiple recommendations per cluster, with combinations of instance type and count at
  various risk levels, catering to different operational comfort zones.
- This launch does not include recommendations for groups consisting of spot instances.
- For this launch, each recommendation consists of a single instance type, prioritizing uniformity
  and simplicity.

## AWS cleanup of CAR and DBR permissions – January 18, 2024

In this release we have removed the display of the older AWS permissions for Detailed Billing
Report (DBR) and Cost Allocation Report (CAR).

Support for AWS Detailed Billing Report (DBR)and Cost Allocation Report (CAR) is no longer
available in Cloudability , however in the permissions view we were showing the permissions related
to DBR and CAR until now with a red "x". With this release we have removed the DBR and CAR
permissions display from the UI.

How this feature can help you

This ensures AWS customers get a cleaner view of relevant permissions related to the AWS Cost
and usage reports.

## Setting Default Cost Metrics for Cloudability Modules – January 17, 2024

With this release, you can now set a specific default cost metric for each module, such as True
Cost Explorer and Rightsizing among others, from the list of all supported metrics for that
respective module.

How this feature can help you

Each module in Cloudability supports a specific set of cost metrics like such as Cost (Total),
Cost (List), and Cost (Amortized) among others. Previously, Cost (Total) used to be the default cost
metric displayed in these modules. Now, this features allows you to set your org's preferred cost
metric as the default cost metric for each module. It will appear under  Profile
 >  Organization Settings  in Cloudability for Cloudability
Admin user roles only.

The cost metric set for each module will get applied as the default metric for all users across
the entire Cloudability org.

## Cloudability introduces support for Oracle Cloud Infrastructure (OCI) in Workload Planning - January 16, 2024

Today we launched Oracle Cloud Infrastructure (OCI) support
in Workload Planning. Starting today, users can seamlessly estimate the costs of new workloads
deployed to OCI, enabling them to make informed provisioning decisions. What’s more, they can now
effortlessly compare cloud resource pricing across AWS, Azure, GCP and OCI. Before this release,
users had to use each vendor’s pricing calculator for the same.

![OCI support in WP](../../../../03-media/cloudability-premium/images/workload-planning-oci-1.jpg)

More information about the release

The key highlights of this release include:

- Effortless OCI Workload Modeling  : You can now seamlessly model out OCI
  workloads with resource recommendations spanning various service types\* such as Virtual Machine,
  Attached Storage, Object Storage, and Load Balancer.
- Custom Pricing Support  : Cost estimates in Workload Planning are
  inclusive of any custom pricing allowing you to plan more realistically.
- Cross-Cloud Resource Comparison  : You can identify the most cost-effective
  solution easily by comparing resource requirements and cost estimates across major cloud providers –
  AWS, Azure, GCP, and OCI.

Note:

Managed Database is not yet supported for OCI.

## Cloudability Enhancement: Service Name Update for F5 Rules for AWS WAF Product - January 11, 2024

In this release, we have corrected the service name designation for “F5 Rules for AWS WAF”.

How this feature can help you

Previously, our solution incorrectly mapped the marketplace charge for “F5 Rules for AWS WAF” to
‘AWS WAF’ as the service name. This has now been amended to accurately reflect the charges under
‘AWS Marketplace’ service name. As part of this enhancement, we have also addressed additional edge
cases where marketplace charges were not being mapped correctly to AWS Marketplace service name.

## Improved Cost (Total) Metric in Cloudability for AWS - January 5, 2024

This release introduces an enhancement to the Cost (Total) metric with a limited impact to some
of the customers monitoring AWS spend. It only impacts line items that relate to partial and no
upfront reserved instances (RI), while leaving the figures at the aggregate level as is.

How this feature can help you

The enhancement will help you improve the clarity of the cost metrics and simplify some of the
reconciliation efforts.

More information about the release

Although, the Cost (Total) metric always aimed at delivering an unadulterated representation of
the invoice cost – the “LineItem/UnblendedCost” column in the CUR file. However, there was one
exception to this, implemented at the time to support a consistent  [transition between the DBR
and CUR](https://www.apptio.com/blog/switch-to-aws-cur/ "(Opens in a new tab or window)")  files. Logic was applied to these two item types:

- For usage covered by an RI – use “reservation/RecurringFeeForUsage”, instead of
  “LineItem/UnblendedCost”.
- For recurring RI line items – use “reservation/UnusedRecurringFee”, instead of
  “LineItem/UnblendedCost”.

This ensured that the usage line items had the consumed RI value assigned to them, instead of a
zero value. It means, it moved cost from the monthly recurring lines to the usage lines. This helped
in maintaining consistent behavior with the older, now deprecated, DBR file but had the downside of
Cost (Total) not being a pure “pass through” cash metric.  With  Cloudability
 not supporting DBR anymore, these special rules for the Cost (Total) metric have been
removed and the enhanced metric is reflected in the lineItem/UnblendedCost column  .

Note:

These changes will take effect from January 2024 onwards. They will also apply to December 2023,
if AWS has not yet finalized your billing. Additionally, the changes will be retroactive in the
event of any billing reprocessing.

If you have any questions or require further assistance or need historical data reprocessed
under the new method, please reach out to your account team or support.

## Support for Custom Pricing for GCP Rightsizing - January 3, 2024

This release adds custom pricing support to the GCP Rightsizing feature for Cloudability so that
the contractual discounts and other customer specific pricing is applied to GCP rightsizing
recommendations and functionality.

How this feature can help you

This provides the capability to apply the contractual discounts received from your GCP to GCP
rightsizing recommendations. This also provides you with a more accurate representation of the cost
savings achieved by optimizing your resources. This will improve the accuracy of the rightsizing
recommendations by bringing attention to cost saving opportunities while identifying resources that
can be resized to better match your underlying workloads.

More information about the release

You are required to provide Cloudability with access to your custom pricing data to enable this
feature. Once this setup has been successfully completed, the new customer specific GCP pricing will
be automatically applied to the GCP rightsizing recommendations and functionality. The primary GCP
rightsizing functionality is located by navigating to  Optimize  >
 Rightsizing  >  GCP  . GCP resource level costs
will be available in Cloudability under  Reports and Dashboards  by selecting
the resource id column.
