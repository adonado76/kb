---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Cost Object Permissions"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/manage-cost-object.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Cost Object Permissions

Note: *Only users with Admin or Budget Process Owner roles can manage Cost Object
Permissions.*

Cost Object Permissions control which users have access to specific departments within a
plan. Administrators can manage access globally across the environment or at the individual
plan level to ensure proper visibility, collaboration, and data security.

## Global vs. Plan-Level Permissions

Apptio Planning supports two levels of access management:

**Global Cost Object Permissions** 

The global **Cost Object Permissions**
page serves as a template for defining organization-wide access defaults.

- Located under **Configuration → Reference Data → Cost Object Permissions**.
- Defines default access settings that apply when new plans are created.
- Updates to Cost Object Permissions will be recorded in Change History.

**Plan-Level User Permissions**

Remember: Plan Level Cost Object
Permissions feature is enabled

Users must have the **ManagePlans** permission (granted
by default to Admin and Budget Process Owner roles) to view or edit Plan level permissions.

Each plan includes its own **User Permissions** page, accessible via **Plan → Settings →
User Permissions**, allowing administrators to assign or adjust access directly within a plan.

- Controls user access at the **plan level** for each Department.
- Overrides global permissions once a plan is created.
- When a plan is created from a baseline, the baseline plan’s User Permissions are copied to the
  new plan.

When **Plan Level Cost Object Permissions** feature is enabled, global permissions no
longer drive access automatically. Instead:

- **New Plan (No Baseline):** Global Cost Object Permissions are copied into the plan at
  creation.
- **New Plan (With Baseline):** User Permissions from the baseline plan are copied into the new
  plan.

## Configuring Cost Object Permissions

**To configure global permissions:**

1. Navigate to **Configuration → Cost Object Permissions**.
2. Use the table to define access levels by user and Department.
3. Use **Export → Export All** to download the permissions list as a .csv for bulk
   updates.

**To configure plan-level permissions:**

1. Navigate to **Settings****(Gear icon)** → **Company Profile**.
2. Select **General Configuration → Access & Permissions**
3. Ensure **Enable Plan Level Cost Object Permissions** checkbox is enabled
4. Open a plan and go to **Plan → Settings → User Permissions**.
5. Use the table to define access levels by user and Department.
6. Use **Export Permissions** from table level overflow menu (...) to download the
   permissions list as a .csv for bulk updates.
7. Use **Import Permissions** from table level overflow menu (...) to upload the
   modified .csv file.

**Field Descriptions**

|  |  |
| --- | --- |
| **Field** | **Description** |
| Cost Object | The unique identifier for the Department or cost center. |
| User Name | The user assigned to the Department. The list is based on users who have access to the Planning environment in Apptio Frontdoor. |
| Edit Level | Grants edit permissions: Owner, Edit & Submit, Edit, or View Only. Refer to [Approval Workflows](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(Opens in a new tab or window)") for details. |
| Approval Level | Defines approval rights (Levels 1–10) for Multi-Level Approvals. Refer to [Approval Workflows](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(Opens in a new tab or window)") for more details. |
| Can View Sensitive Columns | Allows viewing of columns marked as sensitive in the Labor line-item schema on the Labor and Summary tabs. See [*FAQ: Hide Sensitive Labor Data*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(Opens in a new tab or window)")*.* |
| Can View Sensitive Financials | Grants visibility into Summary tab financial line items that are derived from Labor data. See [*FAQ: Hide Sensitive Labor Data*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(Opens in a new tab or window)")*.* |

Important:

When Plan Level Cost Object Permissions feature is enabled

- Users must now be granted access **explicitly at the plan level**.
- Global Cost Object Permissions alone will not provide access to plans.

Note:

- Users with **Admin** or **Budget Process Owner** roles automatically have access
  to **all Departments** by default. All other users must be explicitly granted access.
- To restrict Budget Owners to only the Departments they are permitted to view, enable
  **Enforce View Permissions** in the **Company Profile**.
- When disabled, users can view the entire Department hierarchy but can only interact
  with the Departments they are assigned to.
- **Cost Object Permissions** cascade downward through the hierarchy unless a
  lower-level Cost Object has more specific permissions defined.

## Access Behavior in Plan Comparisons

If the Plan-Level Cost Object Permissions feature is enabled, plan comparison will function as
follows:

- Data in the Expenses table will be displayed based on the user’s permissions in the **source
  (comparison) plan**. For example, if a user has access to department D1 in source plan *Plan
  A* but does not have access to D1 in comparison plan *Plan B*, the user will still be able
  to view comparison details for D1 because access is granted in the source plan.
- Details in the Variance Analysis report will also be shown based on the user’s access in the
  source plan.
- If labor-sensitive data is enabled, the user must have permission to both labor-sensitive
  columns and financial data across **all compared plans** in order to view comparison
  results.

## Publish Plan-Level Permissions to All Plans

Note: This option is not available when **Multi Level Approval** feature is enabled,

**To bulk apply plan level permissions to all plans**:

1. Select permissions via checkbox on the **User Permissions** page (Plan > Settings >
   User Permissions)
2. Right-click or use the table-level overflow menu (**…**) to open the actions menu and
   select **Publish to All Plans**.
3. Click **Confirm**to apply the selected permissions to all plans.

**To bulk apply plan level permissions to global Cost Object Permissions**:

1. Select permissions via checkbox on the **User Permissions** page (Plan > Settings >
   User Permissions)
2. Right-click or use the table-level overflow menu (**…**) to open the actions menu and
   select **Publish to Reference Data**.
3. Click **Confirm** to apply the selected permissionsto Configuration > Cost Object
   Permissions

## Publish Global Cost Object Permissions to All Plans

With **Plan Level User Permissions** enabled, Admins and Budget Process Owners can publish
**global Cost Object Permissions** directly to selected plans. This simplifies centralized
permission management and keeps multiple plans aligned without manual effort.

**To publish global permissions to all plans:**

1. Navigate to Configuration **→** Cost Object Permissions
2. From the **three-dot menu**, select **Publish All Permissions to Plans**.
3. In the **Publish Configuration** dialog, choose one of the following options:
   1. **Update Permissions**: Updates only the matching permissions from global Cost Object
      Permissions and the plan-level User Permissions for the selected plans.
   2. **Replace All Permissions**: Removes all existing permissions from the selected plans and
      replaces them entirely with the global Cost Object Permissions.
4. Use the **Plans** multi-select dropdown to choose one, multiple, or all plans to which the
   permissions should be published.
5. Click **Confirm**

**Result:** All permissions from **Global Cost Object Permissions** are copied to
**Plan-Level User Permissions** for the selected plans based on the chosen publish option.

## Bulk Delete User Permissions from All Plans

Note: This option is not available when **Multi Level Approval** feature is enabled,

**To bulk delete user’s permissions from all plans**:

1. Select permissions via checkbox on the **User Permissions** page (Plan > Settings >
   User Permissions)
2. Right-click or use the table-level overflow menu (**…**) to open the actions menu and
   select **Delete Permission From All Plans**.
3. Click **Confirm** to delete the selected permissions to all plans and Configuration >
   Cost Object Permissions.
