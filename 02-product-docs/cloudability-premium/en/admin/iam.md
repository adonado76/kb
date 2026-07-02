---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Roles and permissions in Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
source_path: "admin/iam.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Roles and permissions in Cloudability

Roles give users permission to access specific views and functions within Cloudability.

By default, all user roles have access to some basic features in Cloudability including cost analytics for reporting, dashboards and
TrueCost Explorer. Additional features can be accessed by assigning permissions to the role.

**Roles in Cloudability**

The following roles can be assigned to users of Cloudability
:

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

**Roles in Access Administration affecting
Cloudability**

The following Access Administration roles are mapped to corresponding
roles in Cloudability :

| Role name | Role permissions |
| --- | --- |
| Admin  : | This role can add, edit, or delete users in Access Administration . This role functions across all Apptio applications, including Cloudability. |
| Administrator | This role has full access to Cloudability.  This role is granted to users who log in to Cloudability with either the  Admin  or  Cloudability Admin  role on Access Administration . |
| User | This role has limited access to Cloudability.  This role is granted to users who log in to Cloudability with the Cloudability user Access Administration role. |

**Identity and access control**

In Cloudability , Identity and Access management (IAM) and
Enterprise Access Control (EAC) are used to provide identity and access control over the roles users
have permission to access.

IAM and EAC support permissions that control Cloudability
features, persona-aligned custom role creation, and identity provider (IdP) role mapping to Cloudability standard and custom roles.

Note: Specific roles assigned to a user in Access Administration will
overwrite roles from IdP role mapping.

**Personas and use cases**

IAM and EAC permissions are based on roles, allowing users to access features based on their
role, or persona. The following table shows examples of use cases and corresponding personas.

| Persona | Use Case | Cloudability Use |
| --- | --- | --- |
| Power User | Cloud Center of Excellence (CCoE)  Focus: deep understanding of cloud cost management, platform administration, colleague enablement | Daily |
| Program Manager or Product Owner | Focus: cloud costs in the context of project or product they own | Ad hoc; weekly; depending on need |
| DevOps User | Cloud operations  Focus: usage optimization and automation | Ad hoc; weekly |
| Finance User | Analysis and cadence reporting at organization level  Focus: planning, budgeting, and forecasting | Weekly; monthly; quarterly |
| Executive | Senior management  Focus: financial overview and direction | Ad hoc; quarterly |

You cannot delete a role unless all users assigned to the role have been
deleted.

**Using identity and access control**

Note:

You must be a Access Administration administrator to access identity and
access controls.

You can use the Access Administration Access Administration portal to
access the functions for granting user roles and permissions in Cloudability.

[Managing user permissions and roles](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Opens in a new tab or window)")

**Supported permissions**

When a user logs into Cloudability , permissions assigned via the Access
Administration Access Administration portal controls access to the features the user can
access, based on their assigned permissions.

Supported permissions in Cloudability are shown in the
following table:

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
