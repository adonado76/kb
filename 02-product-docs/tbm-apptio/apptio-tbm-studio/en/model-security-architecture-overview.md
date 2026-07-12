---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Security Architecture Overview"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Architecture Overview"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/security-architecture.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Security Architecture Overview

TBM Studio provides a multi-layered security model that controls who can access the system, what actions they can perform, and which data they can see. Understanding these layers—and how they interact—is essential for designing a security configuration that protects sensitive financial data while enabling the right people to do their work effectively.

## Security Layers

| Layer | Question Answered | Mechanism | Scope |
| --- | --- | --- | --- |
| Layer | Question Answered | Mechanism | Scope |
| 1. Authentication | Who are you? | Username/password, SSO, API keys | Domain-wide |
| 2. Authorization (RBAC) | What can you do? | Roles and permissions assigned to users | Project-level and report-level |
| 3. Data Security (RLS) | What data can you see? | Row-level security filters on tables | Table-level, flows to reports |

These layers work together like concentric rings. Authentication is the outermost ring—it determines whether you gain entry to TBM Studio at all. Authorization is the middle ring—it determines which features, reports, and actions are available to you. Data security is the innermost ring—it filters the actual rows of data visible to you within the reports and tables you can access.

## Security Scope

- Domain-level security: Password policies, session management, and authentication settings apply to all users across all projects in a domain. Configured via the Domain Security dialog on the Project tab.
- Project-level security: Users and roles are defined at the project level. A user’s role in one project may differ from their role in another project within the same domain.
- Report-level security: Report permissions control which roles can view or edit specific reports. Report collections can also be restricted by role.
- Component-level security: Individual report components (tables, charts, groups) can be configured to show or hide based on the user’s current role.
- Data-level security (RLS): Row-level security filters restrict which rows of data a user can see, regardless of the report they are viewing. RLS operates across Data Studio tables, model objects, editable tables, and reports.

A user must pass all applicable layers to see data. For example, a Business User with a role that grants access to a cost report will still only see the data rows permitted by their RLS configuration. If their role does not include the report, they will not see it at all—regardless of whether RLS would have allowed the data.

## Security Decision Framework

1. Who needs access to TBM Studio? → Set up user accounts and authentication.
1. What should each person be able to do? → Assign roles with appropriate permissions.
1. Which reports should each person see? → Configure report permissions by role.
1. Should different people see different data in the same report? → Implement row-level security.
1. Should report layouts vary by role? → Use component visibility settings
