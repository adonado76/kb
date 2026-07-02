---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Preparing consumer data"
breadcrumb:
  - "Billing"
  - "Configuring Billing Essentials (Implementation)"
source_path: "boit/billing/config-be/prepare.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Preparing consumer data

The Billing Essentials model needs a consistent view of who is being billed.

Steps:

1. **Align with the existing consumer structure in Costing**
   - Identify the “consumer” object or table used by Costing (for example, business units,
     cost centers, departments).
   - Confirm the primary key and hierarchy.
2. **Ensure full coverage**
   - Confirm that all entities expected to be billed appear in the consumer master.
   - Add new entries for:
     - New business units.
     - New cost centers.
     - New project or product entities, if they are being treated as consumers.
3. **Validate mappings**
   - If Billing uses mapping tables (for example, mapping from an external ID to the internal
     consumer ID), ensure:
     - Every external ID in consumption data maps to an internal consumer ID.
     - Orphan entries are resolved before the first billing run.
