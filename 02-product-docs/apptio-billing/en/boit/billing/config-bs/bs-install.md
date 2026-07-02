---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Installing Billing Standard components"
breadcrumb:
  - "Billing"
  - "Configuring Billing Standard (Implementation)"
source_path: "boit/billing/config-bs/bs-install.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Installing Billing Standard components

Billing Standard ships as a set of components installed into the existing Costing
Standard project. The Billing Standard endpoint in the front end surfaces content created by
these components.

Typical components (names may vary slightly by version):

- Foundation
- Units
- Services / Offerings (often part of Foundation)
- Applications
- Servers
- Storage
- End User Devices
- Cloud
- Projects
- Price
- Cost Variance
- Plan Variance
- Inter Company Transfer Pricing

High-level steps:

1. Open the **Costing Standard project** in TBM Studio.
2. Navigate to the component management area.
3. Select and install the required Billing Standard components.
4. Confirm that installation:
   - Adds the expected models, datasets, tables, and metrics.
   - Creates report collections that will be surfaced in the Billing Standard
     endpoint.

Post-install checks:

- All Billing Standard models compile successfully in In Development.
- Key domain tables (Applications, Servers, Storage, Cloud, Projects, Devices, Legal
  Entities, Units, Price) are visible in the data model.
- The Billing Standard endpoint is provisioned and linked to the project, even if reports
  are not yet promoted.
