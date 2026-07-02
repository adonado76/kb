---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configure Report Permissions"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Customization"
source_path: "studio/new-uc/howtoguides/create-reports/config-rep-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure Report Permissions

**Objective:** Control which user roles can view specific reports and report components,
ensuring appropriate access to sensitive data.

**When to use:** Use report permissions when you want to:

- Restrict reports to specific departments or roles
- Show different report components to different user roles
- Create executive-only views of sensitive data
- Ensure compliance with data access policies

**Prerequisites:**

- Admin role (for report-level permissions and collection permissions)
- Power User role (for component-level visibility)
- Understanding of your organization's roles and access requirements
- Familiarity with user role management (see Section 3.4.2)

**Time estimate:** 5-10 minutes per report; varies for complex component visibility
configurations

## Understanding Report Permissions

TBM Studio provides multiple layers of access control for reports:

1. **Report-level permissions:** Control which roles can access an entire report
2. **Collection-level permissions:** Control which roles can access all reports in a
   collection
3. **Component-level visibility:** Show or hide specific components based on user
   role
4. **Row-level security (RLS):** Control which data rows users see (covered in Section
   3.4.2)

These layers work together—a user must have permission at each applicable layer to see
content.

## Report-Level Permission Options

When creating or editing a report, you configure who can view it:

|  |  |
| --- | --- |
| **Option** | **Description** |
| Everyone | All users with access to the project can view the report |
| Selected Roles | Only users in specified roles can view the report |
| Personal (viewable only by creator) | Only you can see the report—useful for drafts and personal analysis |

Note: The "Edit Personal Reports" permission (assigned to Analyst role by default) allows
users to create reports only they can view.

## Step-by-Step: Set Report Permissions When Creating a Report

1. On the **Home** tab, click **New > Report**.
2. Enter the report name and description.
3. In the **Viewable By** section, select your permission option: **Everyone** (leave
   as default) or **Selected Roles** (check the roles that should access this report).
4. Complete the remaining options and create the report.

**Step-by-Step: Change Permissions on an Existing Report**

1. Check out the report you want to modify.
2. On the **Report** tab (or **Project** tab), in the **Advanced** group, click
   **Permissions**.
3. In the permissions dialog, select **Everyone** to make the report available to all
   users, or select **Selected Roles** and check specific roles to restrict access.
4. Click **OK** to save.
5. Check in the report for changes to take effect.

## Step-by-Step: Set Component Visibility by Role

You can show or hide individual report components based on user role—useful for creating
one report with different views for different audiences:

1. Check out the report.
2. Select the component (table, chart, group box, etc.) you want to control.
3. On the **Report** tab, in the **Advanced** group, click **Visibility**.
4. In the **Report Component Visibility** dialog, configure the visibility options:
   - **Component contains data:** Hide if the component has no data
   - **User's current role is:** Check specific roles that should see this
     component
   - **Dynamic text evaluates to "hidden":** Use dynamic text to control visibility
     programmatically
5. Click **OK**.
6. Repeat for other components as needed and check in the report.

## Report Permission Strategies

**Strategy 1: Collection-Based Permissions**

- Create collections by audience (Executive, Finance, IT Operations)
- Set permissions at the collection level
- Add reports to appropriate collections

**Strategy 2: Report-Based Permissions**

- Organize reports by function in collections
- Set specific permissions on each report
- Useful when collection membership doesn't align with access needs

**Strategy 3: Component-Based Visibility**

- Create comprehensive reports with all relevant content
- Use visibility settings to show role-appropriate components
- Reduces the number of reports to maintain

## Common Pitfalls

- **Forgetting collection permissions:** A user might have report permission but still be
  blocked by collection restrictions.
- **Overly complex visibility rules:** Too many role-based visibility rules become
  difficult to maintain. Consider separate reports for significantly different audiences.
- **Not testing with actual users:** Always verify permissions by viewing reports as
  different role users.
- **Ignoring row-level security:** Report permissions control report access; RLS controls
  data access within reports. Both may be needed.

**Parent topic:** [Report Customization](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
