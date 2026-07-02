---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Populating the offering catalog"
breadcrumb:
  - "Billing"
  - "Configuring Billing Essentials (Implementation)"
source_path: "boit/billing/config-be/populate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Populating the offering catalog

The offering catalog drives what appears on bills. It should be populated and validated
before the first billing run.

Steps:

1. **Define the initial catalog**
   - List the services/products to be billed.
   - Assign:
     - Short, recognizable names.
     - Units of measure (for example, user per month, GB per month).
     - Offering IDs that are stable and unique.
2. **Load offerings into the table**
   - Use:
     - TBM Studio ETL if configuration is fully managed in Studio, or
     - Table upload if the catalog is maintained in a CSV or spreadsheet.
3. **Set flags**
   - Mark:
     - Billable = Yes for offerings that should appear on bills.
     - Active for offerings currently in use.
     - Internal or similar flags if some offerings are used only for internal
       allocations.
4. **Validate catalog**
   - Run a simple report or query to:
     - Check for duplicates.
     - Confirm units are populated.
     - Confirm status flags are correct.

Keep the initial catalog tight. It is easier to add offerings later than to roll back a
cluttered catalog.
