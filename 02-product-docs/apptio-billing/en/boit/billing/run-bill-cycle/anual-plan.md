---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Annual planning and rate setting"
breadcrumb:
  - "Billing"
  - "Running the Billing Cycle"
source_path: "boit/billing/run-bill-cycle/anual-plan.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Annual planning and rate setting

Most Billing implementations follow a yearly rhythm for planning and rates, even if
adjustments happen during the year.

Typical annual activities:

1. **Confirm catalog and consumers**
   - Review the list of billable offerings.
   - Confirm which consumers (business units, cost centers, projects, products) will
     receive charges.
   - Retire offerings that are no longer used and add any new ones.
2. **Align with Costing**
   - Confirm that Costing models still support the chosen offering and consumer
     structure.
   - Verify that key cost drivers, allocations, and service definitions are still
     valid.
3. **Define rate strategy**
   - Decide if rates are cost based, cost plus, price based, budget based, or hybrid.
   - Agree how to handle under recovery and over recovery:
     - Adjust future rates.
     - One time adjustment.
     - Track as variance only.
4. **Set target rates**
   - Calculate draft unit rates by offering, based on:
     - Expected cost from Costing.
     - Expected volumes.
     - Target recovery or price.
   - Document assumptions that went into the rates.

1. **Review with stakeholders**
   - Walk through draft rates with Finance, Service or Product Owners, and key
     consumers.
   - Capture feedback and agree on final rates for the year.
2. **Load rates into Billing**
   - Update rate tables for the new year:
     - Effective dates or periods.
     - Rate amounts, currencies, and any rate types.
   - Validate that rates resolve correctly in test runs.

The rest of the year is about executing the monthly cycle against this agreed baseline and
handling any approved changes.
