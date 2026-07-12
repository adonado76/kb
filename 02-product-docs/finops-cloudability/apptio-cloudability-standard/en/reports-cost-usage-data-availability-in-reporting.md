---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost and Usage Data availability in Reporting"
breadcrumb:
  - "Working with dashboards and reports"
  - "Cost and Usage Data availability in Reporting"
source_path: "SSVCLNQ/chatbot/cost-and-usage-data-availability-in-reporting.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost and Usage Data availability in Reporting

Overview

To report on Cloudability cost and usage data, the billing files from the vendor must first be processed through our data pipeline. The process begins with raw cost and usage data ingestion. Once that data is ingested, it goes through a series of data normalization, transformation, aggregation, and decoration steps before being made available to reporting.

Cost Pipeline Details

Cost and usage data ingestion in Cloudability begins after successful vendor credentialing where you grant Cloudability access to your billing data. Once Cloudability confirms that it has appropriate permissions from the credentialing process, it begins retrieving data from the vendor. Cloudability checks for new data multiple times a day for each credentialed account. As soon as new data is discovered on the vendor side, the ingestion process begins to pull the latest available data.

After the raw billing data ingestion, Cloudability’s data pipeline proceeds with various data processing steps. This next stage of the pipeline is responsible for enriching the raw data with many of the valuable data points and measures you use every day, such as tag mappings, business dimensions, account groups, and business metrics among others. Also, if you have clusters provisioned for use with Cloudability Container Insights, this is when container cost allocation is performed. Finally, the processed and decorated cost data is loaded into our data platform for use by Cloudability reporting, dashboards, and Apptio BI.

Frequently Asked Questions (FAQ)

What impacts my data processing time?

Data processing time is directly impacted by data volume. In addition the overall vendor raw file size and record count per credentialed account, the important considerations for the processing time include:

- Number of provisioned clusters and associated pod count (if provisioned within Cloudability ). Container cost allocation generates additional granularity which leads to many more records.
- Customer-defined dimensions such as Business Mappings and Tag Mappings. Mapping quantity and statement complexity.
- Time of the month –MTD data volume increases with every month. It is common for end of month processing to take longer due to data volume being at its peak.

When can I expect my new data to be available for reporting?

With respect to the inconsistent frequency in which the billing files are updated by the vendor and the variability of the overall data size per customer, we cannot guarantee an exact time that the new data will become available in Cloudability. Generally, this is within an average of 24 hours after a new billing file update is published by the vendor.

The “business as usual” (BaU) data processing including raw data ingestion as described in this article by default occurs on recent data . By definition that means current month’s data set, along with the addition of the previous month's data if there is an update to it by the vendor (typically previous month updates can occur up to two weeks after month end). Anything historical processing outside of this would require either a reprocess or refetch, depending on the use case.

What is a reprocess?

A typical customer action is a reprocess , which is a manually triggered action that performs the post-ingestion processing again on historical data . This means that we do not ingest any new vendor data during this operation, but instead process it through the latter part of our pipeline to decorate and transform the data again with updated information. A common use case for a reprocess would be to update Business Mappings on historical data in Cloudability. A reprocess is not necessary during the current month as it is processed automatically as explained previously. Reprocesses are performed in month units, and can take longer than the business as usual processing depending on the number of months requested.

What is a refetch?

A refetch is where we go through the entire pipeline process again, including retrieval the raw vendor data – this should only be performed in rare circumstances such as backfilling missing vendor data due to an error. Or, onboarding a new payer account in which historical data exists in the vendor’s storage and needs to be pulled into Cloudability. If required, work with your TAM or open an Apptio Support case.

This article specifically relates to cost and usage (billing) data availability in reporting/ dashboards for Cloudability and also Apptio BI Reporting.

Other features such as Rightsizing, Resource Inventory, and Cloudability Financial Planning require additional feature-specific processing after the billing data is processed. Additionally, cloud cost data import into TBM Studio (Cost Transparency) requires additional steps not outlined here.

What are future dated line items?

- Future dated line items are invoice line items whose Usage Start Time is later than the processing date .
- Common examples include, but are not limited to: AWS Savings Plans billed for the entire month upfront Pre-paid items such as AWS re:Invent tickets

Possible Discrepancies and How to Resolve

Sometimes, UI KPIs and API/Export totals won’t match until the data is fully processed. Depending on the source of the discrepancy, this can be resolved manually by adding Date or a similar report dimension.

- Within the Report UI, the total shown in the metric KPI across the top does not match the same metric’s total shown in the corresponding report table.
- The metric KPI’s total displayed in the UI does not match against the total in the corresponding report’s export.
- The metric KPI’s total displayed in the UI does not match against the total returned from equivalent report API result.

Reports including the current date

When the UI updates to the current date (e.g., end date advances from Dec 2 to Dec 3), a temporary discrepancy occurs during the ~4-hour window before first data ingestion. The UI KPI/Graph queries the Daily View and includes future dated line items, while Report Table/Export/API queries hit the Monthly View and exclude them. The discrepancy equals the future dated cost total for accounts without current date ingestion. This resolves after the first normal file drop for the impacted payer accounts.

- UI/KPIs use daily data → may include charges for the current date not yet ingested into Monthly Table when the UTC date changes
- Monthly table (exports/API) excludes them until first ingestion of current day occurs
- Common source of Discrepancy: AWS Savings Plans costs

TIP: If the totals match after filtering out AWS Savings Plan Costs, then you can assume the discrepancy is due to future dated line items

Possible Fixes/Workarounds

As previously mentioned, this type of discrepancy will automatically resolve once the next cost ingestion job completes. Otherwise, the following mitigation steps can be used if seeking a workaround sooner:

1. Update Report to include a dimension like Date or any of the other dimensions listed, so that both the API/Export and UI KPIs use the Daily View : Day Day of Week Week (Category) Week (Year) Invoice Date
1. Create a validation Report like the example below If the total shown in the KPI, and the Report Table are the same than you should not run into discrepancies due to future dated line items

Reports ending on yesterday’s date

Reports with the previous day as the end date show discrepancies. When the UTC date changes, UI prevents sudden total shifts by continuing to use the Monthly Table for the previous day. If customers don't update the end date, Report Table/Export/API totals will exceed KPI totals as the monthly table ingests data for the current date while the KPI only includes data through the set end date.

- Monthly table ingests current-day data, but UI report is fixed to yesterday
- This can make API/export totals appear higher than the UI KPIs

1. Update Report to include a dimension like Date or any of the other dimensions listed, so that both the API/Export and UI KPIs use the Daily View : Day Day of Week Week (Category) Week (Year) Invoice Date
1. Or update the date range to include the current date
