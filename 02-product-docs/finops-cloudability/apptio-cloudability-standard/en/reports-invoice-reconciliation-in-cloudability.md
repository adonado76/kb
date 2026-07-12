---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Invoice Reconciliation in Cloudability"
breadcrumb:
  - "Working with dashboards and reports"
  - "Invoice Reconciliation in Cloudability"
source_path: "SSVCLNQ/chatbot/invoice-reconciliation-reporting.html"
images:
  - "03-media/apptio-cloudability-standard/inv_recon_filters.png"
  - "03-media/apptio-cloudability-standard/inv_recon_calendarpicker.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Invoice Reconciliation in Cloudability

Invoice Reconciliation refers to the process of validating that the total billed amount on a finalized Cloud Service Provider (CSP) invoice matches the total cost reported in Cloudability. This alignment is verified by generating a focused Cloudability report with a small set of filters. While the workflow itself is straightforward, there are several important considerations and nuances that can affect the accuracy of the reconciliation. This document outlines those key considerations and provides guidance for completing the exercise effectively.

## Before you proceed

Verify account credentialing

For the specified billing month, check that the Payer Account in question was successfully credentialed during the entire period and that cost data exists in Cloudability as expected.

Validate currency configuration

If the invoice currency differs from the Cloudability account currency, ensure multi‑currency settings are configured correctly.

Reconcile at the correct scope

Perform reconciliation at the combined Invoice Month and Payer/Billing Account level. Where available, use Invoice ID to align invoice data with raw billing records.

Account for invoice finalization timing

When reconciling the most recently closed month, understand the possibility that CSPs may make adjustments several days (up to two weeks) into the following month.

## Special considerations

The following are important notes and behaviors to consider when reporting on cost data in Cloudability:

- Rely on raw billing files (e.g., CUR, Cost Export, Cloud Billing Table) as Cloudability’s authoritative cost source. Expect invoices to match raw data in most cases, but be aware that vendors may include charges or credits on invoices that do not appear in raw billing exports.
- Be aware of vendor‑specific exclusions. Note that Azure Cost Management data exclude taxes and billing adjustments/credits. Do not expect these values to appear in Cloudability.
- There can be post-dated or out-of-cycle charges that exist on the invoice but are outside of the current usage month. This can cause confusion due to how Cloudability reports query the time-period based on Usage Date(explained more in the next section).
- AWS CUR and Azure MCA Cost Management Exports are the only billing file types that currently provide an invoice identifier field to Cloudability that can be used for invoice reconciliation using the Invoice ID dimension.
- When provisioning GKE clusters for use in Cloudability, assign unique cluster names. Ensure the gke-cluster label assigned to the cluster matches the provisioned cluster name exactly. Do not use duplicate names, as this may cause the resulting cluster-split costs in reporting to be incorrect.

## How to reconcile in Cloudability reporting

1. Begin by creating a report in Cloudability filtered on the specific Invoice Date and Payer Account ID . Invoice Date is reflected as the first of the month, the format is YYYY-MM-01 which will be formatted and displayed in the UI as <Month> 1st, <Year> . Payer Account ID is the primary payer/billing ID as shown on the invoice, and is what represents the account that is credentialed with Cloudability to ingest billing files. If reconciling with a vendor that supports Invoice ID, like AWS, add that as well if desired to reconcile at this scope. Invoice IDs typically have a many to one relationship with a Payer Account.
1. Using the Date Picker , choose a wide time period starting from at least the 1st of the prior month, and the end date should be as far into the future as available up until the current date. In this example, Jan 2026 is our desired invoice month and we are running the report on the 24th of February. The Date dimension in Cloudability is based on usage date, therefore the Date Picker in Cloudability queries the costs based on usage date range. The purpose of a wide time period is to capture any invoice charges in the usage months that neighbor the invoice month. Note: Cloudability Reporting will query up to the current usage date . So if there are delayed charges far into the future beyond the queryable time frame, Cloudability will not be able to report on them. This applies to the “out of cycle” charges as mentioned in the Special Considerations section of this document.
1. Optionally add the Month (Year) dimension to the report to highlight any usage charges occurring outside the invoice month.
1. Choose Cost (Total) as the report metric, since invoices reflect actual billed “out‑of‑pocket” costs rather than amortized amounts.
1. Finally, run the report and validate the cost shown in the resulting table.

## FAQ

What if my invoice cost does not match?

- PDF attachment or full screenshot of the invoice which displays all pertinent information including Billing Account ID, date of invoice, cost, and invoice ID
- Cloudability URL link for the report that was used for the reconciliation

Can I reconcile to the total cost as seen in a CSP cost management tool (i.e. AWS Cost Explorer) instead?

Generally, yes. However, native cost management tools are not always a direct reflection of what exists in the raw billing files. Reconcile against the invoice instead which is generally supported by the underlying raw billing data.
