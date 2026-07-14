---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "00-Administration-Users"
source_files_count: 7
last_updated: "2026-07-13"
---

# 00-Administration-Users

## Manage Users and User Groups

<!-- sub-header -->
- **breadcrumb:** Administration > Manage Users and User Groups
- **source_path:** SSVCLNQ/admin/manage-users-and-user-groups.html
- **original_file:** administration-manage-users-user-groups.md
- **images:** []

In Cloudability, users and user groups help define who can access the platform and what they can see or do. There are three key components:

A User in Cloudability is an individual who has been granted access to the platform. Each user has a unique identity, typically linked to an email address. Users are created and authenticated through FrontDoor , which handles both authentication and authorization. Once provisioned in FrontDoor, the user can be assigned specific Cloudability roles such as MSP Admin, Billing Manager, or Cloudability User/Admin. These roles determine the user's permissions and access levels within the platform.

Learn more Manage Users, User Views and Dashboards

A User Group in Cloudability is a set of users bundled together to simplify access management and view assignment. Admins can create user groups and add individual users to them. Once created, these groups can be assigned to specific Views to control visibility and access efficiently.

Learn more Manage User Groups

An Entra ID Group in Cloudability refers to user group managed within Microsoft Entra ID (formerly Azure Active Directory), Microsoft's cloud-based identity and access management service. Instead of manually creating user groups in Cloudability, organizations can import Entra ID Groups along with their associated users.

Learn more Manage Entra ID Groups

---

## Manage Entra ID Groups

<!-- sub-header -->
- **breadcrumb:** Administration > Manage Users and User Groups > Manage Entra ID Groups
- **source_path:** SSVCLNQ/admin/manage-entra-id-groups.html
- **original_file:** groups-manage-entra-id.md
- **images:**
  - 03-media/apptio-cloudability-standard/manage-entra-id-groups_image1.png
  - 03-media/apptio-cloudability-standard/manage-entra-id-groups_image2.png
  - 03-media/apptio-cloudability-standard/manage-entra-id-groups_image3.png
  - 03-media/apptio-cloudability-standard/manage-entra-id-groups_image4.png
  - 03-media/apptio-cloudability-standard/manage-entra-id-groups-auto-sync1.png
  - 03-media/apptio-cloudability-standard/manage-entra-id-groups-auto-sync2.png
  - 03-media/apptio-cloudability-standard/manage-entra-id-groups_image5.png
  - 03-media/apptio-cloudability-standard/View-assignment-visibility-for-Entra-ID-Groups.png
  - 03-media/apptio-cloudability-standard/Picture14.png
  - 03-media/apptio-cloudability-standard/Picture15.png

### Overview

The Entra ID Groups integration allows Cloudability Admins to manage user access by syncing user group information directly from Microsoft Entra ID (formerly Azure Active Directory). Instead of manually creating and maintaining user groups within Cloudability, you can import existing Entra ID groups and assign them to Views for controlled access.

This feature streamlines permission management by aligning Cloudability access controls with your organization's Entra ID Groups. Any updates to group membership in Entra ID (e.g., when users join or leave teams) are automatically reflected in Cloudability during sync - ensuring consistent, up-to-date access without manual intervention.

### How to

Prerequisites

- You are a Cloudability Administrator.
- You have completed credentialing of Microsoft Entra ID tenant. To learn more, visit Connect Microsoft Entra ID

### Import Entra ID Groups into Cloudability

Entra ID Groups cannot be created manually in Cloudability and they must be imported or synced from your Entra ID tenant. To import:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Click Sync Entra ID Groups button.
1. In the dialog that appears, enter the criteria (Scope and the text filter basis which Cloudability will import the Entra ID Groups) and click Next .
1. Click Sync Now to begin importing. This action pulls in all Entra ID Groups from the credentialed tenant that match your specified criteria. Note: Entra ID Groups are read-only : These groups or it’s users cannot be modified within Cloudability. While you can delete an imported Entra ID group from Cloudability, you cannot modify the group name or its users. Import Criteria : You can use different sync criteria to import Entra ID groups into Cloudability Sync Duration : Syncing may take a few seconds to a few minutes depending on the number of groups and users being imported. Sync Behavior : An existing group will be overwritten during the sync. Any addition or removal of users from Entra ID would get synced. If a group has been deleted in Entra ID , it will not be automatically removed from Cloudability. You must delete it manually. Only one group can be deleted at a time. Rationale for Sync Behavior : Cloudability cannot distinguish if a group is missing due to deletion in Entra ID or due to a change in sync criteria. A group might still be associated with active View assignments. Automatically deleting such a group could unintentionally revoke access for multiple users.
1. Click a group eye icon to check the list of users belonging to the group.

### Setup Auto-Sync for Entra ID Groups

Changes to Entra ID groups happen continuously, which can make it difficult to keep Entra ID groups in Cloudability fully up to date through manual syncing. To eliminate this manual effort, Cloudability allows you to configure an automatic sync schedule.

You can set up a daily, weekly, or monthly auto-sync using specific filter criteria. Entra ID Groups will then be automatically synced based on the configured schedule.

To set up auto-sync for Entra ID Groups:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Click on the Pencil (Edit) Icon next to Auto Sync.
1. To enable auto-sync, turn on the Enable auto sync toggle.
1. In the Auto Sync Configuration modal: Review or update the filter criteria. Select the sync frequency ( Daily , Weekly , or Monthly ). Choose the sync time and timezone .
1. Click Save to enable the auto-sync schedule.
1. To disable auto-sync at any time, turn off the Enable auto sync toggle and Save.

### Delete Entra ID Groups in Cloudability

If a group was deleted on the Entra ID side, it will not be automatically deleted in Cloudability - you must delete it manually.

To delete an Entra ID Group:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Find the group you want to delete.
1. Click the ellipsis (…) icon and select 'Delete' menu option.

### View assignment visibility for Entra ID Groups

If an Entra ID Group was used in View assignment, the system blocked it's deletion. Admins can see a read-only list of all Views where a group is assigned. The list displays the View names and clearly indicates when a group is not used in any View, helping streamline group cleanup and reduce manual effort.

To identify which Views are using the Entra ID Group.:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Views column shows the number of Views where this Entra ID Group is assigned.
1. Find the group you want to validate.
1. Click the ellipsis (…) icon and select 'Views' from the menu.
1. In side panel, you'll see the list of views where this Entra ID Group is assigned.

![View assiged to a Entra ID Group](../images/View-assignment-visibility-for-Entra-ID-Groups.png)

### Assign View Access to Entra ID Groups

To assign view's access to an Entra ID Group or multiple Entra ID Groups:

1. Navigate to Organize > Views and create or edit a View. Click Permissions > Select ‘ Users & Groups ’ and Shared With dropdown. Assign View to the imported Entra ID groups from the drop down. Save this to assign the View to all users within the Entra ID Group(s).
1. Optionally, add a combination of User Groups, Entra ID Groups and individual Users to the View.
1. If a view was originally created as Private or Org level view, View Admin can change it to a shared with Users & Groups by selecting “Users & Groups” option view and assign the Users, User Groups and/or Entra ID groups.

---

## Manage User Groups

<!-- sub-header -->
- **breadcrumb:** Administration > Manage Users and User Groups > Manage User Groups
- **source_path:** SSVCLNQ/admin/manage-user-groups.html
- **original_file:** groups-manage-user.md
- **images:**
  - 03-media/apptio-cloudability-standard/Picture3.png
  - 03-media/apptio-cloudability-standard/Picture4.png
  - 03-media/apptio-cloudability-standard/Picture5.png
  - 03-media/apptio-cloudability-standard/Picture6.png
  - 03-media/apptio-cloudability-standard/View-assignment-visibility-for-User-Groups.png
  - 03-media/apptio-cloudability-standard/Picture7.png
  - 03-media/apptio-cloudability-standard/Picture8.png

### Overview

A User Group in Cloudability is a logical collection of users created to simplify access management and streamline assignment of Views.

By organizing users into groups, admins can more easily apply consistent settings, control view access, and maintain governance across your FinOps practice.

### How to

Prerequisites

- You are a Cloudability Administrator.

### Create a User Group in Cloudability

To create a User Group:

1. Navigate to Settings > Users & Groups > User Groups tab.
1. To create a new user group, click ‘ New User Group ’. You can create multiple user groups at once by separating the names by commas.
1. Click Edit Users and add users to the User Group from the list of users.
1. Click Save .

### Delete a User Group in Cloudability

To delete a User Group:

1. Navigate to Settings > Users & Groups > User Groups tab.
1. Find the group you want to delete.
1. Click the ellipsis (…) icon and select 'Delete' menu option.

![ user gropus error screenshot ](../images/Picture6.png)

### View assignment visibility for User Groups

If a User Group was used in View assignment, the system blocked it's deletion. Admins can see a read-only list of all Views where a group is assigned. The list displays the View names and clearly indicates when a group is not used in any View, helping streamline group cleanup and reduce manual effort.

To identify which Views are using the User Group.:

1. Navigate to Settings > Users & Groups > User Groups tab.
1. Views column shows the number of Views where this User Group is assigned.
1. Find the group you want to validate.
1. Click the ellipsis (…) icon and select 'Show views' from the menu.
1. In side panel, you'll see the list of views where this User Group is assigned.

![View assiged to a User Group](../images/View-assignment-visibility-for-User-Groups.png)

### Assign View Access to User Groups

To assign view's access to a User Group or multiple User Groups:

1. Navigate to Organize > Views and create or edit a View. Select the users and groups option and a value from the Shared With dropdown. Assign View to group(s) from the dropdown (under category ‘User Groups’). Click Save to assign the View to all users within the User Group(s).
1. Optionally, add a combination of User groups, Entra ID Groups and individual users to the View.
1. If a view was originally created as Private or Org level view, View Admin can change it to a shared with Users & Groups by selecting “Users & Groups” option view and assign the Users, User Groups and/or Entra ID groups.

---

## Manage Users, User Views and Dashboards

<!-- sub-header -->
- **breadcrumb:** Administration > Manage Users and User Groups > Manage Users, User Views and Dashboards
- **source_path:** SSVCLNQ/admin/create-and-manage-users.html
- **original_file:** groups-manage-users-user-views-dashboards.md
- **images:**
  - 03-media/apptio-cloudability-standard/pencil-icon.jpg
  - 03-media/apptio-cloudability-standard/Manage-Users.png
  - 03-media/apptio-cloudability-standard/add_and_manage_users_4.png
  - 03-media/apptio-cloudability-standard/Picture2.png

### Overview

As a Cloudability Admin, you can manage a user’s access to views and dashboards within Cloudability. This includes configuring their default view, setting a default dashboard, and granting access to specific views. Other user management tasks, such as adding or removing roles, are handled through Access Administration .

Roles and permissions in Cloudability

Learn how to manage user permissions and roles in Access Administration .

### Managing user views and dashboards

1. Navigate to Settings > Users & Groups > Users tab .
1. Select the check box next to the name of user you want to manage, then select .
1. You can also search for the user using either the user name or email.
1. To edit views and dashboards for multiple users, select at least two users, and then select Edit Multiple .
1. In the Edit a User pane that appears, you can configure the following settings for the user: Default View – Sets the view the user sees by default upon login Default Dashboard – Specifies the default dashboard assigned to the user View Access – Grants the user access to specific views. You can filter them based on all ‘Selected’, ‘Unselected’ and ‘All’ criteria. Note: Hierarchical views can only be assigned/unassigned via the Views Permission page. Note: When users are assigned a view, they can not see any data until they have the ViewsFeatureFullAccess permission. For more information, visit Managing user permissions and roles
1. Select Save .

### Setting a Default View for a New User

Cloudability allows you to configure a default view that new users see when they log in for the first time, as long as they’ve been granted access to that view. This default view is often referred to as the org-level default view .

If an admin hasn't set a default view for a user, or if the user hasn’t configured one in their profile ( Manage Profile > Preferences ), Cloudability will automatically default them to this org-level default view upon login.

To configure the default view, select a value from the New User Default View dropdown.

---

## Users and User Groups FAQs

<!-- sub-header -->
- **breadcrumb:** Administration > Manage Users and User Groups > Users and User Groups FAQs
- **source_path:** SSVCLNQ/admin/users-and-user-groups-faqs.html
- **original_file:** groups-users-user-faqs.md
- **images:** []

### Are Entra ID and IDP synonymous?

Entra ID is one of the most widely used IDP (Identity Provider). There are many other IDPs such as Okta, PingIdentify. At present, we’re only supporting Microsoft Entra ID (aka Azure AD).

### Which role in Cloudability can access the features?

The feature is accessible with existing permission ‘ UserManagementFeatureFullAccess’ itself. So if an user had access to ‘User Management’ feature earlier, they'll also have access to User Groups and Entra ID Groups features.

### How many User Groups or Entra ID Groups can be created in Cloudability?

There is no limit on how many User Groups or Entra ID Groups can be created.

### Is there a limit to how long a user group name can be?

Yes, group names in Cloudability can be up to 63 characters long. This limit aligns with the character limit for Entra ID groups in Microsoft Entra ID.

### How much time it takes for changes to take effect when assigning Views to Groups?

Changes would be almost immediate. The users who get access to View via Groups would be able to see the views almost immediately.

### Will changes done at Entra ID side automatically reflect in Cloudability?

### How much time it takes to Synchronize the Entra ID Groups?

It may take from few milliseconds to a few minutes based on the number of groups being synced and the number of users in each group. If sync process is taking longer, you’ll need to wait. You can always come back and verify the “Last Synced” Date field to know if Sync was completed.

### What happens if a user who is member of Entra ID Group doesn’t exist in Cloudability?

While Syncing, Cloudability performs a check whether the Entra ID group's users exist in Cloudabilty or not. If a user doesn’t exist in Cloudability, it won’t be imported. So, if you had 10 users in an Entra ID Group and only 8 existed in Cloudability then only 8 users will be imported.

### When synchronizing Entra ID group(s), why are some users not being imported into Cloudability?

This typically happens when users in Entra ID (Azure AD) do not have a valid email address configured or if the configured email does not match the user's email in Cloudability. Even if the user exists in the group, Cloudability will only import users whose email addresses are both present and matches with those in the Cloudability. Please check the email id of user is not missing, empty or mis-configured in Entra ID.

### Can a user be part of multiple User Groups?

Yes, users can be part of multiple Groups, in both Entra ID groups and Manual User Groups.

### Can we use these Groups with HVs (Hierarchical Views)?

Yes. Both User Groups and Entra ID Groups will be available with HVs as well.

### What is the roadmap for supporting User Groups and Entra ID Groups for sharing Reports, Dashboard, Alerts etc?

Support for User Groups and Entrap ID Groups is planned but not yet available across all features. Currently, these groups cannot be used for sharing or alerting in the areas listed below:

1. Sharing Report and Dashboards: Currently it only has option to share across Entire Organization or Users.
1. Sharing Container Dashboards: Currently it only has option to share across Entire Organization or Users
1. Creating Alerts for Anomaly detection
1. Sharing Workload Plans
1. Creating Alerts for CFP Plan

The above capabilities are on the roadmap and we are actively working to expand group-based sharing and alerting across these features. Updates will be communicated as functionality becomes available.

### Are these Groups supported in Apptio BI?

No, User Groups and Entrap ID Groups are not supported in Apptio BI. Not to mention that Cloudability Reports and Dashboard will honor the Views access based on these Groups.

---

## Roles and permissions in Cloudability

<!-- sub-header -->
- **breadcrumb:** Administration > Roles and permissions in Cloudability
- **source_path:** SSVCLNQ/admin/iam.html
- **original_file:** administration-roles-permissions-in-cloudability.md
- **images:** []

Roles give users permission to access specific views and functions within Cloudability.

By default, all user roles have access to some basic features in Cloudability including cost analytics for reporting, dashboards and TrueCost Explorer. Additional features can be accessed by assigning permissions to the role.

Roles in Cloudability

The following roles can be assigned to users of Cloudability :

| Role name | Role permissions | Application Types |
| --- | --- | --- |
| AI Assistant User | User with this permission will be able to see Apptio AI Assistant widget in Cloudability and will be able to interact with it. | Cloudability Premium, Cloudability,Cloudability Standard, Cloudability Essential |
| AdvancedContainersFullAccess | Admin Role For Cloudability Advanced Containers powered by Kubecost. | AdvancedContainers, Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| AdvancedContainersViewOnly | View Only Role for Cloudability Advanced Containers powered by Kubecost. | AdvancedContainers, Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloud Data Ingestion | This default role is used for CDI users. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Admin | Grants access to all admin functions in Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Billing Admin | Enables customers to set the currency preferences for their org in Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Governance Automation User | This role has the permission GovernanceFeatureConfigurationFullAccess. The user with this role will have full access to Configuration operations (other than Policies) for Cloudability "Governance" feature. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Governance PR Approver | This role has the permission GovernanceFeaturePRApprovalAccess. The user with this role will have access to approve blocked pull requests in Cloudability "Governance" feature. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Governance Policy Admin | This role has the permission GovernanceFeaturePolicyFullAccess. The user with this role will have full access to the policy configuration functionality (view, create, update policies) under the Cloudability "Governance" feature menu item. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Non-restricted User | This role has all the permissions under the Cloudability User role and ViewsFeatureFullAccess. The user with this role will have access to all cloud data under your organization. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Savings Automation Admin | Default role for users that should have administrative access to the Cloudability Savings Automation application. | Cloudability Savings Automation |
| Cloudability Savings Automation User | Default role for non-admin users of Cloudability Savings Automation. | Cloudability Savings Automation |
| Cloudability User | Limited access to Cloudability without any data modification privileges. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability View Management (for migration only) | Please do NOT use this role as it is for migrating "restricted" flag only. As we deprecating "restricted" flag in Cloudability, users WITHOUT "restricted" flag are assigned with this role automatically to continue accessing View management page. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| CloudabilityContainerProvisioner | Can provision and deploy Containers metrics-agent. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| CloudabilityContainerUploader | Can upload Containers data to Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudwiry Admin | Default role for users that should have administrative access to the Cloudwiry application. | Cloudwiry, Cloudability Savings Automation |
| Cloudwiry User | Default role for users that should have non-administrative access to the Cloudwiry application. | Cloudwiry, Cloudability Savings Automation |
| MSP API User | Access to all MSP/CCB features in own environment. | Commercial Billing (MSP) |
| MSP Admin | Access to all MSP/CCB features in own environment. Admin access in end consumers' environments. | Commercial Billing (MSP) |
| MSP Billing Manager | Access to billing module and the price book for each end consumer. This persona will be able to edit/set rates and mark ups for each end consumer, as well as access cost/consumption data for all end consumers as well as add additional costs/line items. | Commercial Billing (MSP) |

Roles in Access Administration affecting Cloudability

The following Access Administration roles are mapped to corresponding roles in Cloudability :

| Role name | Role permissions |
| --- | --- |
| Admin : | This role can add, edit, or delete users in Access Administration . This role functions across all Apptio applications, including Cloudability. |
| Administrator | This role has full access to Cloudability. This role is granted to users who log in to Cloudability with either the Admin or Cloudability Admin role on Access Administration . |
| User | This role has limited access to Cloudability. This role is granted to users who log in to Cloudability with the Cloudability user Access Administration role. |

Identity and access control

In Cloudability , Identity and Access management (IAM) and Enterprise Access Control (EAC) are used to provide identity and access control over the roles users have permission to access.

IAM and EAC support permissions that control Cloudability features, persona-aligned custom role creation, and identity provider (IdP) role mapping to Cloudability standard and custom roles.

Personas and use cases

IAM and EAC permissions are based on roles, allowing users to access features based on their role, or persona. The following table shows examples of use cases and corresponding personas.

| Persona | Use Case | Cloudability Use |
| --- | --- | --- |
| Power User | Cloud Center of Excellence (CCoE) Focus: deep understanding of cloud cost management, platform administration, colleague enablement | Daily |
| Program Manager or Product Owner | Focus: cloud costs in the context of project or product they own | Ad hoc; weekly; depending on need |
| DevOps User | Cloud operations Focus: usage optimization and automation | Ad hoc; weekly |
| Finance User | Analysis and cadence reporting at organization level Focus: planning, budgeting, and forecasting | Weekly; monthly; quarterly |
| Executive | Senior management Focus: financial overview and direction | Ad hoc; quarterly |

Using identity and access control

You must be a Access Administration administrator to access identity and access controls.

You can use the Access Administration Access Administration portal to access the functions for granting user roles and permissions in Cloudability.

Managing user permissions and roles

Supported permissions

When a user logs into Cloudability , permissions assigned via the Access Administration Access Administration portal controls access to the features the user can access, based on their assigned permissions.

Supported permissions in Cloudability are shown in the following table:

| Permission Name | Description | Application Types |
| --- | --- | --- |
| AccountGroupManagementFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Account Groups" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AccountGroupManagementFeatureViewOnlyAccess | enable users assigned to a role with this permission to view but not edit accounts and account groups under the Cloudability "Account Groups" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvancedContainersFullAccess | Admin Permission For Cloudability Advanced Containers powered by Kubecost. | Advanced Containers (powered by Kubecost), Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvancedContainersViewOnly | View Only Permission For Cloudability Advanced Containers powered by Kubecost. | Advanced Containers (powered by Kubecost), Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvisorFullAccess | Users with this permission can view all Turbonomic charts and data, and run plans. However, users cannot use Place to reserve workloads, create policies, or execute any recommended actions. | Cloudability Premium, Turbonomic |
| AnomalyDetectionAlertSharingFeatureAddOn | Adds the ability to share anomaly subscription alerts with other users within their organization. | Cloudability |
| AnomalyDetectionFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Anomaly Detection" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AutomationFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Automation" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AutomatorFullAccess | Users with this permission can use all Turbonomic features (including Plan, Park, and Place), but cannot configure the Turbonomic installation or create policies. | Cloudability Premium, Turbonomic |
| AWSResourceInventoryFullAccess | This permission should be explicitly given to a user if s/he needs to access the AWS Resource Inventory feature in CLDY. There is also a feature flag in the backend to enable AWS Resource Inventory feature for a specific customer org. But for a user to view this module, this user permission must be granted. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BudgetsAndForecastFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Current Month", "Forecast", and "Budgets" feature menu items. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BudgetsFeatureViewOnlyAccess | enable users assigned to a role with this permission to view but not edit all budgets and their values under the Cloudability "Budgets" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BusinessMappingsFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Business Mappings" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BusinessMappingsFeatureViewOnlyAccess | enable users assigned to a role with this permission to view but not edit the business mappings and their definitions under the Cloudability "Business Mappings" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityContainerProvisioning | Permission to provision and deploy Containers metrics-agent. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityContainerUploading | Permission to upload Containers data to Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningCanAccess | This user can access Cloudability Planning functionality. | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningFullAccess | Global Full Access Permission. | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningManage | Create/Duplicate/Delete/Rename Plans/ChangeBaseline/Dimensons(CRUD). | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudwiryAdminFullAccess | Enable users assigned to a role with this permission to access all admin-level functionality of the Cloudwiry application. | Cloudwiry |
| CloudwiryUserFullAccess | Enable users assigned to a role with this permission to access all user-level functionality of the Cloudwiry application. | Cloudwiry |
| CommitmentPreferencesFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Commitment Preferences" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CommitmentPreferencesFeatureViewOnly | enable users assigned to a role with this permission to access functionality to view information surfaced under the Cloudability "Commitment Preferences" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ContainersFeatureFullAccess | everything from the permission "ContainersFeatureViewOnly" plus the ability to create, update a Cldy Containers Agent. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ContainersFeatureViewOnly | enable users assigned to a role with this permission to access functionality to view information surfaced under the Cloudability "Containers" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicFeatureAccess | Enable users assigned to a role with this permission to access all functionalities (view, create, update) of allocations and rules under the Cloudability `Cost Sharing` feature menu item, except for telemetry features. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicFeatureViewOnlyAccess | Enable users assigned to a role with this permission to view all allocations, rules, and their definitions under the Cloudability `Cost Sharing` feature menu item, but without the ability to edit or delete them. They also cannot view the telemetry feature. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicMaintainFeatureAccess | Allows full access to all endpoints of the Modeling Service, except for the telemetry feature. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingFeatureFullAccess | Enable users assigned to a role with this permission to access all functionalities (view, create, update) of allocations, rules, and telemetry data uploads under the Cloudability `Cost Sharing` feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingFeatureViewOnlyAccess | enable users assigned to a role with this permission to view but not edit the cost sharing and their definitions under the Cloudability "Business Mappings > Cost Sharing" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingMaintainFeatureFullAccess | Allows full access to all endpoints of the Modeling Service. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| DataTrackingFeatureBasicAccess | Enable users assigned to a role with this permission to access DataTracking feature in Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| DeployerFullAccess | Users with this permission can view all Turbonomic charts and data, use Place to reserve workloads, and create placement policies and templates. However, users cannot run plans or execute any recommended actions. | Cloudability Premium, Turbonomic |
| GovernanceFeatureConfigurationFullAccess | Access all configuration functionality (view, create, update) other than policies under the Cloudability "Governance" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeaturePolicyFullAccess | Access all policy configuration functionality (view, create, update) under the Cloudability "Governance" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeaturePRApprovalAccess | Allow users to approve Pull Requests that are blocked in Cloudability Governance for not complying with Governance policies. This permission is included in "Cloudability Governance PR Approver" role. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeatureViewOnly | Access functionality to view information under the Cloudability "Governance" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| InvoiceGeneration | Ingest data, access and create invoices. | Commercial Billing (MSP) |
| MspBillingCloudSpendApiRead | Read access to Cloudability MSP/CCB cloud spend API. | Commercial Billing (MSP) |
| MspBillingCustomLineItemsRead | Read access to Cloudability MSP/CCB Custom Line Items. | Commercial Billing (MSP) |
| MspBillingCustomLineItemsWrite | Write access to Cloudability MSP/CCB Custom Line Items. | Commercial Billing (MSP) |
| MspBillingExternalApiPricingRead | Read access to Cloudability MSP/CCB external Pricing API. | Commercial Billing (MSP) |
| MspBillingExternalApiPricingWrite | Write access to Cloudability MSP/CCB external Pricing API. | Commercial Billing (MSP) |
| MspBillingPricingRead | Read access to Cloudability MSP/CCB Price Books. | Commercial Billing (MSP) |
| MspBillingPricingWrite | Write access to Cloudability MSP/CCB Price Books. | Commercial Billing (MSP) |
| MspBillingSettingsRead | Read access to Cloudability MSP/CCB settings. | Commercial Billing (MSP) |
| MspBillingSettingsWrite | Write access to Cloudability MSP/CCB settings. | Commercial Billing (MSP) |
| ObserverFullAccess | Users with this permission can view the environment, including the Home Page and Dashboards. | Cloudability Premium, Turbonomic |
| OperationalObserverFullAccess | Users with this permission can view the environment, including the Home Page, Dashboards, Groups, and Policies. | Cloudability Premium, Turbonomic |
| OrgCurrencyFeatureAccess | enable users assigned to a role with this permission to access currency screen and change the default base currency of an org. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RateOptimizationFeatureFullAccess | Enable users assigned to a role with this permission to access all functionality under the Cloudability Savings Automation "Rate Optimization" feature menu item. | Cloudability Savings Automation, Cloudwiry |
| RateOptimizationFeatureViewOnly | Enable users assigned to a role with this permission to view information surfaced under the Cloudability Savings Automation "Rate Optimization" feature menu item. | Cloudability Savings Automation, Cloudwiry. |
| ReadBillingExternalApi | Can read Billing External API. | Commercial Billing (MSP) |
| ReadOrgStructure | Read access to Org Structure Service | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard, Org Structure Service. |
| ReservationPortfolioFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Reservation Portfolio" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ReservedInstancePlannerFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Reserved Instance Planner" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureCanSnooze | enable users assigned to a role with this permission to perform actions (create, update, delete) related to snoozing recommendations under the Cloudability "Rightsizing" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Rightsizing" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureViewOnly | enable users assigned to a role with this permission to access functionality to view information surfaced under the Cloudability "Rightsizing" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPoliciesFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Rightsizing Policies" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPoliciesFeatureViewOnly | enable users assigned to a role with this permission to access functionality to view information surfaced under the Cloudability "Rightsizing Policies" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPreferencesFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Rightsizing Preferences" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPreferencesFeatureViewOnly | enable users assigned to a role with this permission to access functionality to view information surfaced under the Cloudability "Rightsizing Preferences" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingRoiFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Rightsizing ROI" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| SavingsPlansFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Savings Plans" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ScopedAdvisorFullAccess | Users with this permission can view all Turbonomic charts and data, and run plans. However, users cannot use Place to reserve workloads, create policies, or execute any recommended actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management View. | Cloudability Premium, Turbonomic |
| ScopedAutomatorFullAccess | Users with this permission can use all Turbonomic features (including Plan, Park, and Place), but cannot configure the Turbonomic installation or create policies. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management View. | Cloudability Premium, Turbonomic |
| ScopedDeployerFullAccess | Users with this permission can view all Turbonomic charts and data, use Place to reserve workloads, and create placement policies and templates. However, users cannot run plans or execute any recommended actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management View. | Cloudability Premium, Turbonomic |
| ScopedObserverFullAccess | Users with this permission can view the environment, including the Home Page and Dashboards. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management View. | Cloudability Premium, Turbonomic |
| ScopedOperationalObserverFullAccess | Users with this permission can view the environment, including the Home Page, Dashboards, Groups, and Policies. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management View. | Cloudability Premium, Turbonomic |
| ScopedSharedAdvisorFullAccess | Users with this permission can view the Home Page and Dashboards, but only see VMs and Applications. Users cannot execute Turbonomic actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management View. | Cloudability Premium, Turbonomic |
| ScopedSharedObserverFullAccess | Users with this permission can view the Home Page and custom Dashboards, but only see VMs and Applications. Users cannot see Executive Dashboards or execute Turbonomic actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management View. | Cloudability Premium, Turbonomic |
| ScorecardsFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Scorecards" feature menu item | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| SiteAdminFullAccess | Users with this permission can use all Turbonomic features and modify site-specific settings to configure the Turbonomic installation. Users can also administer Groups, Policies, Workflows, Templates, Billing/Costs, and Target Configuration, but not Email, Licenses, Updates, and Maintenance. Users with this role can set the scope on other accounts. | Cloudability Premium, Turbonomic |
| TagExplorerFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Tag Explorer" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TagsAndLabelsFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Tags" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TagsAndLabelsFeatureViewOnlyAccess | enable users assigned to a role with this permission to view but not edit all Cloudability dimensions and their mapped tag keys and k8 labels under the Cloudability "Tags" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TurbonomicFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Turbonomic" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium |
| UserManagementFeatureFullAccess | enable users assigned to a role with this permission to access all functionality under the Cloudability "Users" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| VendorCredentialsFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Vendor Crendentials" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Savings Automation, Cloudability Standard, Cloudwiry |
| ViewBillMx | View data. | Commercial Billing (MSP) |
| ViewsFeatureCreateOwnViewsAccess | Enable users assigned to a role with this permission to view all Views and their definitions under the Cloudability "Views" feature menu item, but can edit or delete only those Views that are authored by this user. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ViewsFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Views" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlacementFeatureFullAccess | enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Workload Placement" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningFeatureCanAccess | Enable users assigned to a role with this permission to access all functionality (view, create, update) under the Cloudability "Workload Planning" feature menu item. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningFeatureFullAccess | Enable users assigned to an admin role with this permission to access all functionalities (view, create, update) under the Cloudability "Workload Planning" feature menu item. They also have the possibility to view/update any workloads created by other users. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningPreferencesViewOnly | Enable users assigned to an admin role with this permission to set up preferences and restrictions for their org for workload planning. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WriteOrgStructure | Write access to Org Structure Service. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard, Org Structure Service |

---

## First steps for Cloudability admin

<!-- sub-header -->
- **breadcrumb:** Getting started > First steps for Cloudability admin
- **source_path:** SSVCLNQ/getting-started/first-steps-admin-cldy.html
- **original_file:** started-first-steps-cloudability-admin.md
- **images:** []

### Overview

IBM Cloudability optimizes cloud resources and translates bills and tags into insights to provide real-time clarity and accountability for consumption. As a first time admin user, here are the steps to configure your Cloudability that will set you up for success.

### Configuration Steps

1. Set up your user account(s) Ask your Frontdoor administrator to create the relevant Cloudability role for you. Learn about Manage Users
1. Roles and Permissions Roles give users permission to access specific views and functions within Cloudability. Setup roles and permissions Learn about Roles and permissions in Cloudability
1. Vendor Credentials Connect to various data sources available. This allows admins to view, add, update, or delete individual accounts under data sources. Admins can search and filter the accounts, and also view the permission level on every individual account. Learn about Vendor Credentials
1. Tag Mappings You can use Tag Mapping to assign tags to Cloudability dimensions for use in our reporting features. Learn about Tag Mappings
1. Account Groups Accounts and Account Groups enable you to edit and group accounts that are accessed with Cloudability. Learn about Account Groups
1. Create and manage views Know more about app-wide filters for your data in Cloudability and assign them to different users Learn about Setup views
1. Currency Exchange Setup a common currency across all of Cloudability, regardless of the cloud service provider or currency used for billing. Learn about Multi Currency Exchange Rate Service
1. Business Mappings Business Mappings are used to create Business Dimensions that categorize cloud spending according to your organization’s taxonomy. Learn about Business Tags

### Useful links for getting started

How to access Cloudability

What you can do with Cloudability

Find your way around with Cloudability

First steps for users in Cloudability

---
