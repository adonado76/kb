---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Monthly billing process"
breadcrumb:
  - "Running the Billing Cycle"
  - "Monthly billing process"
source_path: "SSV8ML/boit/billing/run-bill-cycle/monthly-bill.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Monthly billing process

*Each billing period typically follows a repeatable set of steps.*

A common pattern looks like this:

1. Close the period Align with Finance on the cut off for the billing period. Freeze or snapshot source data where needed so volumes do not change under Billing.
1. Refresh cost and consumption data Ensure Costing has received the latest cost data for the period. Refresh consumption feeds into Billing: Usage, tickets, devices, cloud usage, project metrics, and similar.
1. Perform QA checks Run standard QA reports: Missing mappings (consumer, offering, domain objects). Volume spikes or drops. Zero or negative charges that should not exist.
1. Review draft bills Analysts and Admins review charges by offering and consumer. Service or Product Owners validate charges for their areas.
1. Apply corrections if required Fix data issues in source systems, mapping tables, or rate tables. Re-run QA checks.
1. Approve bills Once QA is complete, obtain sign off from designated approvers: Often Service or Product Owners and Finance.
1. Release outputs Publish/Email bills or showback reports to consumers.

Export and deliver journals to Finance.
