---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Permission Assignment"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
  - "Permission Assignment"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/permission-assignment.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Permission Assignment

Role-Based Permissions

Permissions in TBM Studio are primarily assigned through roles. Each user is assigned to one or more roles that determine their access level.

Default System Roles:

| Role | Description | Report Capabilities |
| --- | --- | --- |
| Role | Description | Report Capabilities |
| Admin | Full system access | Create, edit, delete, configure all reports |
| Power User | Advanced configuration | Create and edit reports |
| Analyst | Report consumption with customization | View reports, create personal reports, add custom tables/charts |
| View Only | Report consumption only | View and filter reports |

Assigning Permissions to Roles:

1. On the Report tab, click Permissions
1. Select Selected Roles
1. Click the Select roles dropdown
1. Choose the roles that should have access
1. Click OK and check in the report

Permission Inheritance

Inheriting from Project

Reports inherit baseline access from project-level settings:

- Users must have project access to view any reports in that project
- Project-level role assignments determine who can access the project
- Reports can further restrict (but not expand) access beyond project permissions

Override vs. Inherit Settings

Report-level permissions override collection-level settings. The effective permission is the most restrictive combination:

| Collection Setting | Report Setting | Effective Access |
| --- | --- | --- |
| Collection Setting | Report Setting | Effective Access |
| Everyone | Everyone | Everyone |
| Everyone | Analysts only | Analysts only |
| Admins only | Everyone | Admins only |
| Analysts, Admins | Admins only | Admins only |
