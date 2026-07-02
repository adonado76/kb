---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How RBAC Works"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Role-Based Access Control (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/how-rbac-work.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How RBAC Works

The RBAC model has three components that work together:

1. **Permissions** define specific capabilities (such as “EditModels,” “ViewReports,” or
   “UploadData”).
2. **Roles** group permissions into meaningful bundles that correspond to job functions (such as
   “Admin,” “Power User,” or “Business User”).
3. **Users** are assigned to one or more roles. A user’s effective permissions are the
   combination of all permissions in their assigned roles.

This approach has significant advantages over direct user-permission assignment: easier auditing,
consistent access patterns, simplified onboarding (assign a role instead of configuring dozens of
individual permissions), and faster updates when organizational needs change.

**Parent topic:** [Role-Based Access Control (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
