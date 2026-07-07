---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Front-end and endpoint relationships"
breadcrumb:
  - "Administration and Operations"
  - "Solution Architecture and Dependencies"
  - "Front-end and endpoint relationships"
source_path: "SSV8ML/boit/billing/sol-arch-depend/fe-endpoint-relation.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Front-end and endpoint relationships

*While this guide does not go deep into Frontdoor, it is important to understand how users reach Billing.*

- Billing Essentials Users open the Costing Essentials front end. Billing Essentials appears as a Billing report collection inside that project. There is no separate application entry for Billing Essentials.
- Billing Standard Users see a separate Billing entry in the front-end application or endpoint selector. Selecting this entry opens the Billing Standard front end, which is backed by the Billing components installed in the Costing Standard project. User access to Billing Standard is controlled at the endpoint level and within report collections.

The underlying project dependencies (components, models, tables) are always maintained in TBM Studio. The endpoints simply define how that content is grouped and presented to users.
