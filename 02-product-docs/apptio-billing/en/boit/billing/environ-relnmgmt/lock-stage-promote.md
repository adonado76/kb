---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Locking Staging and promoting to Production"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
  - "Environments and Release Management"
source_path: "boit/billing/environ-relnmgmt/lock-stage-promote.html"
images:
  - "resources/images/boit_images/unlockstg.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Locking Staging and promoting to Production

Before promoting changes to Production, the Staging environment should be **locked**
to prevent new check-ins from generating additional builds.

Typical sequence:

1. **Lock Staging**
   - Prevents new builds from being created in Staging.
   - Ensures that QA is performed on a stable Staging build.
2. **Run QA in Staging**
   - Validate:
     - Billing models run successfully.
     - Billing reports open and display data as expected.
     - Key Billing use cases (invoices, detail views, journals) behave correctly.
3. **Promote to Production**
   - After QA is complete, the approved Staging build is promoted to Production.
   - Promotion can be:
     - Performed immediately.
     - Scheduled to occur after a build completes or during a defined maintenance
       window.
4. **Unlock Staging**
   - Once Production is running on the approved build, Staging can be unlocked.
   - Development work can resume and new builds can flow into Staging.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/unlockstg.png)

Fig #: Staging environment locked with Unlock button on Build ribbon showing “Unlock”.

Key points:

- Always test Billing behavior in Staging before promoting to Production.
- Locking Staging is essential to avoid accidentally testing one build and promoting a
  different one.
