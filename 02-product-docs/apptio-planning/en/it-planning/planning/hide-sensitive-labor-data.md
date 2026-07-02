---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Hide Sensitive Labor Data"
breadcrumb:
  - "Planning"
  - "Labor Planning"
source_path: "it-planning/planning/hide-sensitive-labor-data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Hide Sensitive Labor Data

Administrators can restrict visibility of specific columns in the Labor tab—such as
employee name, salary, or other compensation details—so that users without the required
permission can view labor entries without seeing sensitive fields.

Note: Admin or Budget Process Owner roles are required to configure sensitive data.

**Why You Would Use It**

- Protect employee confidentiality while still enabling cost center owners to review
  labor-related costs across departments.
- Ensure compliance with internal privacy or HR policies by hiding sensitive compensation
  details from broader audiences.
- Enable collaborative financial planning without exposing individual salary or bonus
  information.

## How It Works

1. Labor data is visible to users based on their permissions and cost-object access.
2. Columns marked as *Sensitive Data* in the labor schema (such as *Employee
   Name*, *Base Compensation*, *Other Compensation*) can be hidden for users
   who lack the **View Sensitive Columns** or **View Sensitive Financials** permission.
3. Users without permission will see the labor line items, but the sensitive columns will
   hidden—while other cost information (e.g., role, quantity, cost center, fully burdened
   cost) remains visible.
4. Administrators manage which columns are marked as sensitive via **Configuration →
   Schema → Labor**.
5. Cost Object Permissions determine visibility for sensitive labor data through the
   following settings:
   1. **View Sensitive Columns** – Allows users to view and edit attributes marked as
      *Sensitive Data* in the Labor tab.
   2. **View Sensitive Financials** – Allows users to view generated labor financials
      in the Summary tab.

## Setup Instructions

**1. Mark Sensitive Columns**

1. Go to **Configuration → Schema → Labor**.
2. Select the attribute(s) that contain private data (e.g., *Employee Name*, *Base
   Compensation*).
3. Enable the **Sensitive Data** checkbox.
4. Save the schema changes.

***2. Assign Cost Object Permissions***

1. Navigate to **Configuration → Cost Object Permissions**.
2. For each department, assign visibility by granting one or both of the following
   permissions:
3. **View Sensitive Columns** – To view or edit sensitive labor data in the Labor tab.
4. **View Sensitive Financials** – To view sensitive labor financials in the Summary
   tab.
5. Users without these permissions will not see sensitive columns in the Labor tab or
   related labor financials in the Summary tab.

***3. Verify Behavior***

1. Impersonate a user without sensitive-data access.
2. Open a plan and navigate to **Expenses → Labor**.
3. Confirm that:
4. Labor rows are visible, but sensitive columns (e.g., *Employee Name*, *Base
   Compensation*) are hidden.
5. The **Summary tab** does not display sensitive labor financial details.

For more information, refer to [FAQ: Hide Sensitive Labor Data](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(Opens in a new tab or window)").
