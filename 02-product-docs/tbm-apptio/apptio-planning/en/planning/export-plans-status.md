---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Export a plan's status history"
breadcrumb: []
source_path: "planning/export-plans-status.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Export a plan's status history

## About this task

Apptio planning applications maintain a record of actions taken in each plan. Admins and Budget
Process Owners can see the full history of submission, approval, and return activity of individual
Services, Departments, and Projects, and Admins can export this information. This information can
help answer the "who, what, and when" questions about a plan's status actions.

## Procedure

- **To export all Cost Object version history:**

  1. In the Plan menus at the top right, select a Plan,
     a Cost Object category, and a cost object or
     cost object group.

     [Learn more about
     navigating in Planning](navigate-apptio-planning.html#Toolbar)
  2. Navigate to
     Planning > Status. The
     Plan Status page appears.
  3. Select Actions > Export
     History. The planning application generates a version history for all cost
     objects in `.csv` format.
- **The exported details include the following:**

  - Cost Object Code.
  - Cost Object Name.
  - Version: Cost Object version in which an action was performed.
  - Action: the action that was performed.
  - User: Name of the user who performed the action.
  - Date/Time: When each action was performed. The time value is in GMT/UTC
    format, unless otherwise noted.
  - Return Comment: The comment, if any, that was submitted with the Return
    action.

  Note: Plans that are in the New state or newly opened (that is, no actions have been taken yet) will
  result in a blank .csv with only the header row.
