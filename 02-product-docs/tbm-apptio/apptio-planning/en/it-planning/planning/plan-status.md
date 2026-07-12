---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Plan Status"
breadcrumb:
  - "Planning"
  - "Workflows and Collaboration"
source_path: "it-planning/planning/plan-status.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Plan Status

The **Plan Status** page in Apptio Planning provides a centralized view for tracking
the progress of departmental plans throughout the planning and approval process. It helps users
monitor plan ownership, current status, and recent activity across all departments in a plan
cycle.

## Plan Status Overview

Each department’s plan moves through a defined workflow of status changes as it progresses
through the planning and approval process:

- **In Progress** – The initial state when a department begins working on its plan.
- **Submitted** – Indicates the plan has been submitted for review and approval.
- **Approved** – The plan has been reviewed and approved.
- **Returned** – The plan has been sent back for revisions or additional input.

The **Status** table displays the following key details for each department:

- **Owners** – The user(s) assigned as owners of the department’s plan.
- **Status** – The current state of the plan (In Progress, Submitted, Approved, or
  Returned).
- **Last Action** – The date and time of the most recent status update.
- **Available Actions** – Contextual actions available based on the user’s
  permissions (e.g., Approve, Return, Comment).

## Viewing and Navigating the Status Table

***Hierarchical and List Views***

- For **hierarchical approvals**, you can toggle between a **Hierarchical View**
  (to view departments in their organizational structure) and a **List View** (for a
  flat list of all departments).
- Use the **View Selector** at the top of the page to switch between views.

***Multilevel Approvals***

- For **multilevel approval workflows**, the table is available only as a **List
  View**.
- An additional column, **Approval Level**, shows the current progress of the
  approval process — for example, *“1 of 3 approvals”*.
- As each level completes, the status will transition sequentially through levels (*L1
  Approved → L2 Approved → L3 Approved*), and the plan will display as
  **Approved** once all required approvals are complete.

## Approving and Managing Plans

Users with approval permissions can manage the plans for the departments they are assigned
to:

- **Approve** – Marks the plan as approved for the current level of approval.
- **Return** – Sends the plan back to the department owner for revisions.
- **Comment** – Allows approvers or reviewers to leave comments without changing the
  status.

## Bulk Actions and Exporting History

You can perform actions on multiple departments at once using the **Actions menu** at
the top of the page:

- **Bulk Submit, Approve** or **Return** multiple departments simultaneously.
- **Export History** to download a detailed record of all status changes, including
  timestamps and users.

Exporting provides a complete audit trail of plan progress and approvals for reporting
and compliance purposes.
