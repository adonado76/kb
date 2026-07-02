---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "About budget planning and forecasting"
breadcrumb: []
source_path: "it-planning/planning/budget-planning-forecasting.html"
images:
  - "resources/images/it_planning_images/icon_video.jpg"
  - "resources/planning_images/itp_diagram_budget-plan.png"
  - "resources/planning_images/itp_diagram_budget-workflow.png"
  - "resources/planning_images/itp_diagram_forecast-workflow.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# About budget planning and forecasting

After the Admin has configured your Apptio Planning application,
you can begin forecasting and planning your budget. See [Configure and administer the
Apptio Planning applications](configure-administer-apptio.dita "(Opens in a new tab or window)").

![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/icon_video.jpg)

Watch
these videos from Apptio Education Services:

- [IT Planning Workflow 2.0](https://community.ibm.com/community/user/viewdocument/it-planning-20-workflow-2-min "(Opens in a new tab or window)")
- [Understanding Data Hierarchies in ITP](https://community.ibm.com/community/user/viewdocument/understanding-data-hierarchies-in-i "(Opens in a new tab or window)")

## How budget planning and forecasting works in Apptio

Success with Apptio Planning applications requires clear insight into user tasks and process
flows. The following images show examples of tasks (columns) and user roles (rows) for budget
planning tasks in Apptio Planning applications. The images displays examples of a budget planning or
forecasting process with three levels. You can adapt this process to meet your organizational needs.
For example, your organization may have no budget owner, a single budget owner, or several layers of
budget owners. Similarly, your organization may have one or multiple users who approve plans.

In the following examples, there is only one designated Budget Process Owner but probably
multiple budget owners. Owners of a Parent Code in Departments reference data, or of enabled
Projects, Services, or Business Unit reference data are considered group budget owners. See [Manage Financial reference
data](manage-financial-dimensions.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

Here is a budget planning workflow:

![image](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_budget-workflow.png)

Here is a forecast planning workflow:

![image](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_forecast-workflow.png)

- Budget Process Owners are responsible for creating the plan that budget owners will use to input
  data and track their spending. Budget Process Owners are also responsible for finalizing and closing
  plans.
- Budget owners are responsible for inputting budget information for their Cost Objects. This can
  apply to single or group owners of departments, projects, services, or business units.
- Approvers are assigned as designated people who can approve or reject submitted plans. Approvers
  are not tied to credential hierarchy but to the Cost Object hierarchy (see [Manage Cost Object Permissions reference
  data](manage-cost-object.html "Cost Object Permissions determine which users can view, edit, submit, or approve Department-level plans (Cost Objects). Each Department can have one or more users assigned with edit-level permissions and, for Multi-Level Approvals, approval-level permissions.")). Apptio Planning applications support up to five levels of approvers.

## Forecasting

A forecast usually consists of:

- A previous budget plan or forecast to serve as a baseline for the new forecast.
- Monthly actuals that have been uploaded to your Apptio Planning application (see [Import and publish actuals](import-publish-actuals.html)).
  Historical actuals are not editable. If the new forecast includes actuals, but no future planned
  amounts, this represents unplanned spend.

Every forecast you create spans the full plan year (usually your fiscal year). For example, your
plan year is a January-December calendar year. You previously created an annual budget plan and
uploaded year-to-date actuals for January through March. Now, you want to create a forecast. In the
new forecast, the January-March historical actuals are populated and the April-December line-item
values are copied from the Budget Plan baseline:

![image](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_budget-plan.png)

After you have updated and finalized the new forecast, you can use it as the baseline for a
subsequent forecast. If you use the Budget Plan as the baseline for the initial forecast of the
year, then you can use each quarterly forecast as the baseline for the subsequent forecasts. For
example, you can use the Budget Plan as a baseline for the Q1 forecast, then use the Q1 forecast as
the baseline for the Q2 forecast, the Q2 forecast as the baseline for the Q3 forecast, and so on.
The same sequencing logic applies for monthly or other forecasting periods.

## Budget and forecast planning tasks

- [Create a plan or
  forecast](create-budget-plan.html)
- [Manage line-item
  tables](manage-line-item.html)
- [Enter financial details
  and adjust baseline values](enter-financial-details.html)
- [Set financial
  targets](set-financial-targets.html)
- [Plan for multiple
  years](plan-multiple-years.html "Use multiple-year planning features to plan and track your IT financials in a continuous, multi-year time horizon. You can support long-range plans and rolling forecasts across fiscal year boundaries.")
- [Open a plan or a
  forecast](open-plan-forecast.html "After you create a budget plan or forecast, optionally adjust the baseline values, set the targets, and open the plan so that the budget owners can edit line items. Budget owners cannot see a plan when it is in the New state. When you open a plan, an email notification is sent to budget owners and all users who have the Edit & Submit permission associated with the Cost Objects in that plan.")
- [Import and publish
  actuals](import-publish-actuals.html)
- [Analyze a plan or
  forecast](analyze-plan-forecast.html). Use the Costing Standard [Financial Review report](../reports-itfmf-ctv104/itfmf-ct_financialreview107.dita "(Opens in a new tab or window)") to review cumulative spend YTD, projected annual spend, and budget
  variance by cost pool. Use the Costing Standard [Labor
  Review reports](../reports-itfmf-ctv104/itfmf-ct_itplaborreview104.html "◆ Applies to: Planning and Costing Standard on TBM Studio 12.3 and later, with Template v104 and later") to view labor costs by internal and external personnel by Cost Center. See the
  top labor spend by role and internal and external breakout.
- [Compare versions or
  plans](compare-versions-plans.html)
- [Review, approve, or return
  plans or Cost Objects](review-approve-return.html)
- [Archive, restore, or delete
  plans](manage-plans.html "With the Plans page, you can manage your plans easily and intuitively.")
