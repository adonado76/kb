---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Plan States (New, Open, Final)"
breadcrumb:
  - "Planning"
  - "Creating and Managing Plans"
source_path: "it-planning/planning/plan-states.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Plan States (New, Open, Final)

Apptio Planning uses **Plan States** to control the lifecycle of a plan. Each state
governs who can access the plan, what actions can be taken, and when data is locked for
reporting. This ensures version control and proper governance during the planning process.

Note: Admin or Budget Process Owner roles are required to manage plan states.

## Plan States

Plans progress through three lifecycle states:

- **New**
  - Created and managed by administrators only.
  - Cost Center Owners cannot view or edit plans in this state.
- **Open**
  - Editable by Cost Center Owners and authorized users.
  - If email notifications are enabled, users with Edit access to a Department receive
    a notification when a plan is opened.
- **Final**
  - Read-only state.
  - Locks plan values, preserving the approved version for analysis and reporting.

## Changing a Plan State

To update the state of a plan:

1. Navigate to the **Plan.**
2. Select the **three-dot overflow menu** from top right corner.
3. To open a plan, select the **Open Plan** option.
4. Once a plan is open, return to the overflow menu and select **Finalize Plan**.
   1. If some Departments have unsubmitted changes, you can:
      - **Submit all changes and finalize** – submits all outstanding changes and
        moves the plan to Final.
      - **Finalize without submitting** – finalizes the plan, leaving unsubmitted
        Department changes excluded.
5. Administrators can always re-open a finalized plan if adjustments are required.
