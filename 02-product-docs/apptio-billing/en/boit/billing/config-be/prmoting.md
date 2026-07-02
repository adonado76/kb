---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Promoting to Production and first go-live run"
breadcrumb:
  - "Billing"
  - "Configuring Billing Essentials (Implementation)"
source_path: "boit/billing/config-be/prmoting.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Promoting to Production and first go-live run

Once Billing Essentials behaves as expected in Staging:

1. **Lock Staging**
   - Prevent new check-ins from altering the Staging build under test.
2. **Run final QA in Staging**
   - Confirm:
     - All required offerings have rates.
     - All required consumers have charges.
     - No unexpected zero or negative values appear where they should not.
3. **Promote the build to Production**
   - Promote the validated Staging build to Production following the standard environment
     process.
4. **Run Billing models in Production**
   - Execute the Billing Essentials models in Production for the target period.
   - Confirm that outputs populate correctly.
5. **Publish reports to target audiences**
   - Ensure the Billing report collection is visible to Admins, Analysts, and other
     intended roles.

Run a final set of smoke tests on Production reports.
