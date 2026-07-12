---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Project List"
breadcrumb: []
source_path: "planning/iip/project-list-document.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Project List

Applies to: Customers using Integrated Investment Planning feature in
Planning.

Investment planning and project funding is a continuous process driven by changes in priorities,
macroeconomic environment, and competition etc. Apptio customers create budget plan in Planning
during their Annual planning cycle. The annual plan needs the flexibility to add newly funded
projects throughout the year. Similarly, if certain projects are not relevant anymore, budget owners
should be able to delete those projects from the current annual plan. The Project List feature will
help fulfill this need.

The following tasks can be performed by users assigned to the following roles:

- Admin
- Budget Process Owner

These users can now add new project or initiative to your investment planning portfolio, delete
projects in existing plan, or edit project attributes. Projects can now be managed as plan level
dimension.

## Project Dimension vs Project List

Project Dimension in Reference Data
:   Reference data dimensions has “Project” as one of the Standard Dimension. Consider this as your
    master Project list that represents the funded list of projects for expense planning and actuals
    tracking. This global dimension will remain as it is after the release of Project List feature.

    - The projects from the global Project dimension will be copied in the Plan when there is no
      baseline plan used in Create Plan operation.
    - The projects from the global Project dimension will be used to validate the actuals uploaded in
      the Spend Management. If you are uploading financial actuals for Project expenses, those projects
      must be present in the global Project dimension.

Project List in a Plan
:   Project List is a local copy of projects limited to a selected plan. Project List can be managed
    at a plan level independent of global Project Dimension.

    Project List in a Plan and the Project dimension in the reference data share the same schema.

## Navigation

If Integrated Investment Planning feature is enabled, then navigate to Planning > Projects.

![](../../../resources/images/it%20planning_images/project-list.png)

The Project List view appears as below.

![](../../../resources/images/it%20planning_images/project-list-view.png)

## Managing Projects

Add Project
:   To add a new project in the plan, navigate to Expenses >
    Project List, and then select ![](../../../resources/planning_images/icon-itp-apex-add-filter_20x20.png). A New Project dialog
    appears as shown

    ![](../../../resources/images/it%20planning_images/add-new-project.png)

    Provide details in the appropriate fields and then click the Add
    button.

    |  |  |
    | --- | --- |
    | Code | Unique project code for each project. Project code should be unique in the selected plan. (Mandatory attribute). |
    | Name | Name of the project. |
    | Project Group | Parent project group for the project. This dropdown list is a look up list from the Project Group reference data. |
    | Allow Any Cost Center | Checking this check box allows any cost center to be selected for the project. |
    | Default Cost Center | Default Cost Center for the project. |
    | Cost Center | List of cost centers available for the project. |

Edit Project Attributes
:   To edit project attributes, select ![](../../../resources/images/it%20planning_images/icon-plan-properties_21x20.png) from the
    project list. The project edit dialog appears.

    ![](../../../resources/images/it%20planning_images/project-list-edit_498x1535.png)

    Make the appropriate changes to the project attributes and save.

Delete Project
:   To delete project, select one or more projects from the project list.

    Right-click the context menu and select Delete button

    ![](../../../resources/images/it%20planning_images/delete-project.png)

    Or

    Select Delete Selected Projects from ![](../../../resources/images/it%20planning_images/options1_23x20.png)on the project list
    page.

    ![](../../../resources/images/it%20planning_images/delete-select-project.png)

    If any of the projects selected for delete have expense lines in the plan, a confirmation dialog
    appears

    ![](../../../resources/images/it%20planning_images/delete-confirm_507x182.png)

    Select Confirm to delete the selected projects.

    Note: Deleting a project will remove the details from the Project List. It will delete any expenses
    lines where Project is a mandatory attribute. E.g., By default, Labor Activity lines require Project
    as a mandatory attribute. So, any Labor Activity lines associated with the project will get deleted.
    However, if there are any expenses where project is not a mandatory attribute, the project value
    will be cleared from these lines, but the expense line won’t be deleted. E.g., With default
    configuration Contract, Asset, Other and Labor lines don’t need project as a mandatory
    attribute.

Import Project List
:   To import project list, navigate to ![](../../../resources/images/it%20planning_images/options1_23x20.png) and select
    Import from File list as a .csv file.

    Note: Import into Project List using a file import will only support updating attributes for
    existing Projects and adding new projects. Deleting projects using file import is not supported
    currently.

Export Project List
:   To export project list, navigate to![](../../../resources/images/it%20planning_images/options1_23x20.png)and select “Export to
    File” option to export project list as a .csv file.

Edit Project Code
:   To edit project code, follow the steps described under Edit Project
    Attributes section. Enter a new project code and save the changes.

## Managing Project List Schema

Project dimension and Project List share the same schema. If you want to add any custom columns
or manage existing custom columns to Project List, follow the schema management steps under
Configuration > Schema > Project.

► Learn about:[Schemas](../manage_schema.htm "(Opens in a new tab or window)")

## Creating Plan with Project data

- Create Plan without Baseline Plan – If you are creating a plan without a
  baseline plan, projects from reference data dimension “Project” will be added in the plan.
- Create Plan with Baseline Plan – If you are creating a plan with a
  baseline plan, projects from the baseline plan will be added to the new plan.

  ► Learn about:[Plans](../manage-plans.htm "(Opens in a new tab or window)")

## Project Actuals in Spend Management

Spend Management has Project Code column. Project Code column is a lookup attribute to the
Project dimension under Reference Data. If you are uploading project actuals in the Spend Management
or importing project actuals in the Spend Management from Cost Transparency, make sure the project
codes used in the Actual expense lines are present in the Project Reference Data dimension. If the
project code used in the actuals is not present in the project reference data, the project code
attribute value will be cleared from the uploaded actual expense line. If you are tracking project
actuals, it is must to add that project in the global Project dimension.

► Learn about: [Spend
Management](../spend-management.htm "(Opens in a new tab or window)")

## Upgrade Project Reference Data in Plan

With the release of Project List feature, projects are now plan scoped reference data. Projects
can be created/deleted/edited in the plan using the project list independent of Project reference
data dimension. If there are changes in the Project dimension in the global reference data, the
Update reference data in a Plan will not show those changes available to plan since plan once
created starts referring to the Project List as a plan level dimension and not the global Project
reference data dimension.

► Learn about: [Update
reference data](../update-data-open-plan.htm "(Opens in a new tab or window)")

To update the projects in the Projects > List follow the steps below.

1. Open the Options menu from the Projects > List.
2. Click Update Project Data option.

   ![](../../../resources/images/it%20planning_images/3.54-2.png)
3. User is presented with a confirmation dialog.

   ![](../../../resources/images/it%20planning_images/3.54-3.png)
4. To continue applying updates click Update.
5. User is presented with a dialog showing number of projects added, deleted, number of lines
   updated and deleted. Review the impact by going through these numbers.

   ![](../../../resources/images/it%20planning_images/3.54-5.png)
6. Click Update to apply updates.

## How are the Project changes applied?

1. If a project is deleted in the Reference Data > Project but it is present in the plan after
   applying the project data changes, following change will take place.
   - Any labor activity lines for the project will be deleted along with Labor Activity Financials.
     This will show as Lines items to be deleted on the update project data confirmation
     dialog.
   - Project value on any expense line for Labor, Contract, Asset and Other financials will be nulled
     and those expenses will show under Department. This will show as Line items to be updated on
     the update project data confirmation dialog.
   - Project will get deleted from the plan.
2. If a new project is added in the Reference Data > Project and it is not present in
   the plan, the project will be added in the Project List.
3. If a Project is added directly into the Plan and it does not exist in the Reference Data
   > Project, that project will be deleted from the Project List. The impact on expenses
   as a result of project delete will be same as point 1 above.
4. If a Cost Center is removed from the project in the Reference Data >
   Project, but the removed cost center is present for the project in the plan, following
   changes will take place after applying the project data update.
   - Any labor activity lines for the project will be deleted along with Labor Activity Financials.
     This will show as Lines items to be deleted on the update project data confirmation
     dialog.
   - Project value on any expense line for Labor, Contract, Asset and Other financials will be nulled
     and those expenses will show under Department. This will show as Line items to be updated on
     the update project data confirmation dialog.

     This is because cost center is a required attribute
     on the project. If you are looking to not lose any expenses, please move those expenses to
     appropriate cost center before removing cost center from the project.
5. If there are outstanding changes in the other reference data dimensions that are not yet applied
   on the plan and user attempts to apply project data update on the Project > List, the update is
   blocked and user is presented with a message as shown in the screenshot below.

   ![](../../../resources/images/it%20planning_images/itp-3.54.png)

   This step is necessary to
   avoid any dimension dependency conflicts, such as changes in cost center or project group which are
   essential for the project update.
