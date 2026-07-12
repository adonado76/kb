---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Permission Model Architecture"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
source_path: "studio/new-uc/reference/report-studio-reference/permission-model-arch.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permission Model Architecture

**How Report Permissions Fit into the Security Hierarchy**

TBM Studio's report permission model operates within a layered security architecture:

|  |  |  |
| --- | --- | --- |
| **Level** | **Scope** | **Controlled By** |
| **Domain** | All projects in a domain | Enhanced Access Administration |
| **Project** | All assets within a project | Project-level role assignments |
| **Report Collection** | Groups of related reports | Collection-level permissions |
| **Report** | Individual report | Report-level permissions |
| **Component** | Elements within a report | Component visibility settings |
| **Data (RLS)** | Row-level data access | Row-Level Security project |

Permissions flow from broader to narrower scope. A user must have appropriate access at each
level to view a report and its data. For example, a user with report-level view permission still
cannot see data filtered by RLS unless their user ID is included in the RLS mapping tables.

**Relationship to Project Permissions**

Report permissions are a subset of the broader project permission model. The project-level role
assigned to a user determines their baseline capabilities:

**Inherited from Project Role:**

- Ability to access TBM Studio and specific projects
- Ability to create new reports (requires content creation permissions)
- Ability to check out and modify configuration
- Access to administrative features

**Configured at Report Level:**

- Which roles can view specific reports
- Which roles can view specific components within reports
- Report collection membership and visibility

Note: Project roles are managed through Enhanced Access Administration. For information on
configuring user roles, see Section 6.2: User Management.

**Relationship to Row-Level Security (RLS)**

Row-level security and report permissions serve different purposes and work together:

|  |  |  |
| --- | --- | --- |
| **Aspect** | **Report Permissions** | **Row-Level Security** |
| **Controls** | Access to report UI | Access to data rows |
| **Granularity** | Report/component level | Individual data rows |
| **Configured in** | Report Studio | Row-Level Security project |
| **Based on** | Role assignment | User ID mapping |

A user might have permission to view a report but see limited data based on RLS configuration.
Conversely, RLS does not grant report access—users still need appropriate report-level permissions.

Important: Row-level security affects all users but does not secure data from Admin
users. Admin users have access to Studio mode and can author reports that bypass RLS, add themselves
to RLS mapping tables, or disable RLS entirely. Do not rely solely on RLS to secure sensitive data
from administrators

.

**Parent topic:** [Report Permissions](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
