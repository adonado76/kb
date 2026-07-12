---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Report and Component Permissions"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Report and Component Permissions"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/report-component-permission.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Report and Component Permissions

While roles control broad access and RLS controls data visibility, report and component permissions provide an additional layer of control over the user experience in Report Studio. These permissions determine which reports a user can view and which components within a report are visible to different roles.

## Report Permissions

Report permissions control who can view and who can edit each report. Beginning with TBM Studio 12.7, report permissions are managed through a streamlined interface rather than creating separate report copies for each role.

Report Permission Model

When you create a report, you select who can view it. The options include:

- All users: The report is visible to anyone with access to the project.
- Specific roles: Only users assigned to the selected roles can see the report.
- Personal only: The report is visible only to the creator. Requires the Edit Personal Reports permission (assigned by default to the Analyst role).

Report permissions are configured through the Permissions dialog, accessible from the Project tab in the Advanced group.

Report Collections and Permissions

Report collections group related reports for easy navigation. Administrators can set role permissions for collections, controlling which user roles can access reports within each collection. Only administrators can create report collections, and only in the Costing Standard project. Once created, collections are available across the entire project.
