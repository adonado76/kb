---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Access patterns for Billing Essentials"
breadcrumb:
  - "Getting started"
  - "User Roles and Permissions"
  - "Access patterns for Billing Essentials"
source_path: "SSV8ML/boit/billing/getting-started/access-patters-be.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Access patterns for Billing Essentials

Billing Essentials is installed into the same project that runs Costing Essentials. There is no separate Billing endpoint; users access Billing through the existing Costing front-end.

Typical patterns:

- TAS and Partner Have front-end access to the “Billing” report collection. Can run and validate Billing Essentials reports (invoices, detail, summaries). Have TBM Studio access for back-end configuration and data adjustments.
- Service or Product Owners, Senior Leaders, Stakeholders, and Consumers Access Billing reports through the same front-end entry they use for Costing Essentials. See only the reports and data relevant to them, based on security and row-level filtering.

## Key points:

- Most day-to-day access is handled through the same user management and permissions model used for Costing Essentials.
- Changes to Billing Essentials models, datasets, or tables in TBM Studio are performed by a TAS resource or a Partner.

Fig #: Bill Invoice report shown with navigation menu visible on the left
