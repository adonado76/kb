---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Promoting to Production and first go-live run"
breadcrumb:
  - "Configuring Billing Essentials (Implementation)"
  - "Promoting to Production and first go-live run"
source_path: "SSV8ML/boit/billing/config-be/prmoting.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Promoting to Production and first go-live run

*Once Billing Essentials behaves as expected in Staging:*

1. Lock Staging Prevent new check-ins from altering the Staging build under test.
1. Run final QA in Staging Confirm: All required offerings have rates. All required consumers have charges. No unexpected zero or negative values appear where they should not.
1. Promote the build to Production Promote the validated Staging build to Production following the standard environment process.
1. Run Billing models in Production Execute the Billing Essentials models in Production for the target period. Confirm that outputs populate correctly.
1. Publish reports to target audiences Ensure the Billing report collection is visible to Admins, Analysts, and other intended roles.

Run a final set of smoke tests on Production reports.
