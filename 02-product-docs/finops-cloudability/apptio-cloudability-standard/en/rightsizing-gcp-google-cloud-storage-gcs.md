---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "GCP Google Cloud Storage (GCS)"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "GCP Google Cloud Storage (GCS)"
source_path: "SSVCLNQ/product/rightsizing-for-gcp-cloud-storage.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GCP Google Cloud Storage (GCS)

You can use the Rightsizing dashboard to view the resource optimization recommendations for Google Cloud Storage (GCS). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Google Cloud Storage overview

Google Cloud Storage (GCS) is a storage service that is organized around buckets. The buckets are top-level containers. You can use these buckets to store individual objects that are associated with a storage class and also organize individual objects hierarchically within folders.

Buckets

Within each bucket, you can store unlimited individual objects. Costs are incurred at the rate for the object's storage class and factor by the allocated storage space (GB per month), number of operations (read, write, list), retrieval operations (for Nearline, Coldline, and Archive), and volume of data transferred (egress).

Storage Classes

Storage classes are tailored based on access patterns and durability needs, ranging from frequent to infrequent (archival) storage. Only an object, not a bucket, is associated with a storage class.

The GCS storage classes differ in price, performance, availability, and minimum storage duration requirements. Depending on the storage class you use, additional fees can be incurred for retrieval operations (accessing data from Nearline, Coldline, or Archive classes).

By default, GCS objects are created in the Standard storage class. To manually optimize individual objects, you need to identify the rates for each storage class by location, collect the past access patterns and operations, then evaluate each of the alternatives considering all the trade-offs.

Before you begin

To view the GCS dashboard, make sure that you have connected Cloudability to the correct GCP accounts and have Resource Level Billing (RLB) enabled.

Detailed Billing (also known as Resource Level Billing) is required for GCS rightsizing recommendations. For information about enabling Detailed Billing in your GCP configuration, see Connect with Google Cloud .

Access the Google Cloud Storage dashboard

To access the GCS dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the GCP tab, and then select the GCS subtab.

Only buckets with incurred costs greater than zero will be displayed.

Each day Cloudability analyzes your GCS cost, usage, and utilization metrics for the past 30 days. Rightsizing produces bucket-level insights and optimization recommendations. Spend is determined by GB Months.

Customize the dashboard

You can set the following options to customize your dashboard.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Account dropdown.

Apply Filters

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

The dashboard contains a rightsizing recommendations table, which provides an overview of your GCS resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Bucket Name : The GCS bucket name.
- Account Name : The GCP account name.
- Size : The size of all objects within the bucket.
- Objects : The number objects within the bucket.
- Requests : The number of requests (read, write, list) done via the console or API.
- Cost : The cost incurred for the past 30-days for the objects within the bucket.
- Current : The derived storage class for the bucket. When 100% of all objects are in the same storage class, that storage class will be displayed. If a bucket consists of objects within multiple storage classes, then MIXED will be displayed. Clicking the details will display the relative distribution across these classes.
- New : The recommended optimal storage class for all objects within the bucket.
- Action : Recommendation for the resource. The recommendation can be one of the following

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New column. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, location type, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The GCS details panel shows the following information:

Recommendations

Shows one or more recommendations, ranked by cost savings and risk (0-5).

- Savings: Estimated savings percent for the 10- or 30-day period.
- Cost Savings : Estimated savings amount.
- Storage Class : Recommended storage class.
- Action : Recommended action.
- Risk : On a scale of 0-5, the number of storage class transitions from frequent to infrequent access.

Charts

- Storage Size (Bytes) : Displays the storage size amount by storage class. The possible values include the following: Standard Nearline Coldline Archive Autoclass
- Operations (Class B/ Class A Operations Count) : Displays the count of Class A and Class B Operations performed against the bucket. This chart provides valuable insights into the usage category of the bucket such as mostly reads, balanced read-writes, or write oriented.
- Number of Objects (Count) : The graph shows the number of objects in the bucket over the time period.
- Data Transferred (Bytes) : Amount of egress to the internet (or data transferred across regions).
- Data Transitioned (Bytes) : Amount of ingress data from the internet (or data transferred across regions).
- Earyl Deletion (Bytes/Month) : Amount of data deleted from tiers where there is a minimum retention period.

Taking action on recommendations

Storage classes

To transition the storage class of objects or configure bucket-level storage optimization, you have several options:

- Object Lifecycle Management You can configure lifecycle management rules at the bucket level to automatically transition objects to the recommended storage class based on object age, creation date, or other conditions. For more information about object lifecycle management, refer to https://cloud.google.com/storage/docs/lifecycle .
- Autoclass Enable Autoclass on buckets to automatically transition objects between storage classes based on access patterns, eliminating the need for manual lifecycle rules. For more information about Autoclass, refer to https://cloud.google.com/storage/docs/autoclass .

Understanding Autoclass

Autoclass is a bucket-level feature that automatically transitions objects between storage classes based on access patterns. When enabled, Autoclass monitors each object's access patterns and automatically moves objects between Standard, Nearline, Coldline, and Archive storage classes for a per-object monitoring fee in addition to the storage class-specific rates.

Bucket level rightsizing helps you to identify which buckets will benefit from this feature. Although most objects are created in the Standard class initially, as your GCS buckets become optimized over time, additional incremental optimization recommendations such as Nearline, Coldline, or even Archive may be recommended.

For more information, refer to https://docs.cloud.google.com/storage/docs/autoclass .
