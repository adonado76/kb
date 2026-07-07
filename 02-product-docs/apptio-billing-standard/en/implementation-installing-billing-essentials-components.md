---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Installing Billing Essentials components"
breadcrumb:
  - "Configuring Billing Essentials (Implementation)"
  - "Installing Billing Essentials components"
source_path: "SSV8ML/boit/billing/config-be/install-be.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Installing Billing Essentials components

*Billing Essentials is delivered as components that are installed into the existing Costing Essentials project.*

High-level steps:

1. Open the Costing Essentials project in TBM Studio.
1. Navigate to the area where components are managed.
1. Locate and install: Billing – Charge Billing – Charge Reporting
1. Confirm that installation: Creates the expected models and datasets. Adds the “Billing” report collection to the project.

Post-install checks:

- Verify that the Billing models compile without errors in In Development.
- Confirm that the new tables and metrics appear in the project’s data model.
- Confirm that the “Billing” report collection appears in the report tree (even if not yet published to Production).
