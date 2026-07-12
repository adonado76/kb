---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Manage Email Notifications"
breadcrumb:
  - "Planning"
  - "Workflows and Collaboration"
source_path: "it-planning/planning/manage-email-notifications.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Manage Email Notifications

Apptio automatically sends email notifications for key events in the planning process. These
notifications help inform users of required actions, status changes, and updates made during
budget submission and approval workflows.

Admins can control whether users should receive email notifications or not.

## Email Notifications for Plan Status Changes

Email notifications are sent based on a user’s **role**, **edit permissions**, and
**position in the approval chain**.

**When a Plan is Opened**

Users with edit access to the plan (**Edit Level: Owner, Edit & Submit, Edit**)
receive an email notification.

**When a Plan is Submitted**

- Users with edit access to the submitted Department (**Edit Level: Owner, Edit &
  Submit, Edit**) receive an email confirming submission.
- **Level 1 Approvers** receive an email notification requesting approval.

**When a Plan is Partially Approved**

- Users with edit access to the approved Department (**Edit Level: Owner, Edit &
  Submit, Edit**) receive an email indicating the plan was approved by the current
  approval level.
- The **next-level approver** in the approval chain receives an email requesting
  approval.
- This process continues through all approval levels.

**When a Plan is Fully Approved**

Users with edit access to the approved Department (**Edit Level: Owner, Edit & Submit,
Edit**) receive an email confirming final approval.

**When a Plan is Returned**

Users with edit access to the Department (**Edit Level: Owner, Edit & Submit,
Edit**) receive an email notification that the plan was returned.

**When a Plan is Unlocked**

Users with edit access (Edit Level: Owner, Edit & Submit, and Edit) for the Department
will receive an email notification that their plan was revoked/unsubmitted.

**When a Comment is Added**

Users with edit access to the related Department receive an email notification.

These events ensure users are informed when their review or action is required. Refer to
[Approval Workflows](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(Opens in a new tab or window)") for more details.

## Enable Email Notifications

Note: *Admin or Budget Process Owner roles are required to perform these tasks.*

1. Navigate to **Settings (Gear icon) → Company Profile**.
2. Enable **Send Email Notifications for Planning Process Events.**
3. Select **Save and Exit**.
