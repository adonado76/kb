---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Best Practices for Row-Level Security"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Security"
source_path: "studio/new-uc/howtoguides/work-with-data/bp-rls-wn.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Best Practices for Row-Level Security

## Planning Your RLS Strategy

- **Start with clear requirements:** Document who needs access to what data before
  implementing RLS. This prevents rework and ensures consistent security across tables.
- **Use meaningful table names:** Name mapping tables descriptively (e.g., "BU Access -
  Standard Users", "Regional Access - Managers") so others can understand their
  purpose.
- **Consider future growth:** Use a "full access" table pattern rather than listing all
  values for power users. This way, adding new business units or cost centers doesn't
  require updating multiple user entries.

**Implementation Tips**

- **Apply RLS consistently:** If you secure the Cost Source table, also secure related
  tables like IT Resource Towers to prevent data leakage through drill-downs or related
  reports.
- **Test thoroughly:** Use the preview filter and impersonation features to verify RLS
  works as expected for different user types before deploying to production.
- **Document your configuration:** Keep records of which tables have RLS, what mapping
  tables they reference, and the business rules they implement.

**Maintenance Considerations**

- **Establish update processes:** Create procedures for adding/removing users and
  changing access. Consider automating with DataLink for large organizations.
- **Audit regularly:** Periodically review mapping tables to ensure they reflect
  current organizational structure and access requirements.
- **Coordinate with HR/IT:** Align RLS updates with employee onboarding, offboarding,
  and organizational changes.

## How RLS Works Across TBM Studio

Understanding how RLS behaves in different contexts helps you implement comprehensive
security:

**RLS in Transform Tables**

- RLS filters data at retrieval time, so unauthorized rows never reach the user.
- Each table requires its own RLS step; security is not inherited from related
  tables.

**RLS in Editable Tables**

- RLS restricts which rows users can see and edit in editable tables.
- When an editable table is published, hidden rows (those the user cannot see) are
  preserved—not overwritten or deleted.
- This is critical for scenarios where distributed managers update their own cost center
  data.

**RLS in Reports**

- Reports display only rows the user is authorized to see based on RLS rules.
- Aggregations (totals, averages) reflect only the user's filtered data.
- In model overview reports, each tier reflects its own RLS settings—values may not add up
  across tiers if RLS is applied differently to different tables.

**RLS with Model Allocations**

- RLS does not affect how allocations are calculated. The model processes all data
  regardless of security settings.
- Users see allocated costs only for the business units or cost centers they have access
  to, even if those costs originated from other areas.

## What's Next

- [Security
  Model](../../concepts-architecture/studio-model/security-architecture.html) — Understand the conceptual architecture of security in TBM Studio,
  including authentication, authorization, and how RLS fits into the broader security
  framework.
- Section 6.3: Security & Compliance — Learn about administrator-level security
  configuration, audit logging, compliance considerations, and enterprise security best
  practices.
- [Create Reports](../create-reports/report-basic.html) — Learn how to build
  reports that leverage RLS to deliver personalized views to different user audiences.
- [Manual Data Entry](manual-data-entry.html) — Learn about editable tables and how RLS enables
  distributed data management.

**Parent topic:** [Data Security](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
