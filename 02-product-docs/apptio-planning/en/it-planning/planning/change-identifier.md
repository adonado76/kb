---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Change Identifiers"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/change-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Change Identifiers

The Change Identifiers feature allows administrators to update the system identifiers
(codes) used by reference data dimensions such as Cost Centers, Accounts, Projects, and
Departments.

Note: Admin or Budget Process Owner roles are required to change identifiers.

Identifiers act as the unique, system-facing keys that Planning uses to reference and connect
data across plans, imports, APIs, and integrations. While descriptive names are user-facing
and can change, identifiers provide stability and consistency.

## Important Behavior

- Changing an identifier does not update the display name of the dimension value.
- Existing plans, regardless of state (New, Open, or Final), automatically remap to the
  new identifier.
- Identifiers must remain unique within the dimension.

## Supported Dimensions

The Change Identifiers feature applies to most standard and custom dimensions, including:

- Account
- Cost Center
- Department
- Labor Activity Type
- Location
- Project
- Project Group
- Project Labor Role
- Variance Driver
- Vendor
- Custom Dimensions

## How to Change Identifiers

**1. Export the Change Identifiers Template**

1. Navigate to **Configuration** → **Reference Data**.
2. Select the dimension you want to update.
3. Open the **ellipsis (…) menu** and select **Identifiers Template**.
4. Export the identifiers template as a CSV file.

**2. Update the Identifiers**

In the exported CSV:

- Leave existing **Code** records intact.
- Update the **New Code** column with the new codes you want to apply.
- Do **not**modify values you don’t intend to change.

**3. Import the Updated Template**

1. Open the **ellipsis (…) menu** and select **Change Identifiers**.
2. Import the updated CSV file.
3. Review the validation results.

**4. Review and Apply Changes**

If everything looks correct, confirm the change.
