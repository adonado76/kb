---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Default Roles"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Role-Based Access Control (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/default-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Default Roles

TBM Studio provides three default roles. Each role represents a common level of access for
different types of users.

**Administrator (Admin)**

|  |  |
| --- | --- |
| **Aspect** | **Details** |
| Capabilities | Full access to all features: create/edit projects, manage users and roles, configure security settings, build and promote projects, create reports, modify models, upload data, access all environments (Dev, Stage, Prod) |
| Typical Responsibilities | System configuration, user management, security administration, build lifecycle management, troubleshooting, component installation |
| When to Assign | IT finance managers who configure TBM Studio, system administrators responsible for the platform, senior analysts who manage the model and deployment process |
| Key Permissions | AccessDev, AccessStg, AccessProd, Edit Models, UploadData, ViewViewAllData, plus all view and report permissions |

Important:

**Admin and RLS**

Row-Level Security does not reliably restrict Admin users. Admin users have access to Studio mode
and can ultimately author reports that bypass RLS, add themselves to RLS mapping tables, and disable
RLS entirely. Do not rely on RLS to secure data from Admin users.

**Power User**

|  |  |
| --- | --- |
| **Aspect** | **Details** |
| Capabilities | Can create and edit reports, modify models and data transforms, upload data, and access development and staging environments. Can review error messages. Cannot manage users or modify domain-level settings. |
| Typical Responsibilities | Building and maintaining cost models, creating reports for stakeholders, transforming data, running staging calculations |
| When to Assign | IT finance analysts who build cost models, report developers who design and maintain reports, data analysts who manage data pipelines |
| Key Permissions | AccessDev, AccessStg, Edit Models, UploadData, DrillDown, Edit Personal Reports, plus standard view permissions |

**Business User**

|  |  |
| --- | --- |
| **Aspect** | **Details** |
| Capabilities | View reports and data in production. Limited to viewing—cannot modify models, transforms, or system configuration. Can interact with editable table components in reports where granted permission. |
| Typical Responsibilities | Consuming cost reports, analyzing IT spend, reviewing allocations, entering data in editable tables (if configured) |
| When to Assign | Business stakeholders who need to view reports, department managers reviewing their cost data, any user who needs read-only access |
| Key Permissions | AccessProd, ViewReportsSavedForEveryone, ViewObjectReports, ViewMetricReports, DrillDown, plus limited view permissions |

Note:

**Additional Roles**

Some installations include an Analyst role with the Edit Personal Reports permission, allowing
users to create personal reports visible only to themselves. Check with your administrator for the
complete list of roles in your environment.

**Parent topic:** [Role-Based Access Control (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
