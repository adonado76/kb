---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Set Report Permissions by Role"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "Access Control"
source_path: "studio/new-uc/howtoguides/manage-users-permission/set-report-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set Report Permissions by Role

|  |  |
| --- | --- |
| **Objective** | Control which user roles can view and interact with specific reports |
| **Time Estimate** | 10-15 minutes per report |
| **Prerequisites** | Admin role or custom role with appropriate permissions; roles configured in the project |

## When to Use This Procedure

Use report permissions when you need to restrict entire reports or report collections to
specific user roles. This is the first line of access control—if a user cannot see a report,
they cannot access any of the data within it.

**Steps**

**Option A: Set Permissions When Creating a Report**

1. Navigate to **TBM Studio** and click the **Home** tab.
2. Click **New**, then select **Report**.
3. Enter a name and description for the report.
4. In the **Viewable By** section, select which roles can view this report. Options depend
   on your role permissions.
5. Complete the remaining report configuration and click **OK**.

**Option B: Modify Permissions on an Existing Report**

1. In the **Project Explorer**, navigate to **Reports** and locate the report.
2. Check out the report.
3. On the **Projects** tab, in the **Advanced** group, click **Permissions**.
4. In the permissions dialog, select or deselect roles to control report visibility.
5. Click **Apply** to save your changes.
6. Check in the report to apply changes to the staging environment.

**Option C: Configure Component Visibility by Role**

For scenarios where different roles should see different components within the same report,
use role-based component visibility instead of creating separate reports:

1. Check out the report and open it in the report designer.
2. Create a **Group** container for the components that should be role-specific.
3. Add the components (tables, charts) that should be visible to a specific role into the
   group.
4. Configure the group to be visible only to the target role.
5. Repeat steps 2-4 for each role that needs a different view.
6. Layer the groups on top of each other on the reporting surface.
7. Check in the report.

Note: If a user has multiple roles that have different group visibility settings, they will see
the components for the role that is on top of the group stack.

## Expected Results

- Users with permitted roles see the report in Report Finder and can access it
- Users without permitted roles do not see the report listed
- Component visibility (if configured) shows role-appropriate content within shared
  reports

## Common Pitfalls

- **Legacy permissions (pre-12.7):** In older configurations, enabling role-based
  permissions created separate copies of reports for each role. TBM Studio 12.7+ uses a
  unified approach. If you have legacy report copies, see "Migrate report access control" in
  Section 6.3.
- **Out-of-the-box reports:** You cannot delete OOTB reports. Use permissions to restrict
  access instead.
- **Forgetting to check in:** Permission changes do not take effect until the report is
  checked in and the calculation completes.

## Related Tasks

- [Create and manage report collections](../create-reports/build-rc.html)
- [Configure custom roles](config-custom-roles.html)
- Disable reports (Section 6.3)

**Parent topic:** [Access Control](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
