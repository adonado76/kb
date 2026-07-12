---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Permission Inheritance and Effective Permissions"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Role-Based Access Control (RBAC)"
  - "Permission Inheritance and Effective Permissions"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/permission-inheritance.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Permission Inheritance and Effective Permissions

When a user is assigned to multiple roles, their effective permissions are the union of all permissions across all roles. There is no mechanism for one role to deny a permission granted by another role—permissions are purely additive.

Example: If User A is assigned both “Report Viewer” (with ViewObjectReports) and “Data Uploader” (with AccessDev and UploadData), User A can both view reports AND upload data.

When a user changes roles via their profile settings (My Account), they must refresh their browser for the new role to take effect. The active role determines the user’s current capabilities and affects what components are visible in reports.
