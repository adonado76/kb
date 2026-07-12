---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "How RBAC Works"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Role-Based Access Control (RBAC)"
  - "How RBAC Works"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/how-rbac-work.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# How RBAC Works

1. Permissions define specific capabilities (such as “EditModels,” “ViewReports,” or “UploadData”).
1. Roles group permissions into meaningful bundles that correspond to job functions (such as “Admin,” “Power User,” or “Business User”).
1. Users are assigned to one or more roles. A user’s effective permissions are the combination of all permissions in their assigned roles.

This approach has significant advantages over direct user-permission assignment: easier auditing, consistent access patterns, simplified onboarding (assign a role instead of configuring dozens of individual permissions), and faster updates when organizational needs change.
