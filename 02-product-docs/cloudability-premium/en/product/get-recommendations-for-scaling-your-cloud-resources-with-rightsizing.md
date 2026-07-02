---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Rightsizing"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
source_path: "product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html"
images:
  - "images/rightsizing-explorer.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Rightsizing

With Rightsizing, you can define the optimal cloud infrastructure best suited for your current
and near-term needs in a way that balances risk and cost to minimize waste.

Using the Rightsizing dashboards, you can see cloud resource utilization over time. You can
then view recommended scenarios for each resource to better inform your cloud rightsizing decisions.

There are two Rightsizing dashboards:

- Rightsizing: View rightsizing recommendations for your cloud services. [Rightsizing Dashboard](#get-recommendations-for-scaling-your-cloud-resources-with-rightsizing__Rightsiz).
- Rightsizing ROI: View potential and realized savings for tickets synchronized with Jira  [Rightsizing using a Jira integration](jira-for-rightsizing.html) .

Rightsizing Dashboard 

The Rightsizing dashboard displays the Explorer tab by default. The Rightsizing Explorer gives an
overview of possible savings across all Cloud resources used by your company. You can use this
dashboard to group, filter and navigate your rightsizing recommendations.

[Rightsizing Explorer](rightsizing-explorer.html) .

![rightsizing screenshot](../../../../03-media/cloudability-premium/images/rightsizing-explorer.jpg)

The additional tabs in  Rightsizing  are recommendations for specific cloud
providers.

## Rightsizing FAQ

Why is the default recommendation time period 10 days?

10 days captures the most recent performance trends and is more predictive of future resource
use.

How is Idle defined?

*Idle*  is defined differently based on the resource type, but generally is represented as the
following: Idle for Compute (for example EC2) is the time spent below 2% CPU on a scale of 1-100.
Idle for Block Storage/ Disk (for example EBS) is the percent of hours with zero IOPS. Idle for
Relational Storage/ Database (for example RDS) is based on the number of the active DB Connections/
Sessions at a given point in time.

How do you determine spend?

Spend is instance usage spend for Compute (For example EC2) and Relational Storage/ Database
(For example RDS). Data Warehouse (For example Redshift) excludes data transfer. For Object &
Block Storage (For example S3 & EBS), spend is determined by GB Months.

Why doesn't Total Spend in Rightsizing exactly match the values shown in Reporting / True
Cost Explorer?

Rightsizing only lists resources for which it found at least one money-saving resource so it is
likely these values will not match exactly.

Why do I see (not set) under State for EBS?

The account has insufficient permissions (ensure your policy is up to date with the latest
permissions) or the resource was active for less than an hour ( the data does not appear in the
Describe Data cache from AWS).

Why do I see N/A for lastAttachedTime for unattached EBS volumes?

Volumes will show the timestamp from their last attachment to EC2 instances and the volumeID.
For volumes that have not been attached during the rightsizing window (the last 10 days by default),
it will show N/A.

For EC2, do the recommendations take into account burst?

We use baseline performance for burstable resources (for example, T2 instance types) and do not
account for the burst in determining the recommendations. This ensures we make conservative
recommendations that won't result in resource clipping.

For EC2, how do you determine Network and Disk?

AWS does not report EC2  *Network*  and  *Disk*  throughput limits. Furthermore, the
throughput capacity will vary based on both workload (for example, sequential versus random read and
write) and transfer (for example, data transfer within a region versus across regions). We use
commonly observed limits across our customer portfolio to approximate capacity.

Why are Spot Instances excluded from rightsizing recommendations?

Our rightsizing engine takes into account your workload (utilization metrics) and the cost to
run it (current instance type and on-demand price) and generates a list of recommendations from
which you can choose to help save you money. Spot Instances, on the other hand, are already offered
at steep discounts; applying rightsizing in these situations results in negligible savings. For this
reason, we have chosen to exclude Spot Instances from rightsizing.

Note:

When we recommend that you move an EC2 instance type to an instance with no local storage, we
incorporate into the recommendation that you add EBS and account for both in the savings.

How frequently are recommendations updated?

We update our rightsizing recommendations daily. You can access recommendations for resources 24
hours after the resource is created, provided that there is enough utilization data.

How does Cloudability determine rightsizing recommendations?

Rightsizing recommendations are generated using Cloudability ’s best-in-breed proprietary
rightsizing algorithm. These recommendations vary for different CSPs (Cloud Service Providers) and
services but typically the metrics being factored in are those shown in the graphs within the
details pane of the recommendations. For example, compute recommendations would typically look at a
combination of CPU, Network, Disk, Memory, and possibly a few other metrics and the utilization over
the selected time periods to understand the best options.

What should I keep in mind when looking at rightsizing recommendations?

When looking at the rightsizing recommendations, you first need to understand the difference
between the available Cost Basis options and which you intend to use. Secondly, use your due
diligence when implementing a certain recommendation as Cloudability does not know the purpose of
each resource. Your teams may have kept certain resources 'idle' or 'under-utilized' for a specific
purpose but Cloudability may recommend to terminate or reduce the size of resources.

In Rightsizing section, can we set the look back period (timeline) to 60 days?

Currently, rightsizing in Cloudability only supports the look back period or timeline of 10
Days and 30 Days.

What are the various state values displayed in Azure disk rightsizing and what do they mean?

In Rightsizing recommendations for Azure disk, the state values are:

- ActiveSAS: The disk currently has an Active SAS Uri associated with it.
- ActiveSASFrozen: The disk is attached to a VM in hibernated state and has an active SAS URI
  associated with it.
- ActiveUpload: A disk is created for upload and a write token has been issued for uploading to
  it.
- Attached: The disk is currently attached to a running VM.
- Frozen: The disk is attached to a VM which is in hibernated state.
- ReadyToUpload: A disk is ready to be created by upload by requesting a write token.
- Reserved: The disk is attached to a stopped-deallocated VM.
- Unattached: The disk is not being used and can be attached to a VM.

See the following Azure documentation under "fields" for the latest values and their definitions
[https://learn.microsoft.com/en-us/dotnet/api/microsoft.azure.management.compute.models.diskstate?view=azure-dotnet-legacy#fields](https://learn.microsoft.com/en-us/dotnet/api/microsoft.azure.management.compute.models.diskstate?view=azure-dotnet-legacy#fields "(Opens in a new tab or window)")

Do rightsizing recommendations take into account the Cloud Service Provider (CSP) discounts
due to hourly commits? If the recommendations are applied, does the hourly spend go down?

For AWS a custom cost metric must be in place. For Azure and GCP a pricing sheet is provided by
these cloud service providers. So, custom pricing is not required. The hourly spends come into
effect the next time after the cost and usage data is ingested and processed.

- **[Rightsizing Explorer](../product/rightsizing-explorer.html)**
- **[AWS EC2](../product/rightsizing-for-aws-ec2.html)**
- **[AWS EC2 Autoscaling Group (ASG)](../product/rightsizing-for-aws-autoscaling-groups.html)**
- **[AWS EBS](../product/rightsizing-for-aws-elastic-block-store.html)**
- **[AWS ElasticIP](../product/aws_elasticip.html)**
- **[AWS Lambda](../product/rightsizing-aws-lambda.html)**
- **[AWS RDS](../product/rightsizing-for-aws-rds.html)**
- **[Amazon Redshift](../product/aws_redshift.html)**
- **[AWS S3](../product/rightsizing-amazon-s3.html)**
- **[Azure Compute](../product/rightsizing-for-azure-compute.html)**
- **[Azure Compute Scale Sets](../product/azure_compute_scale_sets.html)**
- **[Azure Disk](../product/rightsizing-for-azure-disks.html)**
- **[Azure SQL](../product/rightsizing-for-azure-sql.html)**
- **[Azure Blob Storage](../product/rightsizing-for-azure-blob-storage.html)**
- **[GCP Google Compute Engine (GCE)](../product/rightsizing-for-gce.html)**
- **[GCP Google Compute Engine (GCE) Managed Instance Groups (MIG)](../product/rightsizing-for-gcp-gce-mig.html)**
- **[GCP Google Persistent Disk (GPD)](../product/rightsizing-for-gpd.html)**
- **[GCP Google Cloud Storage (GCS)](../product/rightsizing-for-gcp-cloud-storage.html)**
- **[OCI Virtual Machines (VMs)](../product/rightsizing-for-oci-vms.html)**
- **[Autoscale Action for Rightsizing](../product/rightsizing-autoscale-action.html)**
- **[Rightsizing for Kubernetes Containers](../product/k8s-container-rightsizing.html)**
- **[Rightsizing Preferences](../product/rightsizing-preferences.html)**
- **[Snoozing Rightsizing Recommendations](../product/rightsizing-snoozing-recommendations.html)**

**Parent topic:** [Rightsizing in Cloudability Premium](../product/rightsizing-in-cloudability-premium.html)
