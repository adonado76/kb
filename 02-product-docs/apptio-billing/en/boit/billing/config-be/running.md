---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Running the Billing Essentials calculation"
breadcrumb:
  - "Billing"
  - "Configuring Billing Essentials (Implementation)"
source_path: "boit/billing/config-be/running.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Running the Billing Essentials calculation

With offerings, consumers, consumption, and rates in place, the Billing Essentials
calculation can be run in In Development and Staging.

Steps:

1. **Run Billing models in In Development**
   - Execute the primary Billing calculation model(s) created by the Billing – Charge
     component.
   - Confirm that the run completes successfully.
2. **Inspect outputs**
   - Review the Billing output table:
     - Ensure there are rows for all expected consumers and offerings.
     - Spot-check units, rates, and charges.
3. **Publish and test reports in In Development / Staging**
   - Open invoice and detail reports from the Billing report collection.
   - Validate:
     - Totals by consumer and offering.
     - Key use cases (for example, one major business unit, one large service).
4. **Perform formal QA in Staging**
   - Once initial behavior is confirmed, move to Staging and:
     - Re run the Billing models on more complete data.
     - Run QA reports that highlight missing mappings or anomalies.

Only after this cycle is stable in Staging should a build be promoted to Production.
