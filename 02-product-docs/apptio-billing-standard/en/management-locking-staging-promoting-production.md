---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Locking Staging and promoting to Production"
breadcrumb:
  - "Administration and Operations"
  - "Environments and Release Management"
  - "Locking Staging and promoting to Production"
source_path: "SSV8ML/boit/billing/environ-relnmgmt/lock-stage-promote.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Locking Staging and promoting to Production

*Before promoting changes to Production, the Staging environment should be locked to prevent new check-ins from generating additional builds.*

Typical sequence:

1. Lock Staging Prevents new builds from being created in Staging. Ensures that QA is performed on a stable Staging build.
1. Run QA in Staging Validate: Billing models run successfully. Billing reports open and display data as expected. Key Billing use cases (invoices, detail views, journals) behave correctly.
1. Promote to Production After QA is complete, the approved Staging build is promoted to Production. Promotion can be: Performed immediately. Scheduled to occur after a build completes or during a defined maintenance window.
1. Unlock Staging Once Production is running on the approved build, Staging can be unlocked. Development work can resume and new builds can flow into Staging.

Fig #: Staging environment locked with Unlock button on Build ribbon showing “Unlock”.

Key points:

- Always test Billing behavior in Staging before promoting to Production.
- Locking Staging is essential to avoid accidentally testing one build and promoting a different one.
