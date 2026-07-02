---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Submit, review, approve, and return plans"
breadcrumb:
  - "Planning"
  - "Workflows and Collaboration"
source_path: "it-planning/planning/aw-sub-return-approve.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Submit, review, approve, and return plans

Apptio Planning provides a structured workflow for submitting, reviewing, approving, and
returning departmental budgets. This ensures all plan data moves through the appropriate
approval levels before a plan is finalized.

Regardless of submission status, **all changes are always visible at the All Departments
level**. Submission status does not gate or block edits. The submission and approval steps
are designed for visibility, coordination, and accountability rather than restricting plan
changes.

## Submitting Plans

When a Department submits its plan:

- A **snapshot** of the submitted version is created (read-only).
- If email notifications are enabled, the appropriate approvers are notified based on
  the approval workflow in use.

You can submit plans from the **Expenses** page or the **Status** page.

**Submit from the Expenses Page** 

1. In the **Plan** menu, select a plan.
2. Navigate to **Plan** → **Expenses**.
3. From the **Department** dropdown, select a Department.
4. Open the **Ellipses menu (⋮)** and choose **Submit**.
5. *(Optional)* Enter a snapshot name.
6. Click **Submit**.

**Submit from the Status Page** 

1. Navigate to **Plan** → **Status**.
2. To submit multiple Departments, select the department’s checkboxes then **Actions**→ **Submit Selected.**
3. To submit one Department, select **Submit** in the **Actions** column.

**What Happens After Submission**

- **Hierarchical Approvals:** The next-level *parent Department Owner* is notified.
- **Multi-Level Approvals:** Approvers at Level 1 are notified first, then Level 2, and so
  on.

**Notes for Hierarchical Approvals:**

- Submitting a **Group Department**:
  - Automatically approves all child Departments
  - Creates snapshots for all children
  - Child Departments already approved are unchanged
- A Group Department becomes **In Progress** when at least one child submits a plan.
- If a plan is **Returned**, the submitted version is marked *Returned*. Any
  edits create a **new version**.

## Approving and Returning Plans

Users with approval permissions can approve or return plans at any time. If multiple users
share the same approval level, only one approval is required to move forward.

In Hierarchical Approvals, users with **Owner** edit level act as approvers. When a
higher-level Owner approves a plan, all lower-level approvals are automatically completed.

**Review Plans from the Expenses Page**

1. Navigate to **Plan** → **Expenses**.
2. Select a Department.
3. *(Optional)* Enable **View Updated** to show only changed line items.
4. Open the **Ellipses menu (⋮)** → select **Approve** or **Return**.
5. When returning a plan, you may add a comment.

**Review Plans from the Status Page** 

1. Navigate to **Planning** → **Status**.
2. *(Optional)* Toggle **Include View-Only Cost Objects** (requires *Enforce
   View Permissions*).
3. Approve/return using:
   1. **Actions column** (Approve, Return, Comment), or
   2. **Bulk actions** with selecting Department checkboxes then **Actions** →**Approve Selected** or **Return Selected**

If email notifications are enabled, approving a plan triggers an email to the next-level
approver.

In Hierarchical Approvals, returning a plan sends an email to the previous level’s Owner,
and the plan must be returned step-by-step down the hierarchy.

In Multi-Level Approvals, returning a plan notifies all users with edit access to the leaf
Department, and the plan is returned directly to the original Department Owner, bypassing
intermediate approval levels.

## Hierarchical Approvals: Approval Actions and Behavior

|  |  |  |
| --- | --- | --- |
| **Action** | **Leaf Department** | **Group Department** |
| **Submit** | Updates the Department Status to **Submitted** and creates a snapshot of the submitted version. Users with “Owner” edit level for the submitted department receive an email notification to review and approve the plan. | Updates the Group Department Status to **Submitted**, auto-approves all child Departments, and creates snapshots for all leaf Departments. Already approved children are unaffected. Users with “Owner” edit level for the submitted Group Department receive an email notification to review and approve the plan. |
| **Approve** | Updates the Department Status to **Approved.**  The next-level Owner in the Department hierarchy receives an email notification to review and approve the plan. | Updates the Group Department Status and any child Departments to **Approved**. The next-level Owner in the Department hierarchy receives an email notification to review and approve the plan. |
| **Return** | Updates the Department Status to **Returned**. Users with “Owner” edit level for the returned Department receive an email notification to revise and re-submit the plan. | Updates the Group Department Status as **Returned**. Child Departments remain unchanged unless explicitly returned by their owners. Returning a plan sends an email to the previous level’s Owner, and the plan must be returned step-by-step down the hierarchy. |

## Multi-Level Approvals: Approval Actions and Behavior

|  |  |
| --- | --- |
| **Action** | **Behavior** |
| **Submit** | Updates the Department Status to **Submitted** and creates a snapshot of the submitted version. Level 1 Approvers receive an email notification prompting them to review and approve the submitted plan. |
| **Approve** | Updates the Department status to **L[n] Approved**. Approvers at Level [n+1] receive an email notification to review and approve the plan. After all approval levels are completed, the Department status is set to **Approved.** |
| **Return** | Updates the Department status to **Returned**. Users with edit access are notified by email to revise and re-submit the plan. |

## Unlocking a Plan

Submitted, approved, or returned plans are read-only. Users with **Edit & Submit**
or **Owner**edit level may unlock a plan to continue editing. Unlocking resets the
Department status to **In Progress** and makes the plan editable.

1. Navigate to **Plan** → **Expenses**
2. Select a leaf Department, then click **Unlock this Cost Object** from the banner
   message, or select the Plan Versions menu and click **Unlock**.
3. Alternatively, from **Plan** → **Status**, select the Department checkbox, then
   **Actions** → **Unlock Selected**.

## Finalizing Plans

When all Departments are approved, Admins or Budget Process Owners may **Finalize Plan**
from the Expenses page to lock it.

1. Navigate to **Plan** → **Expenses**.
2. Select **All Departments** from the Department dropdown.
3. Open the **Ellipses menu (⋮)** → select **Finalize Plan**.
4. Select **Finalize**.

If there are unsubmitted changes, you will be notified. These changes will be included in
the finalized plan, but they will not carry an **Approved** status. You can re-open a
plan at any time to make further changes.
