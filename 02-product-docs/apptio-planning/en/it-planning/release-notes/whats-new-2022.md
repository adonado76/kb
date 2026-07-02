---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Planning: What's new in 2022"
breadcrumb: []
source_path: "it-planning/release-notes/whats-new-2022.html"
images:
  - "resources/images/icons/icon-back_18x20.png"
  - "resources/images/icons/icon-options_23x20.png"
  - "resources/images/icons/icon-settings.png"
  - "resources/images/icons/icon-settings_20x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planning: What's new in 2022

## 3.36 - December 26, 2022

Starting on Monday 12/26/2022, main production tenants begin to upgrade to release 3.36. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance update.

## 3.35 - December 12, 2022

Starting on Monday 12/12/2022, main production tenants begin to upgrade to release 3.35. This
minor release announces the launch of KPIs display on the New Expenses View.

For more information on enabling the New Expenses View, see [Enable Apex Line Item Table](../planning/enable-apex-line-item-table.html).

Remember: This release does not add or change any functionality in Planning. KPIs can
already be viewed from the Classic Expenses View, and with this release, they would be available on
the New Expenses View as well.

The following is how KPIs would appear on the New Expenses View page:

![kpi](../../resources/images/it%20planning_images/release-notes/kpis_1.png)

The section can be expanded to get a detailed view, by selecting the expand icon to the left of
the KPIs displayed.

![image](../../resources/images/it%20planning_images/release-notes/kpis_2.png)

## 3.34 - November 28, 2022

Starting on Monday 11/28/2022, main production tenants begin to upgrade to release 3.34. This
minor release announces the general availability of Integrated Investment
Planning, an additional capability of ApptioOne Planning.

Remember: This release does not add any new features or change any existing product
behavior for Integrated Investment Planning. It just informs about the beta milestone confirmation
and steps in to the general availability phase for the feature.

## Integrated Investment Planning

Integrated project expense planning eliminates operations and investment silos to increase
accuracy. The main benefits include:

- Minimize budget surprises from project long-tail costs (increased operational and support costs
  because of prior projects)
- Manage resources more effectively across projects and operations, and ensure funded projects
  stay within budget
- Provide resource owners with project demand transparency to improve financial agility

For detailed information on Integrated Investment Planning, see [Get started with the Integrated Investment Planning](../planning/iip/gs-integrated-investment-planning.html).

## 3.33 – November 14, 2022

Starting on Monday 11/14/2022, main production tenants begin to upgrade to release 3.33. This
release contains Maintenance updates only.

Maintenance release only
:   This release contains system maintenance update.

## 3.32 - October 31, 2022

Starting on Monday 10/31/2022, main production tenants begin to upgrade to release 3.32. This
minor release launches the FTE Based Labor Activity Planning.

## FTE Based Labor Activity Planning

You can enter and visualize labor activity by FTEs, which gets converted to hours based on
selected working day calendar. Also, you can customize the number of hours per day.

## More information about the release

The solution is available for integrated investment planning customers.

[Allocate Labor to Project using Role or Name](../planning/iip/allocate-labor-project.html)

## 3.31 - October 17, 2022

Starting on Monday 10/17/2022, main production tenants begin to upgrade to release 3.31. This
release contains system maintenance update.

Maintenance release only
:   This release contains system maintenance update.

## 3.30 - October 03, 2022

Starting on Monday 10/03/2022, main production tenants begin to upgrade to release 3.30. This
minor release launches the Apex Page Header and Automated Data Management (Beta).

## Apex Page Header

You can now have the Apex styled page header experience on all the planning pages. This feature
is available to all planning customers. No new functionality is added and the existing ones are
intact. The only change is in the underlying UI technology and this is an initiative towards
providing consistent look and feel among all Apptio products.

## Classic View - old page header

![image](../../resources/images/it%20planning_images/classic-view-old-page-header.png)

## Classic View - new page header

![image](../../resources/images/it%20planning_images/classic-view-new-page-header.png)

## New View - old page header

![image](../../resources/images/it%20planning_images/new-view-old-page-header.png)

## New View - new page header

![image](../../resources/images/it%20planning_images/new-view-new-page-header.png)

To learn more about the New View please see [Enable Apex Line Item Table](../planning/enable-apex-line-item-table.html)

## Automated Data Management (Beta)

Users are enabled with the automated sharing of reference data from Cost Transparency to Planning
and the ability to import plan data on-demand from Cost Transparency to a specific plan.

Please note this feature is currently in Beta release and available only to select customers
identified for the beta program. Once we complete the beta phase, it will be rolled out to all the
customers. Unless you are a beta customer, you will not be able to enable or use this feature.

With Automated Data Management, the following capabilities are added:

## Automated Data Management for Reference Data

Customers use Cost Transparency Integration to import reference data dimensions and actuals from
Cost Transparency. For more information, see [Working with Cost Transparency Integration Panel](../planning/cti_panel.html "The updated Cost Transparency Integration (CTI) panel, introduced in Planning release 2.78, is a self-contained space where admin users can perform all Cost Transparency Integration tasks within a single control panel. The new panel provides centralized management and one-click import and export with Cost Transparency."). However, importing data
from Cost Transparency is a manual process.

When updated reference data from Cost Transparency is required in the planning, the administrator
needs to know that changes have taken place in the reference data on the Cost Transparency
side, and there is a wait time for the Cost Transparency calculations to complete. Hence,
the calculation queue should be actively monitored to finish before the data can be pulled
into planning. Once the data is ready, the planning administrator has to manually click
buttons on the Cost Transparency Integration page in Planning and
resolve any conflicts due to dependencies between dimensions, as described in the [Reference Table Dependencies Diagram](https://community.ibm.com/community/user/viewdocument/reference-table-dependencies-diagra?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Opens in a new tab or window)"). Manually
pulling reference data from Cost Transparency can become time consuming and a painful
process to debug and resolve the conflicts.

Automated Data Management feature solves this problem by enabling the user to automatically
import reference data from Cost Transparency as soon as it is available. There is no longer a need
to coordinate between the two systems to find out the right time to pull the data, and there is no
requirement to manually click buttons to import dimensions, thus relieving the user from the pain of
resolving the dimension dependency conflicts.

## Automated Data Management for Actuals

Actuals import is manual in this beta release. However, automated import of actuals will be
available before Automated Data Management feature become generally available.

## Automated Data Management for Plan Baseline Data

Customers bring baseline data for planning such as existing labor head count, fixed assets,
existing contracts etc. from external source systems to TBM Studio in Cost Transparency. Modeling
capability provided by ApptioOne - Cost enables them to do data mappings and data transformation so
that data imported from external systems is consumable for financial budget planning process. At
present, customers have to manually export this data from ApptioOne - Cost and then manually import
to a specific plan in ApptioOne - Plan. However, this issue is resolved with the release of this new
feature.

With Automated Data Management for Plan Baseline Data, customers can define the mapping between
the dataset in TBM Studio and the expenses table in ApptioOne - Plan using Automated Data
Management’s Entity Mapping feature and fetch data with the click of a button from within a specific
plan as and when required.

## 3.29 - September 19, 2022

Starting on Monday 09/19/2022, main production tenants begin to upgrade to release 3.29. This
release contains system maintenance update.

Maintenance release only
:   This release contains system maintenance update.

## 3.28 - September 09, 2022

Starting on Monday 09/05/2022, main production tenants begin to upgrade to release 3.28. This
release contains system maintenance update.

Maintenance release only
:   This release contains system maintenance update.

## 3.27 - August 22, 2022

Starting on Monday 08/22/2022, main production tenants begin to upgrade to release 3.27. This
release contains system maintenance update.

Maintenance release only
:   This release contains system maintenance update.

## 3.26 - August 08, 2022

Starting on Monday 08/08/2022, main production tenants begin to upgrade to release 3.26.

Maintenance release only
:   This release contains system maintenance update.

## 3.25 - July 25, 2022

Starting on Monday 07/25/2022, main production tenants begin to upgrade to release 3.25. This
release launches the Dependent picklist tooltip for Apex line-item tables.

## Dependent picklist tooltip

In Apex line-item tables, when options in a picklist are filtered by a value selected in another
column, the table cell will show an info tooltip icon. When you hover over the tooltip, it displays
a column-specific message.

This feature is only available in Apex line-item tables. It is not available in classic line-item
tables.

[Working with Apex line items](../planning/working-with-apex-line-items.html "This topic explains how to manage Apex line items in the application, including adding, inserting, duplicating, importing, exporting, and deleting line items.")

## 3.24 - July 11, 2022

Starting on Monday 07/11/2022, main production tenants begin to upgrade to release 3.24. This
release adds Rename Standard Dimension and **Publish Labor Activity Plan
Data to Costing Standard**for Integrated Investment Planning.

## Rename Standard Dimensions

You can now rename the following project-related dimensions in Integrated Investment Planning:

- Project
- Project Group
- Project Labor Role

## How this feature can help you

Customers can configure the planning experience to align with their execution model. For example,
if a customer refers to an investment as a Product and not a Project, they can rename the Project
and related dimensions to match the terminology they use.

This feature is compatible with English language renaming in the current version.

## More information about this feature

For more information, see [Rename project-related standard dimensions](../planning/rename_dimension.html)

## Publish Labor Activity Plan Data To Costing Standard

Labor Activity plan data in Integrated Investment Planning can now be published to Costing Standard.

## How this feature can help you

Integrated Investment Planning customers want to send the Labor Activity Allocation data to
Costing Standard for variance analysis and reporting. Using the existing Costing Standard
Integration console, they can now publish the Labor Activity data to Costing Standard in the same
way as for other expense line items.

## More information about this feature

To publish Labor Activity plan data to Costing Standard:

1. Navigate to ![settings](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings.png) > Cost Transparency Integration > Publish.
2. Select the plan from the drop-down menu.
3. Select the Labor Activity Line Item Type.
4. Select Publish.

For more information, see [Working with Costing Standard Integration Panel](../planning/cti_panel.html "The updated Cost Transparency Integration (CTI) panel, introduced in Planning release 2.78, is a self-contained space where admin users can perform all Cost Transparency Integration tasks within a single control panel. The new panel provides centralized management and one-click import and export with Cost Transparency.")

## 3.23 - June 27, 2022

Starting on Monday 06/27/2022, main production tenants begin to upgrade to release 3.23. This
release contains system maintenance update.

Maintenance release only
:   This release contains system maintenance update.

## 3.22 - June 13, 2022

Starting on Monday 06/13/2022, main production tenants begin to upgrade to release 3.22. This
release contains system maintenance update.

Maintenance release only
:   This release contains system maintenance update.

## 3.21 - May 30, 2022

Starting on Monday 05/30/2022, main production tenants begin to upgrade to release 3.21. This
minor release adds the new Enhanced Plan Comparison feature.

## Enhanced Plan Comparison

Plans can now be compared by aligning matching fiscal years or by aligning the start year of both
plans.

## How this feature can help you

When doing plan comparison by using the Add Comparison option from the Expenses
table, or using Compare Shortcuts, users need to select an alignment method to compare plans.
There are two alignment methods:

- Plan Start Year - two plans are compared by aligning the starting year of both
  plans.

For example, if Plan A is a two-year plan with fiscal years 2019 and 2020, and Plan B is a
two-year plan with fiscal years 2020 and 2021, then this comparison method will compare fiscal year
2019 of Plan A to fiscal year 2020 of Plan B.

- Matching Fiscal Year - two plans are compared by aligning matching fiscal years between
  two plans.

For example, if Plan A is a two-year plan with fiscal years 2019 and 2020, and Plan B is a
two-year plan with fiscal years 2020 and 2021, then this comparison method will compare fiscal year
2020 of Plan A to fiscal year 2020 of Plan B.

## More information about this feature

For more information, see [Compare versions or plans](../planning/compare-versions-plans.html)

## 3.20 - May 16, 2022

Starting on Monday 05/16/2022, main production tenants begin to upgrade to release 3.20. This
release contains system maintenance update.

Maintenance release only
:   This release contains system maintenance update.

## 3.19 - May 02, 2022

Starting on Monday 05/02/2022, main production tenants begin to upgrade to release 3.19. This
minor release adds the Apex Line Item Table and Asset Depreciation Cost Center features.

## Apex Line Item Table

The Expenses table now uses the Apex styling. With this beta release, administrators can
enable a new table experience from the Company Profile settings.

## How this feature can help you

When enabled, users can easily toggle between the new and old styling of the Expenses
table view.

## More information about this feature

This feature is available to all customers that don't use the Project Financial Planning or
Service Demand Planning feature.

For more information, see [Enable Apex Line Item Table](../planning/enable-apex-line-item-table.html)

## Asset Depreciation Cost Center

Customers using Integrated Investment Planning feature can now assign separate Cost Centers for
the Asset Purchase expenses and Asset Depreciation expenses.

## More information about this feature

For more information, see [Asset Depreciation Cost Center](../planning/iip/asset-depreciation-cost-center.html)

## 3.18 - April 18, 2022

Starting on Monday 04/18/2022, main production tenants begin to upgrade to release 3.18. This
minor release adds the new Context columns to the Change History table.

## Change History Event Context

Under Change History > Event Log, the Event Log table now has the additional
Context and Context Type columns that record the cost object details for applicable
event type.

- The Context column has the source Cost Object Code for events, like: Add Line
  Item, Update Line Item, Submit Cost Object Plan, or Unlock Cost Object
  Plan.
- The Context Type column has details about Cost Object Type.

  Note: The Context and
  Context Type details are logged for all applicable events that happened after releasing the
  Context feature. Existing event logs generated before adding this feature don't have the
  details.

## How this feature can help you

As a user of the Change History feature, you can now filter the event logs by Cost Object
Code.

## More information about this feature

For more information about change history, see [View and export the change history.](../planning/change-history.html)

## 3.17 - April 04, 2022

Starting on Monday 04/04/2022, main production tenants begin to upgrade to release 3.17. This
major release contains the new Integrated Investment Planning feature.

## Integrated Investment Planning

Integrated Investment Planning allows IT leadership to gain in-depth insight into the true cost
of investments and impact on current and future IT budget, while tracking individual investment
costs to plan and make adjustments in real time. The investments can be a project, a portfolio epic,
or a value stream depending on terminology or execution model used in your organization. Investment
costs, for example internal and external labor, infrastructure, vendor, and other related expenses,
can be planned from both the Build and Run perspective to provide a complete picture of Total Cost
of Ownership, while informing about future operational budget needs.

Integrated Investment Planning feature can help you accomplish the following:

- Integrated planning experience for investment budget and operational budget.
- Ability to allocate resources to a planned investment, using role-based or name-based allocation
  methods.
- Configurable charge and cross-charge support.
- Analyze and report the Run and Grow costs.
- Build customized investment expense reports using Apptio BI.
- Track actual investment costs and compare them to a plan.

Tip: Integrated Investment Planning is applicable to Costing & Planning and Costing
& Planning Plus customers who don’t have Project Financial Planning or Service Demand Planning
enabled. If you are using Project Financial Planning or Service Demand Planning and would like to
access Integrated Investment Planning, contact Apptio support.

## More information about this feature

For more information about Integrated Investment Planning, see [Get started with Integrated Investment Planning](../planning/iip/gs-integrated-investment-planning.html)

## 3.16 - March 21, 2022

Starting on Monday 03/21/2022, main production tenants begin to upgrade to release 3.16. This
release contains bug fixes and system maintenance update.

## Fixes

- Added the Configure Variance Analysis button, under
  Planning > Variance Analysis and
  Forecast plan > Dashboard.

  ![image](../../resources/images/it%20planning_images/release-notes/itp-316-configure-variance-anaysis.png)

  ![image](../../resources/images/it%20planning_images/release-notes/itp-316-configure-variance-analysis-dashboard.png)
- Fixed issue related to the Summary > IT Spend Waterfall chart not appearing when
  using filter on custom list or custom attribute.

## 3.15 - March 07, 2022

Starting on Monday 03/07/2022, main production tenants begin to upgrade to release 3.15.

Maintenance release only
:   This release contains system maintenance update.

## 3.14 - February 21, 2022

Starting on Monday 02/21/2022, main production tenants begin to upgrade to release 3.14. This
release contains bug fixes and system maintenance update.

## Enhancements

- In Configuration > Reference Data, we moved the
  Cost Transparency Integration feature from Options (![more](../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png))
  to Settings (![settings](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png)).

  [Find
  your way around Planning and Planning](../planning/navigate-apptio-planning.html)
- The plan menu now has a plan status and plan type details.

  ![image](../../resources/images/it%20planning_images/itp_plan_status_details.png)
- In Change History > Event Log, the column with the details icon is now always the
  first column, even if there is Freeze Column applied to any other visible column.

## 3.13 - February 07, 2022

Starting on Monday 02/07/2022, main production tenants begin to upgrade to release 3.13. This
release adds Enhanced Reference Data Configuration User Interface to better align with the Apex look
& feel.

## Enhanced Reference Data User Interface

With this release, Planning uses an improved user interface for configuring reference data.

To manage reference data, select Configuration > Reference Data then select the dimension
you want to view or edit.

![image](../../resources/images/it%20planning_images/ref-data.png)

- To perform reference data actions such as Import and Export, select Options
  (![](../../resources/images/it%20planning_images/options1_34x29.png)) in
  the top right corner of the screen.
- To choose which columns the Reference data table displays, use the Show/Hide Columns pane.
- To navigate back to the Reference Data page, select Back (![](../../../../../03-media/apptio-planning/resources/images/icons/icon-back_18x20.png)) in the top left corner
  of the screen.

## Show Appropriate Contract Amortization Methods

We have fixed the user interface to show the appropriate contract amortization method based on
whether the environment is using the Gregorian calendar or Custom Fiscal Calendar.

| Calendar Type | Available Contract Amortization Method |
| --- | --- |
| Gregorian Calendar | - Manual Amortization - Straight Line Even Periods - Straight Line Using Calendar Days - Straight Line By Duration - Straight Line Prorate First and Last |
| Custom 13-Preiod Calendar | - Manual Amortization - Straight Line Even Periods - Straight Line Using Calendar Days - Straight Line By Duration Custom Fiscal Calendar |
| Custom 12-Period Calendar | - Manual Amortization - Straight Line Even Periods - Straight Line Using Calendar Days - Straight Line By Duration Custom Fiscal Calendar |

## 3.12 - January 24, 2022

Starting on Monday 01/24/2022, main production tenants begin to upgrade to release 3.12. This
release adds an enhanced Line Item Filters experience.

## Enhanced Line Item Filters

For dimensions that use Code as an unique identifier, for example Department,
Account, Cost Center or Project, users can now define Line Item Filters (also
known as Dependent Picklists) using the unique code.

## New Filters

To define a new filter with a dimension that uses Code as the unique identifier, when
uploading value mappings for the filter you must provide the code value instead of the name value in
the .csv file that will be used to upload the value mapping data. The filter user interface and the
Expenses line item table displays the name corresponding to the code used in the .csv upload.

## Existing Filters

If you already have filters defined with dimensions that uses Code as the unique
identifier, if you export filter value mapping data, the exported .csv file displays the code
corresponding to the name you used when defining these filters.

To make changes in the value mappings, you must use the code for dimensions that have code as
unique identifier. If you don't see the correct value when using filtered values on the Expenses
line item table, check that your filter definition is using the correct code corresponding to the
value you are expecting in the line items table.

## 3.11 - January 10, 2022

Maintenance release only
:   This release contains system maintenance update.
