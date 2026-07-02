---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Access patterns for Billing Essentials"
breadcrumb:
  - "Billing"
  - "Getting started"
  - "User Roles and Permissions"
source_path: "boit/billing/getting-started/access-patters-be.html"
images:
  - "resources/images/boit_images/apbe.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Access patterns for Billing Essentials

Note: Applies to Billing Essentials only.

Billing Essentials is installed into the same project that runs Costing Essentials. There is
no separate Billing endpoint; users access Billing through the existing Costing front-end.

**Typical patterns:**

- **TAS and Partner**
  - Have front-end access to the “Billing” report collection.
  - Can run and validate Billing Essentials reports (invoices, detail, summaries).
  - Have TBM Studio access for back-end configuration and data adjustments.
- **Service or Product Owners, Senior Leaders, Stakeholders, and Consumers**
  - Access Billing reports through the same front-end entry they use for Costing
    Essentials.
  - See only the reports and data relevant to them, based on security and row-level
    filtering.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apbe.png)

## Key points:

- Most day-to-day access is handled through the same user management and permissions model
  used for Costing Essentials.
- Changes to Billing Essentials models, datasets, or tables in TBM Studio are performed by
  a TAS resource or a Partner.

Fig #: Bill Invoice report shown with navigation menu visible on the left
