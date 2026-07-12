---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Map AWS Marketplace to ATUM"
breadcrumb: []
source_path: "cost-transparency/configuration/mapawstoatum.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Map AWS Marketplace to ATUM

If you consume services from the AWS Marketplace, you must ingest and model those bills
the same as your AWS service bills. AWS creates a separate AWS Marketplace billing file for each
billing report you configure to be created in your billing preferences.

As with typical AWS services bills, Apptio recommends using the AWS Marketplace Cost Allocation
report that aggregates at a monthly level. For more information about AWS Marketplace services,
visit [https://aws.amazon.com/marketplace/](https://community.apptio.com/external-link.jspa?url=https%3A%2F%2Faws.amazon.com%2Fmarketplace%2F "(Opens in a new tab or window)").

Applies to: Apptio Costing Standard or Apptio Cloud Cost Management
running on TBM Studio v12.3.3 or later.

## Task 1: Set up a new DataLink connector to automate the ingestion of your Marketplace bill

### Procedure

1. Create a new Datalink (Classic) AWS connector, or copy an existing AWS connector (Learn
   more).
2. Configure the authentication.

   Note: When using delegation, if you copy an existing connector, this section will be populated
   already.
3. Click Billing Report.
4. In Report Type, select Advanced.
5. In File Pattern, type the following pattern:“<your AWS account
   number>-aws-cost-allocation-AWSMarketplace-{CYYY}-{MM}.csv>”
6. Configure the Apptio Destination, Notifications, and Scheduling based on your specific
   requirements.
