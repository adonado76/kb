---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Azure Blob Storage"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "Azure Blob Storage"
source_path: "SSVCLNQ/product/rightsizing-for-azure-blob-storage.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Azure Blob Storage

You can use the Rightsizing dashboard to view optimization recommendations for Azure Blob Storage. The dashboard shows both rightsizing and idle recommendations, and you can view recommendations across multiple subscriptions from a single dashboard.

Rightsizing in Cloudability

Azure Blob Storage overview

Azure Blob Storage is Microsoft Azure's object storage solution, organized around containers. Containers are top-level entities within storage accounts. You can use containers to store blobs that are associated with an access tier and organize them hierarchically within virtual directories.

Containers

Within each container, you can store an unlimited number of blobs. Costs are based on the blob's access tier, allocated storage (GB per month), operations (read, write, list), retrieval operations for Cool, Cold, and Archive tiers, re-hydration operations for Archive, and data transfer volume (egress).

Access tiers

Access tiers are designed for different access patterns and durability needs, ranging from frequently accessed data to infrequently accessed archival storage. Blobs in the same container can be assigned to different access tiers.

Azure Blob Storage access tiers differ in price, performance, availability, and minimum storage duration requirements. Depending on the access tier, additional fees can apply for retrieval operations and for early deletion when blobs are deleted, overwritten, or moved before the minimum storage duration is met.

By default, Azure blobs are created in the Hot access tier. To manually optimize individual blobs, you must identify regional rates for each access tier, collect historical access patterns and operations data, and evaluate the trade-offs, including early deletion fees.

Before you begin

To view the Azure Blob Storage dashboard, make sure that you have connected Cloudability to the correct Azure subscriptions and have Azure Monitor and diagnostic settings configured.

Azure Monitor and diagnostic settings are required for Azure Blob Storage rightsizing recommendations. Last Access Time tracking must be explicitly enabled on storage accounts for access-pattern-based recommendations. For information about connecting Azure to Cloudability, see Connect with Microsoft Azure .

Access the Azure Blob Storage dashboard

To access the Azure Blob Storage dashboard, open the Cloudability home page. From the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the Azure tab, and then select the Blob Storage subtab.

Only containers with incurred costs greater than zero are displayed.

Each day, Cloudability analyzes your Azure Blob Storage cost, usage, and utilization metrics for the previous 30 days. Rightsizing produces container-level insights and optimization recommendations. Spend is determined by GB-months.

Idle resources or allocated storage volumes containing negligible or no data are also displayed in the Rightsizing dashboard.

Customize the dashboard

You can use the following options to customize your dashboard.

Select Subscription

By default, the dashboard shows recommendations for all subscriptions. To view recommendations for a particular subscription, select the subscription name from the Subscription dropdown.

Apply filters

You can add filters to include or exclude data based on one or more conditions.

Add a filter

To add a filter:

1. Select Add Filter from the toolbar.
1. In the Add Filter menu, choose a Dimension .
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter rule is automatically applied to the Filters field. You can select only one value or parameter from each column at a time.

Remove a filter

To remove a filter: Select X next to the filter that you want to remove.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your Azure Blob Storage resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Container Name : The Azure Blob Storage container name.
- Storage Account Name : The Azure storage account name.
- Resource Group : The Azure resource group that contains the storage account.
- Subscription : The Azure subscription identifier.
- Size : The size of all blobs within the container.
- Blobs : The number of blobs within the container.
- Operations : The number of operations (read, write, list) performed by using the portal or API.
- Cost : The cost incurred during the previous 30 days for the blobs in the container.
- Current : The derived access tier for the container. If 100% of blobs are in the same access tier, that tier is displayed. If a container contains blobs in multiple access tiers, MIXED is displayed. Select the details to view the relative distribution across these tiers.
- New : The recommended optimal access tier for all blobs within the container.
- Action : The recommendation for the resource. The recommendation can be one of the following:

| Recommendation | Description |
| --- | --- |
| Rightsize | Move to the access tier specified in the New column. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels might be available in the details panel. |

Export recommendations to an Excel file

To export recommendations to an Excel file, select Export . The Excel file includes additional columns such as region, location, and confidence score.

Recommendation details

To view recommendation details for a resource, select View Details from the More Options menu.

The Azure Blob Storage details panel shows the following information:

Recommendations

One or more recommendations are shown, ranked by cost savings and risk (0-5).

- Savings: Estimated savings percent for the 30-day period.
- Cost Savings : Estimated savings amount (net of early deletion fees).
- Access Tier : Recommended access tier.
- Action : Recommended action.
- Risk : On a scale of 0-5, the number of access tier transitions from frequent to infrequent access.
- Payback Period : Time to recover early deletion fees (if applicable).
- Confidence Score : Recommendation confidence (0-100%) based on data completeness and Last Access Time availability.

Charts

- Storage Size (GB) : Displays the storage size amount by access tier. The possible values include the following: Hot Cool Cold Archive Smart Tier
- Operations (Read/Write Operations Count) : Displays the count of read and write operations performed against the container. This chart provides valuable insights into the usage category of the container such as mostly reads, balanced read-writes, or write oriented.
- Number of Blobs (Count) : The graph shows the number of blobs in the container over the time period.
- Data Transferred (GB) : Amount of egress to the internet (or data transferred across regions).
- Retrieval Volume (GB) : Amount of data retrieved from Cool, Cold, or Archive tiers.
- Rehydration Events (Count) : Number of Archive tier rehydration operations by priority (Standard/High).
- Early Deletion (GB/Month) : Amount of data deleted from tiers where there is a minimum retention period.

Taking action on recommendations

Access tiers

To transition the access tier of blobs or configure container-level storage optimization, you have several options:

- Lifecycle Management You can configure lifecycle management rules at the storage account level to automatically transition blobs to the recommended access tier based on blob age, last modified time, or other conditions. For more information about lifecycle management, see Azure Blob Storage lifecycle management .
- Smart Tier Enable Smart Tier on containers to automatically transition blobs between Hot, Cool, and Cold access tiers based on access patterns, eliminating the need for manual lifecycle rules. For more information about Smart Tier, see Azure Blob Storage access tiers .

Understanding Smart Tier

Smart Tier is a container-level feature that automatically transitions blobs between access tiers based on access patterns. When enabled, Smart Tier monitors each blob's access patterns and automatically moves blobs between Hot, Cool, and Cold access tiers for a monitoring fee in addition to the tier-specific rates.

Container-level rightsizing helps you identify which containers can benefit from this feature. New blobs start in the Hot tier. Smart Tier automatically moves them to the Cool tier after 30 days of inactivity and to the Cold tier after 90 days of inactivity. Accessing a blob moves it back to the Hot tier and resets the cycle.

Smart Tier does not support the Archive tier. For long-term archival data, use manual tier selection or lifecycle policies. Blobs smaller than 128 KiB remain in the Hot tier and are exempt from monitoring fees.

Smart Tier charges a monitoring fee of $0.04 per 10,000 blobs per month for blobs larger than 128 KiB. There are no early deletion fees or retrieval charges for Smart Tier transitions. All access operations are billed at Hot tier pricing.

For more information, see Smart tiering for Azure Blob Storage .

Understanding early deletion fees

Azure Blob Storage charges early deletion fees when blobs are deleted, overwritten, or moved before the minimum storage duration is met for Cool (30 days), Cold (90 days), or Archive (180 days) tiers. These fees are prorated based on the remaining days in the minimum duration period.

Cloudability recommendations account for early deletion fees when calculating projected savings and payback periods. Recommendations with significant early deletion fees display a payback period, which indicates how long it takes to recover the one-time costs through ongoing savings.

For more information about early deletion fees, see Azure Blob Storage access tiers .

Last Access Time tracking

Last Access Time tracking must be explicitly enabled on Azure storage accounts to provide access-pattern-based recommendations. When Last Access Time is unavailable, Cloudability uses last modified time for time-based analysis that is similar to lifecycle policies, but the resulting recommendations are less accurate.

Recommendations that are based on last modified time have lower confidence scores (70-89%) than recommendations that are based on Last Access Time (90-100%). The recommendation details indicate whether Last Access Time tracking is enabled.

For more information about enabling Last Access Time, see Move data based on last accessed time .
