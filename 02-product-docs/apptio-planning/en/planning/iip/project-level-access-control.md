---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Project Level Access Control"
breadcrumb: []
source_path: "planning/iip/project-level-access-control.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Project Level Access Control

Applies to: Only customers using Integrated Investment Planning feature.

Investment expense planning process for every IT organization is not the same. Organizations
follow different approaches as per their need and what suits best for their organization culture,
financial practices as well as cost accountability and ownership hierarchy. Below is the list of
major investment planning processes and corresponding implementation data model using Integrated
Investment Planning.

## Use Cases

## Use Case 1: Project Manager managing Project costs under a dedicated Department

This implementation approach is suitable only if there are dedicated project level cost centers
and departments and if all the project expenses are allocated to this single cost center.

Goal

As a project budget owner, I am responsible for planning and managing all expenses pertaining to
projects I own.

Organization Structure

- Projects have dedicated cost centers and those cost centers rollup their costs to owning
  Department.
- Project budge owners and department budget owners are separate personas owning new investment
  and operational budget expenses respectively.

Access and Budget Approval Requirements

- Project owners should have access(view/edit) to only their area of ownership to enter the
  spend.
- Project owners should be able to easily navigate to the cost centers of their ownership to enter
  the spend.
- Project budget owners should be able to submit their budget to next level owner for the budget
  approval.

Implementation Approach

Department to which projects costs rollup are used only for planning project expenses. These
could be dummy departments representing Project Group/Project Portfolio used dedicatedly to enter
project expenses only.

Users identified as project owners are assigned Cost Center Owner role in the Apptio Frontdoor
access administration or an equivalent custom role.

Project owners are assigned permissions (view/edit) to respective departments either group level
departments or leaf level departments as per their scope of cost ownership, using the Cost Object
Permission feature in the planning configuration.

Result

Project budget owners can easily navigate to their assigned department and enter all the
expenses.

It is possible to configure restricted access permissions to project budget owners as per the
need.

All project costs rollup to higher level Department as per the configured hierarchy.

Project budget owners can submit their expenses to next level owner for the budget approval using
existing planning budget approval workflow feature.

Limitations

Projects in most cases have shared costs or future Run costs, that are owned by cost
center/department which could be present at another department hierarchy level. These cost centers
may not be used only for specific projects.

With this implementation approach it is not possible to allocated shared or future run cost
expenses to a department/cost center at different level in the organization structure. Doing so will
require to provide edit access to project budget owners on these departments. But that will also
expose them to other sensitive financials in those departments which may not be intended.

Please find below a data model diagram depicting this implementation approach.

![](../../../resources/images/it%20planning_images/uc-1.png)

## Use Case 2 : Cost Center Owners managing both the Project and Operational expenses for the assigned Departments

This implementation approach is suitable only if there is single budget owner for both project
and operational expenses.

Goal

As a Cost Center Owner, I want to plan and manage operational expenses as well as new
investment/project expenses for my Cost Center’s cost ownership.

Organization Structure

- No separate project budge owners and department budget owners personas, but a single Cost Center
  Owner persona, planning and managing all expenses for allocated cost center.
- Projects can assign cost to any available cost center in the entire organization structure.
- The Cost Center owner is planning and owning costs for multiple projects as well as any
  non-project costs.

Access and Budget Approval Requirements

- Cost Center Owners should have access(view/edit) to only their Cost Center/Department ownership
  to enter the spend.
- Cost Center Owners should be able to easily navigate to the Departments of their ownership to
  enter the spend.
- Cost Center budget owners should be able to submit their budget to next level owner for the
  budget approval.

Implementation Approach

Department have Cost Centers and Projects also have Cost Centers.

If projects want flexibility to assign cost toward any department, use “Allow Any Cost Center =
True” in the project dimension/project list configuration.

Users identified as cost center owners are assigned Cost Center Owner role in the Apptio
Frontdoor access administration or an equivalent custom role.

Cost Center Owners are assigned permissions (view/edit) to respective departments either group
level departments or leaf level departments as per their scope of cost ownership, using the Cost
Object Permission feature in the planning configuration.

Result

Cost Center budget owners can easily navigate to their assigned department and enter all the
expenses including project and operational.

It is possible to configure restricted access permissions to cost center budget owners as per the
need.

All costs rollup to higher level Department as per the configured hierarchy.

Cost center budget owners can submit their expenses to next level owner for the budget approval
using existing planning budget approval workflow feature.

Limitations

With this implementation approach it is not possible to have separate project budget owner
persona with restricted access to view only project expense lines in the assigned department. The
assigned user gets full access to view/edit all expenses in the assigned department.

Please find below a data model diagram depicting this implementation approach.

![](../../../resources/images/it%20planning_images/uc-2.png)

## Use Case 3: Department Owner managing operational expense and owning shared project expenses allocated by Project Managers. Project Expenses are entered by Project Managers with Limited Access​ to Departments.

Goal

As a Department Budget Owner, I want to plan and manage operational expenses for my department. I
also own the shared project costs allocated to my department by the Project Managers.

As a Project Manager, I need to enter my assigned project expenses to various departments.

Organization Structure

- Departments have cost centers and projects also have cost centers.
- Projects can allocate costs to any available cost center.
- Project budget owner persona enters project costs.
- Department Budget Owner persona enters operational costs and is also responsible for approving
  and submitting the shared projects costs assigned in his department.

Access and Budget Approval Requirements

- Department Owners should have access(view/edit) to all expenses including operational and
  project expense allocated in their departments.
- Project budget owners should have restricted access in the Departments to view/edit only project
  expense lines for their assigned projects.
- Both department and project budget owners should be able to easily navigate and view their
  assigned projects and departments.
- Department budget owners should be able to submit their budget to next level owner for the
  budget approval.

Implementation Approach

Department have Cost Centers and Projects also have Cost Centers.

If projects want flexibility to assign cost toward any department, use “Allow Any Cost Center =
True” in the project dimension/project list configuration.

Users identified as cost center owners are assigned Cost Center Owner role in the Apptio
Frontdoor access administration or an equivalent custom role.

Department Owners are assigned permissions (view/edit) to respective departments either group
level departments or leaf level departments as per their scope of cost ownership, using the Cost
Object Permission feature in the planning configuration.

Users identified as Project and Project Group managers are assigned “IIP Project Manager” and
“IIP Portfolio Manager” role respectively in the Apptio Frontdoor access administration or an
equivalent custom role.

Project managers are given view/edit permissions in the Projects > Permission page. They also
have view/edit access to Departments to which projects roll up their expenses, using the Cost Object
Permissions. But their access to departments is restricted to view/edit only expenses for the
projects, that the Project Manager owns.

Result

Department budget owners can easily navigate to their assigned department and view/enter all the
expenses including project and operational.

Project budget owners can easily view and expenses for their projects using the Project hierarchy
filter.

It is possible to configure restricted access permissions to project budget owners.

All costs rollup to higher level Department as per the configured hierarchy.

Department budget owners can submit their expenses to next level owner for the budget approval
using existing planning budget approval workflow feature.

Please find below a data model diagram depicting this implementation approach.

![](../../../resources/images/it%20planning_images/uc-3.png)

The Use Case 3 mentioned above is supported by the Project Level Access Control feature. This
feature is released as Beta. The beta feature is available to all the customers. It doesn’t need a
separate support ticket or enablement on the customer environment. You can follow the steps below to
configure and use it.

## Access Permissions

To support project level access, Apptio has introduced new Frontdoor permissions as described
below. To learn more about permissions and role please visit Frontdoor permissions and roles.

- IIPProjectExpenseEdit – Users with this permission can view and edit budget and forecast
  expenses only for assigned Projects in the Planning component. Users can also view and edit projects
  in the Project List.
- IIPProjectPermissionManage – Users with this permission can view/edit permissions in the
  Projects > Permission page.
- IIPProjectManage - Users with this permission can create and delete projects using create
  Project feature in the Projects > List page.

## Apptio Standard Roles

Using the permissions defined in the IIP Permissions section, Apptio has created two new standard
Frontdoor roles. Customers can use these roles as it is for their Project and Portfolio managers or
create custom roles as per their requirements using the project specific permissions above.

- IIP Portfolio Manager: This role should be assigned to the Group project owners, who need
  limited access in the Department to view and edit expenses and Project List for the entire project
  portfolio as well as need access to Projects > Permission page to assign other users
  as Project Managers for the projects the Portfolio Manager owns.
- IIP Project Manager: This role should be assigned to Project Managers, who need limited
  access in the Departments to only view and edit expenses for the assigned projects. These users can
  edit attributes for the assigned projects using the Project List page. These users don’t have access
  to Projects > Permission page and can’t assign permission to other project managers.

Note: Apptio standard Admin and Budget Process Owner roles in Frontdoor by default have all three
(IIPProjectExpenseEdit, IIPProjectPermissionManage, IIPProjectManage) permissions.

## Project Permission Configuration

1. Admin or Budget Process Owner must assign the Apptio standard role IIP Portfolio Manager or IIP
   Project Manager or equivalent custom role to identify Project Managers and Project Group managers.
   For additional information on roles, see Frontdoor permissions and roles.
2. Admin or Budget Process Owner must assign permissions to Project Group budget owners on the
   respective Project Groups, by following the below steps:

   Configure using Permission page UI
   :   1. From Left Navigation select Projects.
       2. On Projects page select Permission tab.
       3. Click on the pencil icon for the project or project group row.
       4. You will be presented with permission assignment dialog.
       5. Search the username to assign permissions.
       6. Select permission View Only or Edit. Click Save.

   Configure using File Import
   :   1. From options menu (…) on the Permission page export the Project permission template as .csv
          file.
       2. Update the exported .csv file with permission details.
       3. Import the permission as file.

   Project Permission Page

   ![](../../../resources/images/it%20planning_images/project-permission.png)

   Project
   Permission configuration

   ![](../../../resources/images/it%20planning_images/project-permission-config.png)

   Note:
   - If the user is assigned Edit permission at group project level, irrespective of
     permission assigned under the child hierarchy user will have Edit access on entire child
     hierarchy.
   - If the user is assigned View Only permission at group project level but also has
     Edit permission at one of the leaf projects, user will get Edit access on the assigned
     leaf project and for all other projects, the user will have View Only access.
3. Admin or Budget Process Owner, need to assign permissions to Project and Project Group budget
   owners on the respective Departments in the Configuration > Cost Object Permission. To learn more
   about how to assign permissions to Departments using Cost Object Permission page please visit [Manage Cost Pbject](../manage-cost-object.htm "(Opens in a new tab or window)")

   It is
   necessary to assign Project/Portfolio managers permissions on the Projects > Permission page as well
   as Cost Object Permission page because

   - Projects are linked to cost centers.
   - Project linked cost centers are used when allocating expenses to projects.
   - The cost centers are also linked to Departments, so the project expenses ultimately rollup to
     owning department.
   - Since Department is the cost object having its own permission configuration, it is necessary to
     provide project managers view or edit access to these departments.

However, even though Project managers have Edit access at the department level, they will get
limited edit access in the department. When project managers navigate to department having edit
access, only the expense lines that have Project column value same as the assigned project for
project manager will be displayed.

## Managing Project Level Expenses as a Project Manager

- User with project level permissions configured will be able to view/edit only the expense lines
  under any department that are tagged with the project they own. In other words, only those lines
  will be accessible where Project column value = assigned Project Name.
- Any other expense lines, either those that have different project name than assigned permission
  or those that have project name as empty will be filtered out from the project manager’s view.
- Project column on the Expenses view will be mandatory, when adding new expense lines or editing
  existing expense lines, as a user with project level permissions configured. This validation will
  make sure project managers are not able to add any non-project expenses. This validation will be
  applicable whether the lines are added/edited using the UI or the .csv file import.
- In the beta release, project managers can only add/edit/delete expense lines for the assigned
  projects. Submit Budget option is NOT yet enabled for the project managers. Department budget owners
  will review the expenses added by the project managers and they will Submit the budget for the
  approval.

## Project Hierarchy Filter

Project Hierarchy Filter is a dropdown in the Planning header that presents users with a
multi-select dropdown list view of all the projects to which they have access. Users can select one
or more projects from the multi-select dropdown list, that results in filtering the expenses lines
for the selected project. The hierarchy filter comes with the features below:

- Department budget owners will be able to view/edit all the expenses under the assigned
  department. This includes expenses tagged with any project name and expenses that have project field
  empty.
- The Projects dropdown will show only those projects to which user has permissions.
- By default, All Projects checkbox is selected, enabling user access to all the projects
  to which access is granted.
- Selecting Project group will automatically select all the children project groups and children
  projects to which user has permissions.
- Select one or more projects, and then select Update Filters. The Expenses view or the
  Summary/Dashboard charts displays the expenses only for the selected projects.
- Once the view is filtered, user will be able to enter the expenses only against the filtered
  projects either by using the UI or by .csv file import.
- Exporting the expenses with Project Hierarchy Filter applied will result in exporting expenses
  only for the filtered projects.
- Navigating a group or leaf department using the Department dropdown will automatically
  filter the Project dropdown with those projects that roll up their expenses to filtered
  departments.

  ![](../../../resources/images/it%20planning_images/phf-2.png)

  ![](../../../resources/images/it%20planning_images/phf-1.png)

## Frequently Asked Questions

Is this feature available to all the customers?

Yes, this feature is available to all the customers, who have enabled Integrated Investment
Planning in the Company Profile Settings.

When the feature is enabled on my environment, will it impact my existing permission
configurations?

No, there will not be any impact on the existing permission configurations. The project level
permissions will work only when the user roles are updated with newly added project level
permissions IIPProjectExpenseEdit, IIPProjectPermissionManage and IIPProjectManage.

Can I select Project Group from the Projects dropdown in the navigation header?

No, selecting Project Group from the Project dropdown is not supported as yet. It is on our
roadmap to support it.

Is there an option to unselect all the projects from the Project dropdown so I can see only
operational expenses?

No, the user must select at least one project from the Project dropdown.

We are satisfied with our existing project permission configuration, but we want to use only
the Project dropdown feature, since it enables us to easily navigate projects. Is that
possible?

Yes, you can use only the Projects dropdown if you don’t want to change the existing project
permission configuration.

Is it possible to select all the projects to which I have access and plan the expenses for all
those projects without navigating to the corresponding department hierarchy?

Yes, you can achieve this by following the steps below:

1. Assign either IIPProjectManager or IIPPortfolioManager Role or an equivalent custom role that
   has project specific permissions IIPProjectExpenseEdit, IIPProjectPermissionManage and
   IIPProjectManage to the Project/Portfolio managers.
2. Assign Project/Portfolio managers to appropriate project/project group from Projects >
   Permissions page.
3. Assign Project/Portfolio manager Edit access to All Departments in the Cost Object Permission
   page.

With this configuration, the user now gets restricted Edit access at All Department level, that
enables them to navigate to Expenses > All Departments and then enter project level expenses to all
the projects they own.

If I assign users with Apptio’s standard Cost Center Owner role to a project using the
Projects > Permission page, will the user get restricted access in the departments to view/edit only
the project level spend?

No, it is mandatory to update the user role with IIPProjectExpenseEdit permission to get
restricted access in the departments to view/edit only the project expenses.

Why is the Project column mandatory when a user with project level permissions is planning the
expenses?

Any user with project level permissions is considered as a Project/Portfolio manager. In this
role, users will get access to view and edit expenses only for the projects they have access to. The
project level expenses are identified by knowing the value of Project attribute on the expenses
line. Since, the user is shown a filtered view of expenses that are only related to project, the
same restriction should also apply when entering/editing new expenses, so that user is prevented
from entering any expenses that are not project related or to a project that user does not have
access.

In our organization project level expenses are submitted by the project managers, but in this
beta version, submitting the budget is owned by the department owner. Can we get the ability to
submit the budget to the Project/Portfolio managers?

Yes, it is on our roadmap to support this capability. However, we also want to hear from you
about your use cases in this area. Please reach out to your Customer Success Manager and ask for a
meeting with the Product Manager to discuss more on this topic.

Can we set up a separate project level budget approval workflow, independent of the Department
budget?

No, at present this feature is not available. Please reach out to your Customer Success Manager
and ask for a meeting with the Product Manager to discuss more on this topic.
