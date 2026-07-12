---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Custom Roles"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Role-Based Access Control (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/custom-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Custom Roles

When the default roles do not fit your organization’s needs, you can create custom roles with
precisely the permissions required. Custom roles allow you to follow the principle of least
privilege—granting each user exactly the access they need and nothing more.

**When to Create Custom Roles**

- You need a role between Power User and Business User—for example, users who can view staging
  data but not edit models
- You want to restrict data upload access to a specific team while allowing broader report viewing
- API service accounts need minimal permissions (such as upload-only or download-only access)
- You want to separate report editing from model editing responsibilities

**Permission Granularity**

Permissions in TBM Studio fall into four categories:

|  |  |  |
| --- | --- | --- |
| **Category** | **Examples** | **Typical Use** |
| View Permissions | ViewObjectReports, ViewMetricReports, ViewTransformReports, ViewReportsSavedForEveryone, ViewAllData | Controlling which types of reports and data users can see |
| Edit Permissions | Edit Models, Edit Personal Reports, UploadData | Controlling who can modify models, create reports, and upload data |
| Access Permissions | AccessDev, AccessStg, AccessProd | Controlling which environments (development, staging, production) users can access |
| Execute Permissions | DrillDown, InteractiveBenchmarksAndCostData, View Proactive | Controlling interactive features like drill-through navigation and benchmark access |

**Custom Role Design Principles**

1. Start with the closest default role and adjust permissions rather than building from scratch.
2. Document the purpose and intended audience for each custom role.
3. Test custom roles by impersonating a user assigned to the role before deployment.
4. Review custom roles periodically to ensure they still match organizational needs.

Note:

**Best Practice: API Roles**

For API service accounts, create dedicated custom roles with only the permissions needed for the
specific integration. For upload-only accounts, grant AccessDev, and UploadData. For download-only
accounts, grant AccessProd, AccessStg, DrillDown, and the relevant View permissions

**Parent topic:** [Role-Based Access Control (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
