---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "04-Insights-Tag-Explorer"
source_files_count: 1
last_updated: "2026-07-13"
---

# 04-Insights-Tag-Explorer

## Identify tagged and untagged spend with Tag Explorer

<!-- sub-header -->
- **breadcrumb:** Insights > Identify tagged and untagged spend with Tag Explorer
- **source_path:** SSVCLNQ/product/identify-tagged-and-untagged-spend-with-tag-explorer.html
- **original_file:** insights-identify-tagged-untagged-spend-tag-explorer.md
- **images:**
  - 03-media/apptio-cloudability-standard/tag_explorer_mceclip0.jpg
  - 03-media/apptio-cloudability-standard/tag_explorer_not_set-drilldown.jpg
  - 03-media/apptio-cloudability-standard/tag_explorer_service.jpg
  - 03-media/apptio-cloudability-standard/tag_explorer_untaggable.jpg

With Tag Explorer , we make it easy to see which tags your organization is currently using. For example, if you know your company uses the Team tag to allocate spending but can't remember if the values for the team should be lowercase, camel-case, spaces, abbreviated, etc., Tag Explorer is here to help.

The scenario

Many customers use Tag Explorer for asset management. Continuing the previous example, if you want to identify which resources are currently missing Team tags, you must only click on the Not Set segment for Team to display those resources in the table below.

For customers running infrastructure in multiple public clouds, we provide a seamless way to see tag usage in a single pane of glass. In this example, we use the Service tag to identify a process that runs in parallel in Azure, GCP, and AWS.

Not all AWS resources support tagging. In the Untaggable Spend tab, you can see a simple interface to view all AWS resources that don't currently support tags. Note that Account Groups and Business Dimensions face no comparable restrictions, so they aren't displayed in this view.

The Solution

To review, Cloudability offers a variety of tags to collect your cloud resources into meaningful groups.

- Mapped Tags offer a simple way to bring existing tags into Cloudability with the option to combine duplicate tags into a single dimension. This includes tags in AWS, resource labels, and project labels in GCP, and tags and resource groups in Azure.
- Account Groups allow you to apply tags at the account level, which then flow through to any resource which is consumed by that account. Functionally, these are very similar to project labels in GCP.
- Business Dimensions allow you to apply tags using arbitrary rules that you define.

Frequently asked questions

- How many tags are displayed? Fifteen most widely used tags are showed in this visualization. Note that any tags with less than 1% coverage are excluded. The tags with minimal spend are rolled into a catch-all group labeled "Other" for this visualization. It is not an actual tag value in your data, and you can see which individual tag values are being aggregated into "Other" by selecting "Other" segment.
- Does Tag Explorer support visibility into the different tag types - Resource Group Tags, Subscription Tags, GCP Tags and Labels etc.? Yes. Tag Explorer provides visibility into Resource Group Tags, Account/Subscription Tags, GCP Tags and Labels along with Resource Tags.

---
