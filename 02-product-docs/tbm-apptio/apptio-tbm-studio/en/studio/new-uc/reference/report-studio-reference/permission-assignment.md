---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Permission Assignment"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
source_path: "studio/new-uc/reference/report-studio-reference/permission-assignment.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permission Assignment

**Role-Based Permissions**

Permissions in TBM Studio are primarily assigned through roles. Each user is assigned to one or
more roles that determine their access level.

**Default System Roles:**

|  |  |  |
| --- | --- | --- |
| **Role** | **Description** | **Report Capabilities** |
| **Admin** | Full system access | Create, edit, delete, configure all reports |
| **Power User** | Advanced configuration | Create and edit reports |
| **Analyst** | Report consumption with customization | View reports, create personal reports, add custom tables/charts |
| **View Only** | Report consumption only | View and filter reports |

**Assigning Permissions to Roles:**

1. On the Report tab, click Permissions
2. Select Selected Roles
3. Click the Select roles dropdown
4. Choose the roles that should have access
5. Click OK and check in the report

Tip: When restricting a report to specific roles, ensure that all users who need access
are assigned to at least one of the selected roles.

**Permission Inheritance**

**Inheriting from Project**

Reports inherit baseline access from project-level settings:

- Users must have project access to view any reports in that project
- Project-level role assignments determine who can access the project
- Reports can further restrict (but not expand) access beyond project permissions

**Override vs. Inherit Settings**

Report-level permissions override collection-level settings. The effective permission is the most
restrictive combination:

|  |  |  |
| --- | --- | --- |
| **Collection Setting** | **Report Setting** | **Effective Access** |
| Everyone | Everyone | Everyone |
| Everyone | Analysts only | Analysts only |
| Admins only | Everyone | Admins only |
| Analysts, Admins | Admins only | Admins only |

**Parent topic:** [Report Permissions](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
