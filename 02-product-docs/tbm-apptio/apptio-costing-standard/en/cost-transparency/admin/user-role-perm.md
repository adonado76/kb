---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "User Roles and Permissions"
breadcrumb:
  - "Costing Standard"
  - "Administration"
source_path: "cost-transparency/admin/user-role-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# User Roles and Permissions

IBM Apptio Costing Standard uses role-based access control to ensure users have
appropriate visibility and permissions across cost models, data, and reports. Roles define the
level of access within the application, while permissions provide more granular control over
specific tasks. This structure helps organizations balance governance, security, and
self-service access across Finance, IT, and Business stakeholders. IBM Apptio uses the
**Frontdoor** application to manage users, their roles, and permissions across the
platform. Frontdoor provides centralized identity and access management, ensuring consistent
user governance across projects and solutions.

## Manage Users

Administrators can manage users by adding new users, activating or deactivating existing
users, exporting the user list, and deleting users when access is no longer required.

To manage users, navigate to the **Settings** (![gear](_829212255.)) menu and select **Access Administration**. The
Access Administration console opens with the **Users** tab selected by default. From this
page, administrators can search across all user records, filter and sort the user list, and
hide inactive users using the available controls at the top of the page.

Use this screen to add, update, or remove user access as needed to maintain proper
governance and security.

For more details on how to perform these actions, go [here.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-users "(Opens in a new tab or window)")

## Manage User Roles and Permissions

Roles define a set of permissions and capabilities that control the actions users can
perform within IBM Apptio. Each user is assigned one or more roles that determine their
level of access and functionality.

To manage roles, navigate to the **Settings (**![gear](_8791317.)**)** menu and select **Access Administration**.
From the left-hand navigation menu, click **Roles and Permissions**. This page allows
administrators to add, modify, or remove role assignments for users within a project.

For more details on how to manage roles and permissions, go [here.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Opens in a new tab or window)")

## Standard User Roles

IBM Apptio Costing Standard includes these predefined roles:

- **Admin**
- Full administrative access across Costing Standard, TBM Studio, Datalink, Planning,
  Interactive Benchmarking applications with no functional restrictions.
- **Enterprise Admin**
- Performs advanced administrative tasks including self-service promotions and DataLink
  configuration and execution.
- **Power User**
- Creates and manages projects and models, uploads and transforms data, and builds
  reports and dashboards.
- **Analyst**
- Creates personal reports and analyses using available data and views existing
  reports.
- **Service Manager**
- Uploads data and reviews reports related to services and operational performance.
- **Project Manager**
- Reviews project-related financial and operational reports to track costs, progress, and
  outcomes.
- **Finance**
- Views financial reports to analyze costs, budgets, and variances across IT
  domains.
- **Business User**
- Views shared reports made available across the organization for general business
  insight.
- **Executive User**
- Views all published reports to support strategic and executive decision-making.
- **View Only**
- Provides read-only access to production reports; users can view published content but
  cannot modify or create reports.

## Custom Roles

In addition to the standard roles, IBM Apptio allows you to create **custom roles**
using the Frontdoor application. Custom roles enable organizations to tailor user access
based on specific responsibilities and governance requirements.

You can also duplicate an existing standard role and modify its permissions by adding or
removing capabilities to meet your organization’s needs.

For more details on how to create and manage custom roles, go [here](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles#Manageuserpermissionsandroles__Createcustomroles__title__1 "(Opens in a new tab or window)").
