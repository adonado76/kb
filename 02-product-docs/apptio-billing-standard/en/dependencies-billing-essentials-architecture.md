---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Billing Essentials architecture"
breadcrumb:
  - "Administration and Operations"
  - "Solution Architecture and Dependencies"
  - "Billing Essentials architecture"
source_path: "SSV8ML/boit/billing/sol-arch-depend/be-arch.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Billing Essentials architecture

*Billing Essentials is implemented inside the same project that runs Costing Essentials. There is no separate endpoint for Billing Essentials. All content is delivered as additional components and report collections within that project.*

Core elements:

- Components Billing- Charge Billing- Charge Reporting
- Where they install Installed by TAS or a Partner into the Costing Essentials project using TBM Studio. Add models, tables, metrics, and report definitions that support the billing process.
- How users see it Exposed as a “Billing” report collection in the Costing Essentials front end. Users access Billing Essentials reports the same way they access other Costing Essentials reports.

Fig #: “Billing- Charge” and “Billing- Charge Reporting” components highlighted

Dependencies and assumptions:

- The Costing Essentials project is already deployed and receiving cost and consumption data.
- Required Billing Essentials tables are populated with: Catalog of billable offerings. Consumer identifiers. Units and rates.
- Users who need access to Billing Essentials reports are granted front-end access to the project and the Billing report collection.
