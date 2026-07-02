---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configure Custom Roles"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "User Management"
source_path: "studio/new-uc/howtoguides/manage-users-permission/config-custom-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure Custom Roles

**Objective:** Create custom roles with specific permission combinations to meet unique
organizational needs.

**When to use:** When default roles don't provide the exact permission combination your
users need, or when you need fine-grained control over specific capabilities.

**Time estimate:** 15-30 minutes per role

**Prerequisites**

- Admin role required.
- Clear understanding of the permissions needed for the target user group.
- Documentation of your organization's access control requirements.

## When to Create Custom Roles

Consider creating a custom role when:

- Users need a subset of Power User permissions but not full access.
- You need API-only accounts with limited permissions for automation.
- Different teams require different report visibility.
- You need to restrict access to specific environments (Dev, Stage, Prod).
- Compliance requirements mandate separation of duties.

## Steps

1. **Access Role Management.** In Enhanced Access Administration, navigate to the **Roles
   and Permissions** section.
2. **Create a new role.** Click **Add Custom RoleName the role.** Enter a name and
   description that indicates the role's purpose (e.g., "Data Uploader", "Report Viewer -
   Finance", "API Integration").
3. **Select permissions.** Choose the specific permissions this role should have. Common
   permission categories include:

   |  |  |
   | --- | --- |
   | **Permission Category** | **Examples** |
   | **Environment Access** | AccessDev, AccessStg, AccessProd |
   | **Data Operations** | UploadData, DrillDown, ViewAllData |
   | **Reporting** | ViewMetricReports, ViewObjectReports, ViewTransformReports, ViewReportsSavedForEveryone, Edit Personal Reports |
   | **Export** | CanExportExcel, CanExportPDF (enables data download) |
4. **Save the role.** Click **Save** to create the custom role.
5. **Test the role.** Assign the role to a test user and verify the permissions work as
   expected before rolling out to other users.

## Example Custom Roles

***Example 1: Data Uploader Role***

For users who only need to upload data files but don't need to build models or view all
reports.

- AccessDev
- UploadData

***Example 2: Finance Report Viewer***

For finance team members who need production report access but no configuration
capabilities.

- AccessProd
- ViewMetricReports
- ViewObjectReports
- CanExportEcel

***Example 3: API Integration Account***

For automated processes that upload and download data via API.

- AccessDev
- UploadData
- CanExportExcel

## Common Pitfalls

- **Over-permissioning:** Adding too many permissions defeats the purpose of a custom
  role. Start minimal and add permissions as needed.
- **Missing dependent permissions:** Some permissions require others to function. Test
  thoroughly to ensure the role works as intended.
- **Duplicate "Upload" permissions:** Note that "UploadData" and "Upload Data" are
  separate permissions. Include both for complete upload functionality.
- **Not documenting custom roles:** Always document what each custom role is for and
  which permissions it includes.

## What's Next

After setting up users and roles, you may want to:

- **Configure report permissions** to control which reports each role can access. See [Access Control](access-control-intro.html).
- **Implement row-level security** to restrict data visibility based on user identity. See
  [Access Control](access-control-intro.html).
- **Set up SSO integration** for enterprise authentication. See [User Management](../../admin/user-management.html) for detailed reference.
- **Monitor user activity** using Apptio Usage reports. See [User Management](../../admin/user-management.html).

**Parent topic:** [User Management](../../../../studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html)
