---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configure Editable Table Permissions"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "Access Control"
source_path: "studio/new-uc/howtoguides/manage-users-permission/config-et-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure Editable Table Permissions

|  |  |
| --- | --- |
| **Objective** | Control which users or roles can edit, upload, or delete data in editable tables |
| **Time Estimate** | 15-20 minutes per editable table |
| **Prerequisites** | Editable table created; Admin or Power User role; users and roles configured |

## When to Use This Procedure

Use editable table permissions when different users or roles should have different edit
access to data entry tables. This is especially important for distributed data entry
scenarios where cost center managers, application owners, or other stakeholders maintain
their own portions of mapping or reference data.

## Types of Editable Table Permissions

Editable tables support several permission types:

|  |  |
| --- | --- |
| **Permission** | **What It Controls** |
| Upload Permission | Which roles can upload data files to the editable table |
| Show History Permission | Which roles can view the change history for the table |
| Delete All Rows Permission | Which roles can delete all rows from the editable table (when enabled) |

## Steps

## Option A: Configure Basic Role-Based Permissions

1. In the **Project Explorer**, navigate to the report that contains the editable
   table.
2. Check out the report.
3. On the editable table shown on the report, open the table's **Advanced Properties**
   (right-click > Properties > Advanced).
4. Configure the following permissions as needed:
   - **Upload Permission:** Select the roles that can upload data
   - **Show History Permission:** Select the roles that can view change history
   - **Delete All Rows Permission:** Select the roles that can perform bulk deletion (if
     enabled)
5. Click **Apply** to save your changes.
6. Check in the report.

## Option B: Configure Advanced User/Table Access (Table Upload Component)

For granular control over which users can access which tables through a Table Upload
component in reports:

1. Create an editable table to define access mappings with these columns:
   - **Table:** The name of the editable table
   - **Role:** (Optional) The role that has access
   - **User:** (Optional) The specific user email that has access
2. Populate the access mapping table. For example:

   |  |  |  |
   | --- | --- | --- |
   | **Table** | **Role** | **User** |
   | Acme Contracts | Power User |  |
   | Acme General Ledger |  | bob@acme.com |
   | Acme IT Org Mapping |  | roxanne@acme.com |
3. In your report, add the **Table Upload** component.
4. Click the **Config** button on the Table Upload component.
5. Toggle the **Configuration Type** to **Advanced**.
6. In the **Table** field, enter the name of your access mapping editable table.
7. Click **Apply** and save the report.

Users will now see only the tables they have access to in the Table Upload dropdown.

## Option C: Apply Row-Level Security to Editable Tables

For scenarios where users should only see and edit their own rows within an editable table
(e.g., cost center managers editing their own cost center data):

1. Configure RLS mapping tables as described in the previous section ("Implement Row-Level
   Security").
2. Enable RLS on the editable table by adding an RLS step in the transform pipeline.
3. When users access the editable table through a report, they will only see rows matching
   their RLS permissions.
4. Users can only edit cells in rows they can see.

Important: When a user publishes an RLS-filtered editable table, hidden rows are
preserved. The publish operation does not delete rows the user cannot see.

## Expected Results

- Users see only the editable tables they have permission to access
- Upload, history, and delete functions are available only to permitted roles
- With RLS enabled, users see and edit only their authorized rows
- Publishing preserves rows hidden by RLS

## Common Pitfalls

- **Concurrent editing conflicts:** When User A begins editing a cell, User B is locked
  out of that cell until A saves or cancels. Plan data entry windows for distributed teams to
  minimize conflicts.
- **Validation errors blocking publish:** Invalid data (failed validation rules) cannot
  be published. Ensure users understand validation requirements before data entry.
- **Enriched table row deletion:** Users cannot delete rows from enriched editable tables
  because the rows are based on the source transform table.

## Related Tasks

- [Create editable tables](../work-with-data/create-blank-et.html)
- [Configure validation rules for
  editable tables](../work-with-data/config-dd-valid.html)
- [Set up editable table publishing
  schedules](../work-with-data/setup-et-publish.html)

**Parent topic:** [Access Control](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
