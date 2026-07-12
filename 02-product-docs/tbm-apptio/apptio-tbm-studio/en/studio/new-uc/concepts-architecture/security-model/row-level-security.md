---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Row-Level Security (RLS)"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
source_path: "studio/new-uc/concepts-architecture/security-model/row-level-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Row-Level Security (RLS)

Row-level security (RLS) is TBM Studio’s data-level security mechanism. While roles and
permissions control what features and reports a user can access, RLS controls which rows of data a
user can see within those reports and tables. RLS ensures that users see only the data relevant to
their organizational scope—even when they access the same reports.

## What is Row-Level Security?

RLS works by filtering data based on the identity of the logged-in user. When a user opens a
report or views a table, the system checks the RLS configuration to determine which rows that
specific user is authorized to see. Rows that are not associated with the current user are
hidden.

**Why RLS Matters**

- **Multi-tenant data:** When multiple business units share the same TBM Studio instance, RLS
  ensures each business unit sees only its own data.
- **Organizational boundaries:** Managers can be restricted to seeing cost data for their own
  department or region, while executives see aggregate data across the organization.
- **Regulatory compliance:** RLS helps enforce data access policies that may be required by
  internal governance or external regulations.

Note:

**RLS vs. Report Permissions**

RLS and report permissions are complementary, not alternatives. Report permissions control
whether a user can access a report at all. RLS controls which data appears in reports the user can
access. You typically need both: report permissions to organize the user experience, and RLS to
enforce data boundaries.

- **[How RLS Works](../../../../studio/new-uc/concepts-architecture/security-model/how-rls-worls.html)**
- **[RLS Architecture](../../../../studio/new-uc/concepts-architecture/security-model/rls-arch.html)**
- **[RLS Scope: Where RLS Applies](../../../../studio/new-uc/concepts-architecture/security-model/rls-scope.html)**
- **[RLS Inheritance and Flow](../../../../studio/new-uc/concepts-architecture/security-model/rls-inheritance.html)**
