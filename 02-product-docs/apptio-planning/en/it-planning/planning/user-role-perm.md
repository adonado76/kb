---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "User Roles & Permissions"
breadcrumb:
  - "Planning"
  - "Getting started"
source_path: "it-planning/planning/user-role-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# User Roles & Permissions

User roles and permissions control who can access, edit, and manage data in Apptio Planning.
Roles define the level of access within the application, while permissions provide more
granular control over specific tasks.

## Standard User Roles

Apptio Planning includes five predefined user roles:

1. **Admin**
   1. Full access to all features in Apptio Planning.
   2. Includes administrative permissions across other Apptio applications through
      FrontDoor.
2. **Budget Process Owner**
   1. Full access to all features in Apptio Planning.
   2. Typically responsible for coordinating the budget cycle and managing plan
      lifecycles.
3. **Cost Center Owner**

   1. Can edit expenses for the Departments they are assigned to.
   2. Useful for department-level budget contributors.
4. **IIP Project Manager**
   1. Can edit expenses for Projects they are assigned to in Integrated Investment
      Planning (IIP).
   2. Focused on managing individual project-level financials.
5. **IIP Portfolio Manager**
   1. Can edit expenses for assigned Projects in IIP.
   2. Can also grant user permissions on projects and create new projects.
   3. Typically oversees a portfolio of projects and allocates permissions.

## Custom Roles

In addition to the standard roles, you can create **custom roles** in **FrontDoor**.
Custom roles let you tailor access to meet your organization’s specific needs.

## Permissions

The following table lists available permissions and their descriptions:

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Permission Name** | **Description** | **Admin** | **Budget Process Owner** | **Cost Center Owner** | **IIP Project Manager** | **IIP Portfolio Manager** |
| ApiCanReadData | Allows access to table data via API. Required for Cost Transparency Integration. | x |  |  |  |  |
| CanComment | Enables adding and viewing plan-level comments. | x | x | x | x | x |
| canEditExternalCode | Grants permission to edit external codes. | x |  |  |  |  |
| CompanyProfileConfig | Allows viewing and editing of Company Profile settings. | x |  |  |  |  |
| CTIConfig | Allows viewing and editing of Cost Transparency Integration settings. | x | x |  |  |  |
| DataOrchestrationServiceFeatureFullAccess | Provides full access to all Data Orchestration Service endpoints/actions. Required for Automated Data Management. | x |  |  |  |  |
| EditPlanning | Grants permission to view and edit plans. | x | x | x | x | x |
| EditReferenceData | Allows editing, importing, and publishing of reference data. | x | x |  |  |  |
| EditRestrictedDimensions | Enables editing of dimensions and attributes configured with restricted access. | x | x |  |  |  |
| ExternalLineEdit | Grants permission to edit external line items. | x | x |  |  |  |
| IIPProjectExpenseEdit | Grants permission to view and edit project line items. Also allows editing projects in the Project List. |  |  |  | x |  |
| IIPProjectManage | Grants full project management capabilities: create and delete projects, edit attribute data, and manage expenses across all projects in a plan. | x | x |  |  |  |
| IIPProjectPermissionManage | Allows access to the Project Permissions page. | x | x |  |  | x |
| ITPCompensationAdjustmentAllPeriodsEdit | Allows editing labor compensation adjustments for all plan periods. | x | x |  |  |  |
| ITPCompensationAdjustmentEdit | Allows editing labor compensation adjustments only for defined compensation cycles. | x | x | x |  |  |
| ITPPlanSettingsEdit | Grants permission to edit Plan Settings pages. | x | x |  |  |  |
| ITPPlanSettingsView | Grants permission to view (but not edit) Plan Settings pages. |  |  |  |  |  |
| ManagePlans | Allows creating, archiving, and deleting plans. | x | x |  |  |  |
| ManageUsers | Grants full access to manage user roles and permissions in the Access Administration console. | x |  |  |  |  |
| ViewAssets | Grants visibility to the Assets tab and allows editing asset line item details. | x | x | x | x | x |
| ViewChangeHistoryFeatureViewOnly | Grants visibility to Change History Event Log | x | x |  |  |  |
| ViewContracts | Grants visibility to the Contracts tab and allows editing contract line item details. | x | x | x | x | x |
| ViewLabor | Grants visibility to the Labor tab and allows editing labor line item details. | x | x | x | x | x |
| ViewPlanning | Allows viewing but not editing of plans. | x | x | x | x | x |
| ViewReferenceData | Allows viewing but not editing of reference data. | x | x |  |  |  |
| ViewSpendManagement | Allows viewing but not editing of actuals in Spend Management. | x | x | x | x | x |
| ViewCloud | Allows viewing and editing lines in the Cloud tab | x | x | x | x | x |
| CanImporFromCloudability | Provides access to to import data from Cloudability into the Cloud tab and to delete Cloudability-imported line items. | x | x |  |  |  |
| *ITPPredictiveForecastingFeatureFullAccess* | Provides full access to generate and view predictive forecasting in planning. | x | x | x |  |  |

## Cost Object Permissions

Cost Object Permissions determine which users can view, edit, submit, or approve
Department-level plans. Only users with the **Cost Center Owner** role are eligible to be
assigned department access. Users with **Admin** or **Budget Process Owner** roles
automatically have access to all departments by default. User access is managed at the plan
level through **Plan** → **Settings** → **User Permissions.**

See [Cost Object Permissions](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-cost-object-permissions "(Opens in a new tab or window)") for more information.

## Project Permissions

Project Permissions determine which users can view or edit Project expenses. Only users with
the **IIP Portfolio Manager** or **IIP Project Manager** role are eligible to be
assigned project access. Users with **Admin** or **Budget Process Owner** roles
automatically have access to all departments by default. User access is managed at the plan
level through **Plan** → **Projects** → **Permissions.**

See [Project Permissions](iip/project-level-access-control.html) for more
information. =
