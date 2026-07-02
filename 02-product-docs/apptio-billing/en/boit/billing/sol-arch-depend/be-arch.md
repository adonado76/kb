---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Billing Essentials architecture"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
  - "Solution Architecture and Dependencies"
source_path: "boit/billing/sol-arch-depend/be-arch.html"
images:
  - "resources/images/boit_images/bearch.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Billing Essentials architecture

Billing Essentials is implemented inside the same project that runs Costing Essentials.
There is no separate endpoint for Billing Essentials. All content is delivered as additional
components and report collections within that project.

Note: Applies to Billing Essentials only.

Core elements:

- **Components**
  - Billing- Charge
  - Billing- Charge Reporting
- **Where they install**
  - Installed by TAS or a Partner into the Costing Essentials project using TBM
    Studio.
  - Add models, tables, metrics, and report definitions that support the billing
    process.
- **How users see it**
  - Exposed as a **“Billing” report collection** in the Costing Essentials front
    end.
  - Users access Billing Essentials reports the same way they access other Costing
    Essentials reports.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/bearch.png)

Fig #: “Billing- Charge” and “Billing- Charge Reporting” components highlighted

Dependencies and assumptions:

- The Costing Essentials project is already deployed and receiving cost and consumption
  data.
- Required Billing Essentials tables are populated with:
  - Catalog of billable offerings.
  - Consumer identifiers.
  - Units and rates.
- Users who need access to Billing Essentials reports are granted front-end access to the
  project and the Billing report collection.
