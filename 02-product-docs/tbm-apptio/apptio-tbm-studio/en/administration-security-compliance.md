---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Security & Compliance"
breadcrumb:
  - "Administration"
  - "Security & Compliance"
source_path: "SSWRJM/studio/new-uc/admin/sec-comp.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Security & Compliance

Content Type: Conceptual / How-To

Target Audience: Administrators, Security Officers

Prerequisites: Admin role, understanding of data security requirements

TBM Studio provides multiple security layers to protect sensitive financial data and ensure compliance with organizational policies. This section covers domain security settings, row-level security, and data governance practices.

## Domain Security Settings

Domain security settings control authentication policies, password requirements, and session management for all users in your Apptio environment.

To access domain security settings:

1. Navigate to the Project tab.
1. Click Domain Security .
1. Configure password policies, session settings, and authentication options.

Password Policy Settings

| Setting | Description |
| --- | --- |
| Setting | Description |
| Min Password Length | Minimum number of characters required for passwords |
| Min Password Age | Days before a password can be changed. Value of -1 means unlimited. |
| Max Password Age | Days until password expires and must be changed. Value of -1 means unlimited. |
| Password History | Number of previous passwords that cannot be reused |

## Row-Level Security (RLS)

Row-level security ensures users only see data they are authorized to access. RLS filters data at the row level based on user attributes, allowing the same report to show different data to different users.

Where RLS applies:

- Transform tables - Filters visible rows before data enters reports
- Editable tables - Restricts what data users can view and modify
- Reports - Aggregations reflect only the filtered view for each user

Note: When publishing editable tables with RLS enabled, rows the user cannot see are preserved, not overwritten. This prevents data loss when users publish their changes.

## Data Governance Practices

Effective data governance ensures data quality, security, and compliance. TBM Studio provides several features to support governance workflows.

## Closing Periods

Closed periods prevent data modifications while still allowing reporting. Use closed periods for finalized fiscal periods to maintain data integrity.

## Data Freshness Rules

Data freshness rules monitor when tables are updated and send notifications if data becomes stale. This helps ensure timely data loads and prevents reporting on outdated information.

To create a data freshness rule:

1. Navigate to Project > Data Freshness Rules .
1. Click Create Rule and specify the expected refresh frequency.
1. Configure email notifications for missed updates.
1. Associate the rulerules with one or more tables.

## Data Lineage

Data lineage tracks the flow of data through your TBM Studio project, showing where data originated, how it has been transformed, and where it is used. Lineage is essential for impact analysis and troubleshooting.

Lineage use cases:

- Impact analysis - Understand what would be affected by changing or removing a column or table
- Cleanup - Identify orphan tables or unused calculated metrics
- Data privacy - Trace where sensitive data exists and is exposed

To access lineage:

- Right-click any entity in Project Explorer and select Trace Lineage for this document
- Right-click the document tab at the bottom of the workspace and select Trace Lineage
