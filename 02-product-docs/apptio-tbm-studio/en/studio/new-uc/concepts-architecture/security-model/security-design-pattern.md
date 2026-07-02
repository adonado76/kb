---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Security Design Patterns"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Best Practices"
source_path: "studio/new-uc/concepts-architecture/security-model/security-design-pattern.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Security Design Patterns

The following patterns address common security scenarios in TBM Studio. Use these as starting
points and adapt them to your organization’s specific requirements.

**Pattern 1: Role-Based Access by Job Function**

|  |  |
| --- | --- |
| **Aspect** | **Details** |
| Scenario | Different teams need different levels of access: finance analysts build models, department managers view reports, and executives see summary dashboards. |
| Implementation | Create three roles: Model Builder (Power User + model permissions), Report Viewer (Business User + specific report collection access), and Executive (Business User + executive dashboard collection access). |
| RLS | Not required if all roles should see all data. Apply RLS only if some roles should see restricted data. |
| Report Permissions | Assign report collections to specific roles. Use component visibility to show different chart layouts for executives vs. analysts. |

**Pattern 2: Organizational Hierarchy**

|  |  |
| --- | --- |
| **Aspect** | **Details** |
| Scenario | Managers should see data for their teams, directors should see their departments, and VPs should see their divisions. |
| Implementation | Create mapping tables that reflect the organizational hierarchy. Each manager’s mapping includes their team’s cost centers. Directors’ mappings include all cost centers in their departments. |
| RLS | Apply RLS filtering by cost center or organizational unit. Use multiple mapping tables if needed to handle the hierarchy cleanly. |
| Full Access | Create a separate full-access mapping table for VPs and executives who need to see all data, using the Is Admin flag pattern. |

**Pattern 3: Multi-Tenant Data**

|  |  |
| --- | --- |
| **Aspect** | **Details** |
| Scenario | Multiple business units share a single TBM Studio instance but should see only their own data. |
| Implementation | Create RLS mapping tables keyed by business unit. Each user is mapped to one or more business units. Apply RLS to every table that contains business unit data. |
| RLS Completeness | Critical: RLS must be applied to ALL tables in the model that contain business-unit-specific data, including drill-through targets. Missing RLS on any table creates a data leak. |
| Testing | Use the Preview Filter and impersonation to verify that users in each business unit see only their data across all reports and drill paths. |

**Parent topic:** [Security Best Practices](../../../../studio/new-uc/concepts-architecture/security-model/security-best-practices.html)
