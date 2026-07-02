---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "release-notes"
title: "Planning: What's new in 2023"
breadcrumb: []
source_path: "release-notes/whats-new-2023.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planning: What's new in 2023

## 3.60 - December 25, 2023

Starting on Monday 12/25/2023, main production tenants begin to upgrade to release 3.60. Apptio
is launching following features in this minor release.

- Async Plan Creation (Beta) : Plan creation process is now asynchronous.
  Users can begin the plan creation process and continue to use Planning application for performing
  other tasks. Once the plan is created, user will be notified. *In the beta version this feature
  will be available only in the sandbox (non-main) environments.* To know more, see [Async Plan
  Creation.](Async Plan%0ACreation.../../it-planning/planning/create-budget-plan.dita "(Opens in a new tab or window)")
- Automated Data Management : The connection settings are configured
  automatically when ADM integration is enabled from Company Profile. For more information, see [Prerequisites](Prerequisites../../it-planning/planning/adm/adm_prerequisites.dita "(Opens in a new tab or window)").
- Expense Line Delete Confirmation - A confirmation dialog will be shown
  before deleting an expense line item. This feature is available from Expenses
  > New View. To know more, see [Deleting line items](Deleting line items../../it-planning/planning/working-with-apex-line-items.dita#Deletinglineitems "(Opens in a new tab or window)").

## 3.59 - December 11, 2023

Starting on Monday 12/11/2023, main production tenants begin to upgrade to release 3.59. Apptio
is launching following features in this minor release.

## Plan Comparison on Labor

It is now possible to compare the Labor data between two plans using the Expenses New View. To
know more, see [Compare labor headcount](Compare labor headcount../../it-planning/planning/analyze-labor-headcount.dita "(Opens in a new tab or window)")

## FTE Labor Activity Data in Apptio BI

It is now possible to create Apptio BI reports for Labor Activity using FTE is a unit of quantity
in addition to Hours as currently supported unit of quantity. To know more, see [FTE labor activity data](FTE labor activity data../../it-planning/planning/ssr/fte-labor-activity-data.dita "(Opens in a new tab or window)").

## 3.58 - November 27, 2023

Starting on Monday 11/27/2023, main production tenants begin to upgrade to release 3.58. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.57 - November 13, 2023

Starting on Monday 11/13/2023, main production tenants begin to upgrade to release 3.57. In this
minor release Apptio will release support for Automated Import of Actuals from Cost Transparency to
Spend Management via Automated Data Management.

## Automated Import of Actuals

It will now be possible to automatically import Actuals from Cost Transparency to Spend
Management using Automated Data Management. To learn more about ApptioOne Planning and Automated
Data Management Integration, see [ADM Overview.](ADM Overview.../../it-planning/planning/adm/adm_overview.dita "(Opens in a new tab or window)")

To learn more about importing actuals with Automated Data Management please visit [Import
Actuals](Import%0AActuals../../it-planning/planning/adm/adm_import_actuals.dita "(Opens in a new tab or window)").

## 3.56 - October 30, 2023

Starting on Monday 10/30/2023, main production tenants begin to upgrade to release 3.56. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.55 - October 16, 2023

Starting on Monday 10/16/2023, main production tenants begin to upgrade to release 3.55. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.54 - October 3, 2023

Starting on Monday 10/03/2023, main production tenants begin to upgrade to release 3.54. Apptio
is launching following features in this minor release.

## External Unique Identifier for Expense Lines

Expense lines now supports External Unique Code. Users can define a unique code for every expense
line.

When updating existing expenses:

- Line-Item Code takes precedence over the External Code if both are present.
- If missing Line-Item Code, External Code is used to update existing expenses.
- In case Line-Item Code is a match between existing lines and imported lines but External Code is
  different, the operation is treated as an update to the External Code.

To enable the feature, navigate to Company Profile >
Settings and click Enable External Code and Save
Changes.

To know more, see [External Unique Identifier](External Unique Identifier../../it-planning/planning/external-unique-identifier.dita "(Opens in a new tab or window)").

## Integrated Investment Planning Features

## Update Project List Data

In ApptioOne Plan Release 3.54, we have simplified the process of updating the project list using
the projects from Reference Data > Projects. Use Update Project Data option
from the Projects > List actions menu to update the projects in the Project List with Reference Data
> Projects.

![](../../resources/images/it%20planning_images/proj-list-data.png)

To learn more visit [Upgrade Reference Data](Upgrade Reference Data../../it-planning/planning/iip/project-list-document.dita "(Opens in a new tab or window)") in Plan section.

## Select Project Groups in Projects Dropdown

It is now possible to select Project Group(s) from the Projects dropdown.
Selecting a project group will automatically select all the children entities, either project
group(s) or a project(s).

![](../../resources/images/it%20planning_images/pg-projects.png)

Note: In case you have a project hierarchy where Project Group doesn’t have any leaf projects,
such project groups are not shown in the Projects dropdown currently. For example, consider the
project hierarchy below. In this case Project Group 1 isn’t shown in the projects dropdown, but
Project Group2, Project Group3 and Project Group 4 are shown. This is a limitation in the 3.54
release, we are working on improving it to show all project groups.

Projects Group1

- Project Group2
  - Project1
  - Project2
- Project Group3
  - Project3
  - Project4
  - Project Group4
    - Project5

## Labor Activity Summarization

It is now possible to view related attributes of a Resource such as Vendor, Location, External
Code, Role etc. on Expenses > Labor Activity.

To summarize labor activity data by relevant Labor resource attributes such as Vendor, Location,
Role, enable the required attributes from Show/Hide Columns… dialog.

![](../../resources/images/it%20planning_images/3.54-labor.png)

## 3.53 - September 18, 2023

Starting on Monday 09/18/2023, main production tenants begin to upgrade to release 3.53. Apptio
is launching support for Cost Type in Spend Management.

## Cost Type in Spend Management

Customers using Integrated Investment Planning can now see Cost Type as out of the box column in
the Spend Management. This will help identify Actual expenses as build or run. It will now be
possible to pull actuals as build or run into forecast plans. If the value is not provided, the
default value Run will be applied to the uploaded actuals.

![](../../resources/images/it%20planning_images/release-notes/3.53-rn_987x238.png)

## 3.52 - September 4, 2023

Starting on Monday 09/04/2023, main production tenants begin to upgrade to release 3.52. Apptio
is launching support to Save Year-to-Date (YTD) Comparison in Comparison Shortcut.

## Save Year-to-Date (YTD) Comparison in Comparison Shortcut

Plan comparisons created using Comparison Shortcut will also support and save the Year-to-Date
(YTD) comparison for the forecast plans. To know more, see [Compare
versions or plans](Compare%0Aversions or plans../../it-planning/planning/compare-versions-plans.dita "(Opens in a new tab or window)")

## 3.51 - August 21, 2023

Starting on Monday 08/21/2023, main production tenants begin to upgrade to release 3.51. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.
:   Async Plan Creation - Due to recently observed production issue, we have
    temporarily disabled Async Plan creation feature. Plan creation will be executed as a synchronous
    request like earlier until we re-enable the feature. The feature will be enabled back again in
    ApptioOne 3.54 release.

## 3.50 - August 7, 2023

Starting on Monday 08/07/2023, main production tenants begin to upgrade to release 3.50. Apptio
is launching support for Soft Plan Delete in this minor release.

## Soft Delete Plan

The plan delete process now happens in two steps.

- Soft Delete - The plan is removed from the UI as soon as an admin clicks
  the Delete button on the Plans page. The deleted plan will no longer be accessible to users.
- Hard Delete - Plan data is deleted automatically, two days after the soft
  delete.

Admins no longer need to wait for the long running plan delete process; soft delete a plan
quickly then proceed with other tasks. In case you accidentally delete any plan, there is a two-day
window to restore the plan data by logging a support ticket with Apptio.

► Learn about: [Manage Plans](Manage Plans../../it-planning/planning/manage-plans.dita "(Opens in a new tab or window)")

## 3.49 - July 24, 2023

Starting on Monday 07/24/2023, main production tenants begin to upgrade to release 3.49. Apptio
is launching support for Async Plan Creation and Project Level Access Control (Beta) in this minor
release.

## Project Level Access Control (Beta)

- IIP only: Grant permissions to users such as project/product managers at a per project basis.
  (Independent of the department budget).
- IIP only: These users can view expenses for one or more projects using the Project hierarchy
  filter.

► Learn about:[Project Level Access Control](Project Level Access Control../../it-planning/planning/iip/project-level-access-control.dita "(Opens in a new tab or window)")

## Async Plan Creation

Plan creation process is now asynchronous. Users can begin the plan creation process and continue
to use Planning application for performing other tasks. Once the plan is created, user will be
notified.

► Learn about: [Async Plan Creation](Async Plan Creation../../it-planning/planning/create-budget-plan.dita "(Opens in a new tab or window)")

## 3.48 - July 10, 2023

Starting on Monday 07/10/2023, main production tenants begin to upgrade to release 3.48. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.47 - June 26, 2023

Starting on Monday 06/26/2023, main production tenants begin to upgrade to release 3.47. Apptio
is launching support for Automatically adding and deleting custom dimensions in the
Automated Data Management > Entity Mapping in this
minor release.

## Automated Data Management

This feature is applicable if Automated Data Management is enabled.

Costing & Planning is integrated with the Automated Data Management platform service that
enables automated sharing of data from Costing & Planning Cost (Costing Standard) to Costing
& Planning Plan ( Planning), and brings in the ability to import plan data on-demand from
Costing Standard to a specific plan. To know more, see [ADM
Overview](ADM%0AOverview../../it-planning/planning/adm/adm_overview.dita "(Opens in a new tab or window)").

- Automatically add entity mapping in Automated Data Management  when new custom dimension is
  created in ITP
- Automatically delete entity mapping in Automated Data Management when a custom dimension is
  deleted in ITP

► Learn about: [Custom Dimension Entity Mapping](Custom Dimension Entity Mapping../../it-planning/planning/adm/custom-dimension-entitiy-metric.dita "(Opens in a new tab or window)")

## 3.46 - June 12, 2023

Starting on Monday 06/12/2023, main production tenants begin to upgrade to release 3.46. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.45 - May 29, 2023

Starting on Monday 05/29/2023, main production tenants begin to upgrade to release 3.45. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.44 - May 15, 2023

Starting on Monday 05/15/2023, main production tenants begin to upgrade to release 3.44. Apptio
is launching support for custom date ranges with Planning data sources in this minor release.

## Custom Date Ranges for Apptio BI Reports

ApptioOne Planning data sources in Apptio BI now support following custom periods for
visualizations:

- Month
- Quarter
- Half
- Year

These custom periods are provided in addition to the existing date ranges. You can also use
the Rolling and Compare option with these custom
periods. For more details, visit [Custom Date Ranges](Custom Date Ranges../../it-planning/planning/ssr/custom-date-ranges.dita "(Opens in a new tab or window)").

## 3.43 - May 2, 2023

Starting on Monday 05/02/2023, main production tenants begin to upgrade to release 3.43. Apptio
is launching enhanced sensitive data hiding in this minor release.

## Enhanced Sensitive Data Hiding

If you have an organization structure where you have users who own managing labor headcount and
financials for their respective department or group department level, you need to provide them edit
permissions for the respective departments or group departments. But at the same time if you want
these users to be able to view the labor financials or labor headcount at a higher department
hierarchy excluding the sensitive data for visibility and awareness, you will have very specific
needs to manage the labor sensitive data for this use case.

For example,

![](../../resources/images/it%20planning_images/release-notes/esdh-example.png)

In the above example, user CCO2 has been given Editor access at APPDEV
department. Since the permissions cascade down top to bottom in the cost object hierarchy, CCO2 will
automatically get the Editor access on the child cost object hierarchy for
APPDEV, whether or not specific access is provided to CCO2 user.

Note that CCO2 user is not given Can View Sensitive Columns access at
APPDEV level. But CCO2 user has Can View Sensitive Columns access at
APPDEV L3, a child cost object hierarchy in APPDEV.

With the new changes in ApptioOne Planning 3.43 release, we have introduced a different
permission cascading behavior for the sensitive data permissions. Which enables controlling
permissions at granular level.

In the above example since CCO2 user doesn’t have permission to view sensitive columns at APPDEV
level, the same permission will cascade down in the department hierarchy until it finds a cost
object/department either group or leaf where the permission to view sensitive columns is provided.
If it finds one, then that permission takes precedence over the top-level permission.

Because of this change it is now possible to provide CCO2 user access to view sensitive columns
at APPDEV L3 even though CCO2 doesn’t have permission to view sensitive columns at a higher-level
cost object APPDEV.

You will also notice that CCO2 user has been given explicit access to view sensitive columns on
leaf cost objects APP-BO and APP-SALES, but there is no explicit Can View Sensitive
Columns permission given at APP-LOB. But irrespective of that CCO2 will be able to view
sensitive columns at APP-LOB because the top level cost object APPDEV L3 permission will cascade
down to lower-level child cost objects. In summary, it is not required to give explicit permission
to view sensitive columns on all the leaf cost objects of APPDEV L3 if the permission to view
sensitive columns is provided at APPDEV L3, it will cascade down to lower-level cost objects under
APPDEV L3.

Check the screenshots below to understand the difference between old behavior and new behavior
when handling sensitive data permissions.

## Previous behavior (Prior to ApptioOne Plan 3.43)

![](../../resources/images/it%20planning_images/release-notes/esdh-prev.png)

## New behavior (After ApptioOne Plan 3.43 release)

![](../../resources/images/it%20planning_images/release-notes/esdh-current.png)

The example above is specific Can View Sensitive Columns permissions, but
same rules also apply for Can View Sensitive Financials permission as
well.

NOTE: The non-sensitive data permissions (Editor, Owner and View Only) work the same way as
before. The change is specific only to sensitive data permissions.

## 3.42 - April 19, 2023

Starting on Monday 04/19/2023, main production tenants begin to upgrade to release 3.42. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.41 - April 12, 2023

Starting on Monday 04/12/2023, main production tenants begin to upgrade to release 3.41. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.40 - March 20, 2023

Starting on Monday 03/20/2023, main production tenants begin to upgrade to release 3.40. This
minor release announces the launch of Project List feature.

## Project List

Customers using Integrated Investment Planning can now view all the projects or investments along
with their attributes in a plan level list view. Using the list view admin users can now add, edit
or delete projects at a plan level.

![](../../resources/images/it%20planning_images/project-list.png)

![](../../resources/images/it%20planning_images/project-list-view.png)

► Learn about: [Project List](Project List../../it-planning/planning/iip/project-list-document.dita "(Opens in a new tab or window)")

## 3.39 - February 20, 2023

Starting on Monday 02/20/2023, main production tenants begin to upgrade to release 3.39. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.38 - February 6, 2023

Starting on Monday 02/06/2023, main production tenants begin to upgrade to release 3.38. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance updates.

## 3.37 - January 23, 2023

Starting on Monday 12/23/2023, main production tenants begin to upgrade to release 3.37. This
minor release launches the ability to Enable/Disable Expenses Labor Activity tab and enhancements to
the New Expenses View.

## Enable/Disable Labor Activity Tab

Customers using [Integrated Investment Planning](Integrated Investment Planning../../it-planning/planning/iip/gs-integrated-investment-planning.dita "(Opens in a new tab or window)") can now enable or disable Labor Activity tab
on the Expenses page using settings on the Company Profile page.

## Expenses Page New View

Expenses page New View is updated to show All, Opex and Capex sub-tabs in the Expenses > Summary
tab. Upgrade reference data operation is also supported now from the New View.

To enable “New View” in Expenses, see [Enable Apex Line Item Table.](Enable Apex Line Item Table.../../it-planning/planning/enable-apex-line-item-table.dita "(Opens in a new tab or window)")
