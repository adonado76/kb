---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Overview of AWS billing reports"
breadcrumb: []
source_path: "cost-transparency/reports-v104/awsbillingreportsapptio.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Overview of AWS billing reports

Applies to: Costing Standard on TBM Studio 12.3.3 and later

AWS offers several sources of billing data, each with its own characteristics and uses. For more
detail, see [Understanding Your Usage with Billing Reports - AWS Billing and Cost
Management.](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports.html "(Opens in a new tab or window)")

While Apptio supports data from a large variety of sources, we offer purpose-built integrations
around a subset of AWS billing reports. Currently, Apptio has built integrations with the following
billing reports:

- **Cost Allocation Report** - This monthly-grain bill from AWS includes all of the billing
  details (AWS product, usage quantity, cost, etc.) as well as tags selected to be included in the
  bills. Apptio leverages the Cost Allocation Report to drive monthly TCO reporting for public
  cloud.
- **Detailed Billing Report with Resources and Tags** - This hourly-grain bill from AWS is
  similar to the Cost Allocation Report, and includes both billing details and tags. Apptio leverages
  the Detailed Billing Report with Resources and Tags to drive the Daily Costs reporting in Cloud Cost
  Management, which you can use to see month-to-date costs as of the current day, as well as the daily
  and hourly trending of AWS costs.

The Detailed Billing Report with Resources and Tags bill can become excessively large (100M+ rows
per month) because it combines hourly detail with the inherent detail of AWS billing. As your
organizational AWS spend increases, the size of this bill might become too large to bring into
Apptio as a native .csv file.

Beginning with Apptio's 12.3.3 release and Datalink (Classic), you will see a new AWS connector
automatic transform option that allows you to ingest the Detailed Billing Report with Resources and
Tags bill in a new format on which the Daily Costs reporting is built. This new format, while
serving as the foundation for the daily reports in Cloud Cost Management, is not currently available
for transforms or modeling in TBM Studio. The Cost Allocation report is still the source for monthly
billing.

## What about the AWS Cost and Usage Report (CUR)?

AWS has a newer billing report that is the go forward standard for AWS bills. Apptio is currently
working on integrating with the CUR and has plans to provide a CUR-based connector in an upcoming
release.
