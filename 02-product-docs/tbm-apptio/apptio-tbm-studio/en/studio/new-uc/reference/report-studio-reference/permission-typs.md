---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Permission Types"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
source_path: "studio/new-uc/reference/report-studio-reference/permission-typs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permission Types

**View Permissions**

View permissions determine which roles can see a report when navigating through the Project
Explorer or Report Collections.

**Configuring View Permissions:**

1. Check out the report
2. On the Report tab, in the Advanced group, click Permissions
3. Select the roles that should have access to view the report
4. Choose one of the following options:

**Everyone**: All users with project access can view the report

**Selected Roles**: Only users assigned to specific roles can view the report

**Viewer Capabilities:**

- Navigate to and view the report
- Use slicers and filters to explore data
- Export report data (if export permissions allow)
- Print reports or generate PDFs
- Subscribe to email notifications (if configured)

**View-Only Restrictions:**

Users with view-only roles cannot:

- Check out or modify report configuration
- Change component settings or layout
- Modify report permissions
- Create custom tables or charts (unless assigned to an Analyst role)

**Edit Permissions**

Edit permissions are typically controlled through project-level roles rather than individual
report settings. Users who can edit reports must have:

- A role that includes content creation permissions
- The ability to check out documents in the project

**Editor Capabilities:**

1. Check out and modify report layout
2. Add, remove, or configure report components
3. Modify table and chart configurations
4. Change report properties and settings
5. Save and check in changes

**The Edit Personal Reports Permission**

A specific permission called Edit Personal Reports allows users to create reports visible only to
themselves. This permission:

- Is assigned to the Analyst role by default
- Can be assigned to any custom role
- Enables personal report creation without affecting other users
- Creates reports that do not appear in collections for other users

**Admin Permissions**

Report administration capabilities are tied to the Admin role (or custom roles with equivalent
permissions). Administrators can:

- Configure report-level permissions
- Manage report collection membership
- Delete custom reports (out-of-the-box reports cannot be deleted)
- Deactivate reports to prevent calculation
- Hide reports from report collections
- Manage email subscriptions for other users
- Configure component visibility by role

**Administrative Actions Available:**

|  |  |  |
| --- | --- | --- |
| **Action** | **Location** | **Notes** |
| Set report permissions | Report tab → Permissions | Requires checkout |
| Assign to collection | Report tab → Assign to Collection | Requires checkout |
| Delete report | Home tab → Delete | Custom reports only |
| Deactivate report | Report tab → Clear Active checkbox | Prevents calculation |
| Hide from collection | Project tab → Report Collections | Toggle visibility |

**Execute Permissions (Email Subscriptions)**

Report execution through scheduled email subscriptions requires specific permissions:

|  |  |
| --- | --- |
| **Permission** | **Capability** |
| **EmailSubscriptionsCreate** | Create email subscriptions for self and others |
| **EmailSubscriptionsFilteredCreate** | Create subscriptions with filter parameters |

**Subscription Limitations:**

- Email recipients must be in authorized domains for the customer environment
- Row-level security (RLS) is not supported in email subscriptions
- Only TBM Administrators see the Email Subscription option by default

**Parent topic:** [Report Permissions](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
