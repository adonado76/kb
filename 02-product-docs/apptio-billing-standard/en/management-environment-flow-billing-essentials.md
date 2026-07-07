---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Environment flow for Billing Essentials"
breadcrumb:
  - "Administration and Operations"
  - "Environments and Release Management"
  - "Environment flow for Billing Essentials"
source_path: "SSV8ML/boit/billing/environ-relnmgmt/env-be.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Environment flow for Billing Essentials

Billing Essentials lives inside the Costing Essentials project and follows its environment lifecycle.

Implications:

- Any Billing Essentials configuration change (models, tables, reports) is made in In Development of the Costing Essentials project.
- When items are checked in: A new In Development build is created. A corresponding Staging build is automatically created.
- QA for Billing Essentials is performed against the Staging build of the Costing Essentials project: Run Billing Essentials models or scheduled processes. Open and validate Billing Essentials reports. Check that invoices, detail views, and archives match expectations.

When the Staging build is promoted:

- The Production environment for Costing Essentials and Billing Essentials is updated together.
- End users see the updated Billing Essentials behavior and reports once the promotion completes.

<image: show a Builds or Versions view for a Costing Essentials project, highlighting a specific build with a note mentioning Billing Essentials changes in its description>

Operational recommendations:

- Document which builds contain Billing Essentials changes so they can be traced during issue investigation.
- Align Billing Essentials releases with Costing Essentials releases wherever possible to simplify communication to stakeholders.
