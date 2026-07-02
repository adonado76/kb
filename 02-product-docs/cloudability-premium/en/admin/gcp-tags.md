---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "GCP Tags and Labels"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
source_path: "admin/gcp-tags.html"
images:
  - "images/gcp-tags.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Tags and Labels

Cloudability supports the below mentioned types of tags and labels for GCP

- **GCP Labels**
  - These are part of the GCP Billing data extract and no extra permissions are required within
    Cloudability for enabling these .Cloudability support below labels
    - Resource labels
    - Project labels
    - System labels

Note: If same key is configured for project, system and resource labels, the precedence to show
the label on Cloudability UI is as follows:

- Resource

- Project
- System

- **GCP Tags**
  - These are part of the GCP Billing data extract and no extra permissions are required within
    Cloudability for enabling these

GCP Tags are becoming popular tagging mechanism with large number of GCP customers for cost
allocation and policy-based tagging. Cloudability now supports GCP Tags in addition to GCP Labels.
Users can now use both of these in a variety of use cases.

For more information on GCP Tags, click [https://cloud.google.com/resource-manager/docs/tags/tags-overview#inheritance](https://cloud.google.com/resource-manager/docs/tags/tags-overview#inheritance "(Opens in a new tab or window)")

## Key changes for GCP Tag Mappings :

- Enhanced mapping options: You can now map costs using both GCP Tags (organization/folder level)
  and GCP Labels (resource level) for more comprehensive cost allocation.
- Hierarchical cost allocation: Map inherited tags to business units or departments, while using
  labels for project-specific allocations.
- Priority configuration: Set priority between GCP Tags and Labels in cases where both exist for
  the same cost dimension.

In order to use GCP Tags, customers would need to enable the GCP tags in GCP console. Once
enabled, Cloudability while ingesting the billing data will also bring in the GCP Tags.

Once
Ingested GCP Tags will appear as new tag dimensions in your Tag Mappings configuration in Tags and
Labels page alongside existing GCP Labels. You will see them as below:

- **cldy:gcp:tag:<tagkey>** for direct tag assignments
- **cldy:gcp:tag:<tag key>:inherited** for inherited tags
- **cldy:gcp:tag:<tagKey>:namespace** for tag attachment level

![gcp tags](../../../../03-media/cloudability-premium/images/gcp-tags.png)

GCP Tags then can be used in other features like Business Mappings, Views Tag explorer,
Dashboards and reports to further drill down into various cost allocation scenarios.

## Troubleshooting

**How do I prioritize between selection of GCP Labels vs GCP Tags?**

GCP Tags and Labels both will be displayed in Cloudability's Tags and Labels page under the
organize section. Currently the page follows a priority order based on the tags mentioned. If you
already have GCP labels and want to give priority to GCP Tags then you'll need to remove the old GCP
labels and add GCP tags as the first option, followed by labels. Once this is done, Reprocess is
required to reflect this change in Cloudability reports and everywhere.

**I have added a new GCP Tag, but I am unable to view the value associated with it in
Cloudability, what might be the reason?**

Please check the GCP Tag order as explained above. Please ensure that the GCP tags are given
priority in the order of TAGS in the tags and labels page. In case of conflicts between GCP labels
and GCP tags we'll check the priority order of Tags configured.

**At the time of launch how many months of GCP tags would be available?**

At the time of launch we'll start pulling the GCP tags data from the current month.

**How can GCP tags be backfilled?**

Customers would need to raise a GCP backfill case to request the backfilling of GCP tags. The
internal Support or Engineering team will then need to trigger a refetch to load the data for the
specified months.

**How will Tag Explorer change with GCP Tags support?**

Tag Explorer will now provide visibility into both GCP Tags and Labels, offering:

**Enhanced Coverage Analysis:**

- **Dual-layer visibility**: See both inherited GCP Tags and directly applied GCP Labels
- **Inheritance tracking**: Identify which costs are allocated through inherited tags vs. direct
  resource labeling
- **Coverage gaps**: Spot resources that lack either tags or labels for complete cost allocation

**New Filter and Analysis Options:**

- **Tag source filtering**: Filter by direct tags vs. inherited tags
- **Hierarchy analysis**: Understand cost allocation patterns across your GCP organization
  structure

**Parent topic:** [Connect Google Cloud](../admin/connect-google-cloud-premium.html)
