---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Managing Plans"
breadcrumb:
  - "Planning"
  - "Creating and Managing Plans"
source_path: "it-planning/planning/manage-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Managing Plans

The **Plans** page provides a central workspace to create, view, and manage your
plans. From here, you can open existing plans, configure plan properties, and perform lifecycle
actions such as archiving or deleting.

Note: Admin or Budget Process Owner roles are required to manage plans.

## Accessing Plans

1. Open the left-hand navigation pane.
2. Select **Planning > Plans**.
3. Use the tabs at the top of the page to switch between:
   - **Available Plans** – Shows all active plans that are accessible to Cost Center
     Owners.
   - **Archived Plans** – Shows archived plans, accessible only to users with Admin or
     Budget Process Owner roles.
   - **All Plans** – Shows all plans in the system.

## Viewing Plan Properties

Select the **pencil icon** next to a plan to open the **Properties pane**, which
displays the following details:

- **Plan Name** – Rename the plan by clicking the pencil icon.
- **Type** – Indicates whether the plan is a *Budget* or *Forecast*.
- **State** – Shows the current lifecycle stage (*New, Open, or Final*).
- **Status** – Displays whether the plan is *Available* or *Archived*.
- **Created Date** – The date the plan was created.
- **Plan Length** – The total number of years covered by the plan.
- **Plan Start Year** – The first year included in the plan.
- **Plan Description** – Allows Administrators or Budget Process Owners to enter plan
  descriptions, key assumptions, guidance, or announcements. The description is displayed in the Plan
  Header across all pages, including Expenses, Dashboard, and others. Users can show or hide the
  description at any time using the bell icon in the Plan Header.

## Archiving and Restoring Plans

- **Archive a plan** – Moves it from the Available list to Archived.
  - To archive a single plan: right-click the plan and select **Archive**.
  - To archive multiple plans: select them using the bulk-edit checkbox, right-click,
    and select **Archive**.
- **Restore a plan** – Moves it back to the Available list.
  - To restore a single plan: right-click the plan and select **Restore**.
  - To restore multiple plans: select them, right-click, and select **Restore**.

## Deleting Plans

Plan deletion is a two-step process:

- **Soft Delete** – The plan is immediately removed from the UI when an admin deletes
  it. It is inaccessible to users but can be restored within two days by logging a support
  ticket.
- **Hard Delete** – Two days after a soft delete, the plan data is permanently
  removed.

This process ensures faster UI removal and provides a two-day safety window for
recovery. When multiple plans are deleted, they are processed sequentially during cleanup.

- To delete a single plan: right-click and select **Delete**.
- To delete multiple plans: select them with the bulk-edit checkbox, right-click, and
  select **Delete**.
