---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Updating Reference Data in Plans"
breadcrumb:
  - "Planning"
  - "Working with Plans"
source_path: "it-planning/planning/update-refdata-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Updating Reference Data in Plans

Note: Only users with Admin or Budget Process Owner roles can perform these tasks.

## What is Reference Data?

Reference data defines the standardized lookup values for dimensions like Cost Center,
Account, Department, Vendor, Project, etc. These values power how plan line items are
classified, aggregated, and reported.

Learn more: [Reference Data Overview](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-reference-data-overview "(Opens in a new tab or window)")

## Updating Reference Data in a plan

When a plan is created, it automatically uses the latest published version of reference data
available at that time. If reference data is updated later, existing plans do not
automatically inherit those changes. You must explicitly update the plan to apply the latest
reference data.

**How to Update Reference Data**

1. Open the plan you want to update.
2. Ensure you are viewing **All Departments**.
3. Open the **ellipsis (…) menu** and select **Update Reference Data**.
4. Review the **impact summary** shown in the confirmation modal, which includes:
   1. Line items to be updated
   2. Line items to be deleted
   3. New items
   4. Removed items
   5. Parent codes changed
5. If the impact looks correct, select **Update** to apply the changes.

**Important Notes**

- By default, updates that would delete existing line items are blocked to prevent
  accidental data loss.
- To allow destructive updates, an Admin must enable **Disable Update Reference Data
  Restrictions** in the Company Profile.
- When destructive updates are allowed, a **backup plan is automatically created**
  before applying the reference data update.
