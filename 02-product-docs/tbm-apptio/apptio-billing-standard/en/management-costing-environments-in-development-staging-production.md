---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Costing environments: In Development, Staging, Production"
breadcrumb:
  - "Administration and Operations"
  - "Environments and Release Management"
  - "Costing environments: In Development, Staging, Production"
source_path: "SSV8ML/boit/billing/environ-relnmgmt/environments.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Costing environments: In Development, Staging, Production

*Billing uses the same environments as the Costing project it is installed into. Configuration changes to Billing are managed through the Costing project’s environments: In Development , Staging , and Production .*

Environments are not separate projects . They are different environment areas of the same project.

## Costing environments: In Development, Staging, Production

Each Costing project (and therefore Billing content inside it) has three primary environments:

- In Development Where Admins and Analysts make configuration changes. Components, models, datasets, and reports are edited here.
- Staging Receives completed builds from In Development. Used for QA, regression checks, and validation before Production.
- Production The live environment for end users. Only completed, tested builds are promoted here.

Key behaviors:

- In Development is the only environment where items are checked out and edited.
- Each check-in produces a new build for In Development, and the platform automatically creates a corresponding build for Staging.
- Production only receives builds that are explicitly promoted.
