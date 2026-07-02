---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Tag and Label Mapping"
breadcrumb:
  - "Cloudability Premium"
  - "Setup"
  - "Organize Your Cloud Spend"
source_path: "admin/map-tags.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Tag and Label Mapping

Cloudability enables comprehensive cost allocation by ingesting and normalizing tags and labels
from supported cloud providers, SaaS platforms, and container environments. This document describes
the tag and label types supported by each vendor, how they are collected (billing data vs. APIs),
required permissions, and key considerations such as formatting differences, precedence rules, and
known limitations

## Tag and label support by vendor

AWS Tags

Cloudability supports the below mentioned types of tags for AWS

- **Resource level tags**

  These are part of the AWS CUR files and no extra permissions are required within Cloudability for
  enabling these
- **Account level tags** (via API)

  To get account level tags from AWS Organizations,
  Cloudability needs an additional permission named **organizations:ListTagsForResource**. Note:
  Account level tags are currently not available in Cloudability Gov.

  These are displayed in
  the following format in Cloudability:

  `cldy:aws:accountLevelTag:<tag
  key>`

Note: If a customer switches from legacy CUR to CUR 2.0, then they have to reconfigure their Tags
and Labels within Cloudability.

Difference between AWS Legacy CUR and CUR 2.0 tags:

Legacy CUR tags format:

- AWS tags = `aws:<tag key>` e.g.
  `aws:autoscaling:groupname`
- user tags = `<tag key>`

CUR 2.0 tags format:

- AWS tags= `aws_<tag key>` will be separated with an underscore = e.g.
  `aws_autoscaling_group_name`
- user tags = `user_<tag key>` e.g. `user_application`

Azure Tags

Cloudability supports the below types of tags for Azure:

- **Resource level tags**
  - These are part of the Azure Export files and no extra permissions are required within
    Cloudability for enabling these
  - Tags format - `cldy:Azure:ResourceTag:<resource tag key>`
- **Resource group tags** (via API)
  - To get Resource group tags from Azure, Cloudability needs an additional permissions for advance
    credentials either **management:Reader** or
    **Microsoft.Resources/subscriptions/resourceGroups/read** on the subscription.
  - Tags format - `cldy:Azure:ResourceGroupTag:<resource group tag key>`

  Important:

  If a tag key exists on a resource at both the resource level and the resource group level, and
  you map the **plain tag key** from the drop-down (for example, `project`),
  Cloudability will resolve the value as follows:

  - The resource-level tag is used when present.
  - If the resource-level tag is missing or null, the resource group tag is used as a fallback.

  If you do not want the resource group tag to be used as a fallback, map the **explicit
  resource-level tag** instead (for example, `cldy:Azure:ResourceTag:project`).
- **Subscription level tags** (via API)
  - To get subscription level tags from Azure, Cloudability needs an additional permission:
    **subscription:ReadSubscription**
  - Tags format - `cldy:Azure:SubscriptionLevelTag:<subscription tag key>`

GCP Tags and Labels

Cloudability supports the below mentioned types of tags and labels for GCP:

- **GCP Labels**

  These are part of the GCP Billing data extract and no extra permissions are
  required within Cloudability for enabling these. Cloudability supports the below labels:

  - Resource labels
  - Project labels
  - System labels

  If same key is configured for project, system and resource labels, the precedence to show
  the label on Cloudability UI is as follows: **Resource** > **Project** >
  **System**

  Note: Cloudability does not support mapping of labels which are a result of the
  "GKE cost allocation" feature from GCP. Labels such as `goog-k8s-*` or
  `k8s-*` will result in (not set) values. To benefit from container cost allocation,
  clusters should be provisioned for use in the *Cloudability Containers* feature which enables
  namespace and label level costs.
- **GCP Tags**

  These are part of the GCP Billing data extract and no extra permissions are
  required within Cloudability for enabling these

  Format of the GCP tags supported in
  Cloudability:

  `cldy:gcp:tag:<tagKey>` for direct tag
  assignments

  `cldy:gcp:tag:<tagKey>:inherited` for inherited
  tags

  `cldy:gcp:tag:<tagKey>:namespace` for tag attachment level

OCI Tags

- **Resource and compartment level tags**
  - Resource level or compartment level assigned by namespace. These are part of the OCI Billing
    data and no extra permissions are required within Cloudability for enabling these
  - Compartment level tags must be assigned via a Tag Namespace first and then assigned as a Tag
    Default in OCI

Note: We map the OCI billing fields of *compartment name* and *compartment id* to tag keys
named `cldy:oci:compartmentname` and `cldy:oci:compartmentid`

IBM Tags

- **Resource level tags**
  - These are part of the IBM Billing data and no extra permissions are required within Cloudability
    for enabling these

Databricks Tags

- **Resource level custom tags**

  These are part of the Databricks Billing data and no extra
  permissions are required within Cloudability for enabling these

Note: We do pass Databricks usage metadata, identity metadata and product features as Tags.
*WorkspaceId* will be visible as a tag key under
`cldy:databricks:workspaceid`

MongoDB Tags

- **Resource level tags**
  - These are part of the MongoDB invoice data and no extra permissions are required within
    Cloudability for enabling these

Note: We map the MongoDB billing fields of *Group ID* and *Group Name* to tag keys
named `cldy:mongodb:groupid` and `cldy:mongodb:groupname`

Snowflake Tags

We support Snowflake warehouse and account level tags in the below format. Be aware that there
are specific requirements for warehouse tags to populate, including enabling the TAG\_REFERENCES view
in Snowflake. Please see the credentialing documentation for more details.

`cldy:snowflake:account:<tagkey>`

`cldy:snowflake:warehouse:<tagkey>`

Kubernetes (K8s) Labels for containers

Different from typical vendor cost allocation tags, Kubernetes labels are also supported within
the Tag & Label Mapping feature. These labels are fundamentally different than cost tags/labels
as they do not exist in the billing data, instead they're a result of the Cloudability Container
Insights feature which provides granular cost allocation for your supported container spend (EKS,
GKE, AKS, OpenShift).

These labels will be available for mapping once you provision a supported cluster with the IBM
FinOps Agent. For more information, please see "Define additional dimensions based on K8s labels"
under [Container Cost Allocation](../product/k8s-cost-allocation.html).

## Frequently asked questions

Why are AWS resource-level tags missing on the Tag & Label Mapping
page?

Before mapping, you must instruct AWS which tags to include in your cost data exports. You can do
this in the AWS Billing Preferences. Only the selected tag keys will appear in the CUR.

Why do I see a (not set) tag value in reports?

If you've built a report in Cloudability with a tag column, you've likely seen a value called
**(not set)**.

This could mean one of these things:

- You have not told the vendor (like AWS) to include all your tags in your billing data
- You have resources that are taggable but are not yet tagged
- You have spend that is not taggable
- You didn't request to reprocess the historical data

How do I know what resources are taggable?

Each vendor has their own definitions and restrictions on what they define as a "taggable
resource". Cloudability offers the *Tag Explorer* feature to assist you in getting transparency
of your top taggable and untaggable spend which can help you understand where to focus your tagging
efforts.

When in doubt, it is best to refer to the vendor-specific documentation on whether a specific
type of usage is taggable. Common examples of untaggable spend are Support costs, commitment fees,
Tax, EBS snapshots, and some marketplace charges.

Why aren't my Azure resource group tags showing up?

To populate resource group and subscription-level tags for Azure, we require additional
permissions to fetch them from the Azure API (known as "advanced credentials" in Cloudability).
Please reference the previous portion of this document to check the permissions that are
required.

Can I map multiple tag keys to a single tag dimension in Cloudability utilizing a tool
like regex or wildcards?

At present, Cloudability does not allow you to map multiple tag keys to a single dimension using
regex or wildcards.

How does Cloudability handle multiple tag keys?

If the same resource has multiple tag keys then Cloudability will pick up the first valid tag key
(one with a value) which was added to the tag key list for the given dimension.

How can I extract a value from a tag?

In Cloudability , there are couple of ways to find out value from a tag:

1. Using Tag Explorer: Navigate to Insights > Tag Explorer, under *Taggable Spend* tab,
   apply filter for ' Tags & Labels' Dimension. In the chart, you can mouse hover to different Tag
   and view the tag values.
2. Using Reports: You can generate a report by including a specific *Tag (Value)* dimension in
   the report. The result will display all the different Tag (Values) for different Tag (Keys).

What is the limit on tags that can be mapped in tags and labels?

In Cloudability, the current dimension limit for Tags & Labels is 50.

Can we add more than 30 Tag & Label mappings?

Cloudability has increased the number of available 'Tags & Label' mappings in Cloudability
by 20. This means customers can now have up to 50 reporting dimensions in the platform that are
specific to mapped tags and labels. This will particularly help customers who are multi-cloud and
have many tag or label keys in their environment. Cloudability administrators can add these
additional mappings in the 'Tag & Labels' Mapping feature.

If a tag value changes in the CSP raw data, how will it appear in
Cloudability?

Suppose you changed the tag on CSPs side from 'playground' to 'game'. The old tag value has
already been written to previous billing data, and any change in value wouldn’t be retroactive. So,
any new billing data, associated will reflect the new tag value. You should leverage business
mappings, which can be applied to historical data.

You cannot update historical tags unless the you upload new billing files for old months with the
new tag value. If you'd like to pursue this, open a support case and Apptio Support can trigger a
data refetch for the updated data. **Be aware when data is refetched**, all previous data will be
overwritten with the current values. So in the case of hierarchical tags (account/subscription
level), Cloudability will take in the **current** value of those tags and apply it to all
refetched data.

How will Cloudability process the tags if the same resource has multiple tag
categories assigned to it i.e., resource tag, resource group tag and account level tag?

If a customer has 3 resources namely Resource A, Resource B and Resource C.

- Resource A has a resource tag called **Owner** with value as **R1**
- Resource B has a resource tag called **Owner** with value as **R2**
- Resource C has no tag assigned

These 3 resources belong to a resource group namely **Resource X** that has a resource group
tag called **Owner** with value = **RG1**

**Resource X** belongs to an Azure subscription namely **Subscription Z** that has a
subscription level tag called **Owner** with value = **S1**

In Cloudability, customer creates a new tag dimension called **CLDY Owner** and maps the
above tag keys in the below mentioned sequence:

cldy:azure:resourcetag:owner | cldy:azure:subscriptionleveltag:owner |
cldy:azure:resourcegrouptag:owner

Resource A has all 3 tags (resource tag, resource group tag and subscription tag) but because
resource tag is the first in the sequence per the dimension created above (CLDY Owner), resource tag
will be picked first for Resource A with tag key Owner and value = R1, and resource group tag and
subscription tags will be ignored. Same will happen for Resource B, where resource tag will be
picked up with tag key = Owner and value = R2. When it comes to Resource C, there is no resource tag
associated with it, so it will check what is next in the sequence in the dimension created. Since
the next is resource group tag, resource group tag with tag key = Owner and value = RG1 will get
assigned to Resource C.

Now lets say if the customer created the tag dimension in a different order as below, where
resource group tags come first:

cldy:azure:resourcegrouptag:owner | cldy:azure:resourcetag:owner |
cldy:azure:subscriptionleveltag:owner

In this case, resource group tag will be assigned to all 3 resources because they all have
resource group tags (tag key = Owner and value = RG1). Resource tags and subscription tags will get
ignored here, because resource group tags comes first in the sequence and all 3 resources have
resource group tags associated with them.

Similarly if subscription level tag was the first one added in the sequence, then the
subscription tag with tag key = Owner and value = S1 will get assigned to the tag dimension and
resource group tags and resource tags will be ignored.

**Parent topic:** [Organize Your Cloud Spend](../admin/tag-data.html)
