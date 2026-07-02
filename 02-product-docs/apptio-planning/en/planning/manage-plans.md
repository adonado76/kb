---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Manage plans"
breadcrumb: []
source_path: "planning/manage-plans.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Manage plans

With the Plans page, you can manage your plans easily and intuitively.

- To open Plans, open the left-hand navigation pane and select Planning > Plans.

  ![](../../resources/images/it%20planning_images/plans2_430x128.png)

## Choose which plans to view

Use the tabs at the top of the screen to display All Plans, Active Plans or Archived Plans.

## Select which columns to display

You can do this in the Show/Hide Columns pane.

- Select ![](../../resources/images/it%20planning_images/options1_23x20.png) > Open
  Show/Hide Columns.
- Select or clear the checkboxes to add or remove columns.

## Create a new plan

1. Select ![](../../resources/images/it%20planning_images/new-plan-icon_19x20.png).

   The
   New Plan dialog opens.
2. Enter the plan details.

   [Learn more about creating plans](create-budget-plan.dita "(Opens in a new tab or window)")
3. Select Create Plan.

   The new plan is displayed in the Budget or Forecast page.
4. Return to Plans and confirm that the new plan is now listed as an Active Plan.

   If Integrated
   Investment Planning is Enabled, the projects will be copied into the new plan with one of the
   following methods. To learn more about Integrated Investment Planning, please see [Get started with the
   Integrated Investment Planning](iip/gs-integrated-investment-planning.dita "(Opens in a new tab or window)").

   - Create Plan without Baseline Plan – If you are creating a plan without a baseline plan,
     projects from reference data dimension “Project” will be added in the plan.
   - Create Plan with Baseline Plan – If you are creating a plan with a baseline plan,
     projects from the baseline plan will be added to the new plan.

## View a plan's details in the Properties pane

The Properties pane displays the following information about a Plan:

- Type
- State
- Status (displayed in the All Plans tab only)
- Created date
- Plan Length
- Plan Start Year

To view a plan in the Properties pane, select ![](../../resources/images/it%20planning_images/icon-plan-properties_21x20.png).

## Filter plans

To filter the values displayed in a plan column:

1. Hover over the column header and select ![](../../resources/images/it%20planning_images/burger-button_13x9.png).
2. Select ![](../../resources/images/icons/icon-filteron_18x20.png) to filter column
   values.

   Remember: You can also use this pane to:
   - Show and hide columns, by selecting ![](../../resources/images/icons/icon-showhide_19x20.png)
   - Freeze and unfreeze columns, by selecting ![](../../resources/images/icons/icon-column-freeze_21x20.png)

   Planning opens the list of filters for you to choose from. By default, (Select All)
   is selected.

   ![](../../resources/images/it%20planning_images/plan-filter.png)
3. Filter the values to display in the column by doing one of the following:
   - Clear (Select All) and select the check boxes next to the required values.
   - Enter a search term to use to filter values. All values matching all or part of your search term
     are displayed in a list. To apply the filter to the plan, select enter.

   You can filter any column apart from columns with unique values per plan. Columns which have
   filters applied appear with a filter icon in the header.

   ![](../../resources/images/it%20planning_images/current-filters.png)

## Clear filters

To clear filters, select ![](../../resources/images/it%20planning_images/clear-filters_20x20.png) above the plan.

## Sort plans by column

- To sort plans by a column, hover over the column header and select ![](../../resources/images/it%20planning_images/itfmf-ct_images/sort-icon_21x20.png).

## Archive active plans

This moves the plan from your Active list to your Archived list. You can restore an archived plan
back to Active status at any time.

You can only archive plans in the Active Plans tab.

- To archive a single plan, right-click the plan you want to archive and select Archive.
- To archive multiple plans, select the plans using the bulk edit checkbox, right-click any of the
  plans you have selected and select Archive.

## Restore archived plans

You can only restore plans in the Archived Plans tab.

- To restore a single plan, right-click the plan you want to restore and select Restore.
- To restore multiple plans, select the plans using the bulk edit checkbox, right-click any of the
  plans you have selected and select Restore.

## Delete plans

You can delete plans from any tab.

Note: Deleting a plan permanently removes it from the system.

- To delete a single plan, right-click the plan you want to delete and select Delete.
- To delete multiple plans, select the plans using the bulk edit checkbox, right-click any of the
  plans you have selected and select Delete.

## Soft Delete Plan

From the ApptioOne Planning Release 3.50, the plan delete process now happens in two steps:

- Soft Delete - The plan is removed from the UI as soon as an admin clicks the Delete
  button on the Plans page. The deleted plan will no longer be accessible to users.
- Hard Delete - Plan data is deleted automatically, two days after the soft delete.

Admins no longer need to wait for the long running plan delete process; soft delete a plan
quickly then proceed with other tasks. In case you accidentally delete any plan, there is a two-day
window to restore the plan data by logging a support ticket with Apptio.

There is no change for the end user in the plan delete process. The steps to delete plan as
described here still hold good. Only noticeable difference to the end user is that the plan gets
removed very quickly from the Planning application UI, irrespective of the size of the plan.

If multiple plans are selected for delete, the plan data delete requests are added in a queue and
processed sequentially during the data cleanup process.
