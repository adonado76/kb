---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Planning: What's new in 2021"
breadcrumb: []
source_path: "it-planning/release-notes/whats-new-2021.html"
images:
  - "resources/planning_images/icon-itp-apex-add-filter.png"
  - "resources/planning_images/icon-itp-apex-add-filter_20x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planning: What's new in 2021

## 3.10 - December 13, 2021

Starting on Monday 12/13/2021, main production tenants begin to upgrade to release 3.10. With
this release, Planning will have a new Plan header.

## New Plan header

![](../../resources/images/it%20planning_images/plan-header-21-12-13.png)

- The Plan menu has moved to the top left of the screen.
- You now access Plan functions from Options (![](../../resources/images/it%20planning_images/options1_34x29.png)) in the top
  right corner of the screen. This includes Open Plan, Finalize Plan, Submit Changes, Unlock Cost
  Objects, Edit, Compare Shortcuts and Update Reference Data. These functions work in the same way as
  before.

The following pages display the new Plan header:

- Dashboard
- Summary
- Expenses
- Status
- Variance analysis
- Targets

## 3.9 - December 6, 2021

Starting on Monday 12/6/2021, main production tenants begin to upgrade to release 3.9. This
release adds Cost Transparency Integration (CTI) actions to the list of supported Event Types in the
Change History and adds a new Plan header in Planning > Expenses.

## Additional Change History Events

CTI actions are now logged in the Event Log of the Change History service.

[Learn
more about the Change history](../planning/change-history.html)

## New Plan header in Expenses

Planning > Expenses uses a new Plan header, which is rolled out more fully
in release 3.10.

![](../../resources/images/it%20planning_images/plan-header-21-12-13.png)

- The Plan menu has moved to the top left of the screen.
- You now access Plan functions from Options (![](../../resources/images/it%20planning_images/options1_34x29.png)) in the top
  right corner of the screen. This includes Open Plan, Finalize Plan, Submit Changes, Unlock Cost
  Objects, Edit, Compare Shortcuts and Update Reference Data. These functions work in the same way as
  before.

## 3.8 - November 15, 2021

Starting on Monday 11/15/2021, the 3.8 release goes live in main production environments. This
release adds text search to the filter functionality in the Event Log.

[Learn
more about the Event Log](../planning/change-history.html)

## 3.7 - November 01, 2021

## Maintenance release only

This release contains only bug fixes and servicing to support operational requirements.

## 3.6 - October 18, 2021

## Maintenance release only

This release contains only bug fixes and servicing to support operational requirements.

## 3.5 - October 04, 2021

Starting on Monday 10/4/2021, main production tenants begin to upgrade to release 3.5. This
release adds sort and filter functionality to the Plans page.

[Learn
more about the Plans page](../planning/manage-plans.html "With the Plans page, you can manage your plans easily and intuitively.")

## 3.4 - September 20, 2021

Starting on Monday 9/20/2021, the 3.4 release goes live in main production environments. This
release adds new Event types to the Planning Change History: Delete Custom Dimension and Delete Line
Item Filter.

## Additional Change History Events

The following event types have been added to the Change History service:

- Delete Custom Dimension
- Delete Line Item Filter

[Learn
more about the Change history](../planning/change-history.html)

## 3.3 - September 6, 2021

Starting on Monday 9/6/2021, the 3.3 release goes live in main production environments. This
release contains a single feature. Planning now has support for 13-period calendars.

## 13-Period Calendar Support

Planning extends use of custom fiscal calendars to now include support for 13-period
calendars.

For more information, contact your Apptio account team.

## 3.2 - August 23, 2021

Starting on Monday 8/23/2021, the 3.2 release goes live in production environments. This release
contains a single minor feature: Group Actions on Status Page.

## Group Actions on Status Page

The group level actions and status of Cost Objects have been restored for Submit, Approve, and
Return.

[Learn more about group actions](../planning/review-approve-return.html)

## 3.1 - August 9, 2021

Starting on Monday 8/9/2021, the 3.1 release goes live in production environments. This release
contains two minor features: Plan Line Item Codes, an anticipated feature that assigns a unique code
to each line item across Planning, and the addition of new event types to the Change History
service.

## Plan Line Item Codes

Three attributes have been added across tables in Planning:

- Line Item Code
- Source Line Item Code
- Source Plan

Together these three attributes help users identify a given line item and understand how it was
created. For generated line items or entries that weren’t directly due to a direct user input, the
line item code will be blank. The source attributes however will be populated as appropriate.

Line items across the following tables now have an assigned unique code:

- Financial
- Labor
- Contract
- Asset
- Allocation
- Demand

[Learn
more about Line Item Codes](../planning/line-item-codes.html)

## Additional Change History Events

The following event types have been added to the Change History service:

- Add Custom List
- Update Custom List
- Delete Custom List

These events will now appear in the Event Log upon occurring. Tracking of these event types began
with this upgrade. Occurrences of these events prior to this upgrade will not appear.

[Learn
more about the Change history](../planning/change-history.html)

## 3.00 - July 26, 2021

Starting on Monday July 26, 2021, the Planning 3.00 release goes live in production environments.
This release contains three features: the ability to sort entries in the Event Log by the contents
of a column, a new Plan management page, and a new tool to select start and end dates for time
periods.

## Change History Sort

In the Event Log, you can reorder the change history by sorting the entries by column.

You can sort entries by these columns:

- Timestamp
- Event
- Area
- Item Type

[Learn
more about the Change history](../planning/change-history.html)

## Plan management page

A new page has been added called Plans. This page is the new location to
change the Plan you are viewing in the application. You can use this page to perform plan management
procedures such as archiving or deleting plans.

To get to this page, open the navigation pane and select Planning >
Plans.

[Learn
more about the Plans page](../planning/manage-plans.html "With the Plans page, you can manage your plans easily and intuitively.")

## Improved period time selector

Across the application where time is periodic, a new time period selector component has been
added. You can choose to view a specific year from the plan or a custom time range between two
periods. The selector remains in the same location.

## 2.99 - July 12, 2021

Maintenance release

## Maintenance release only

This release contains only bug fixes and servicing to support operational requirements.

## 2.98 - June 28, 2021

The Planning 2.98 release is now live in production environments. This release contains one minor
feature, *Enhanced Configuration Experience*.

## Enhanced Configuration Experience

Planning is transitioning to a new configuration experience. All reference data page
functionality will be migrated to the Configuration module via the left-hand
navigation.

Under Configuration, you can now find the following pages:

- Reference Data: you can still manage all dimensions using the
  Reference Data page with a few minor changes. A new navigation screen has
  been added to separate out the different types of dimensions across the app. You can now manage the
  individual dimension attributes using the Schema page.
- Schema: this new page uses a similar navigation interface as the new
  Reference Data page. It allows you to configure the individual attributes
  across both dimensions and line item tables.
- Custom Lists, Line Item Filters,
  Calendar Setup: no change. The page to manage Line Item
  Filters remains here under Configuration.
- Cost Object Permissions, Labor Allocation Rules
  (previously included under Reference Data)

## How this feature can help you

*Enhanced Configuration Experience* provides a more intuitive user experience to app
configuration. We will continue to make incremental improvements in
Configuration over the upcoming releases to support new features.

## 2.97 - June 14, 2021

The Planning 2.97 release is now live in production environments. Your environment upgrades the
week commencing June 14 on the [chosen upgrade day](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Opens in a new tab or window)"). This release primarily consists of two
features: Change history and Working day labor amortization.

## Change history

A new service and page in Planning gives you the ability to see a log of all the changes made to
a plan. The Event Log surfaces the who, what, and when of any change made across the
application.

![](../../resources/images/it%20planning_images/release-notes/change-history.png)

## How this feature can help you

Users need to understand how a plan evolves with new information, a shift in priorities, or a
decision made during an approval process. Using this feature to view changes increases the
likelihood that minor, hard to find errors can be found and corrected.

## More information about this feature

To access this feature, navigate to Change History > Event Log.

[View
and export the change history](../planning/change-history.html)

## Working day labor amortization

A new amortization method for labor line items, users can now configure the application to
calculate amortization expenses based on the company's unique working day schedule. The feature
supports any number of unique schedules. This method takes into account the actual working days by
calculating a weighted average of working days per month.

For more information, see [Labor Configuration reference data](../planning/manage-labor-configuration.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

## Calendar configuration

In support of this new working day labor amortization method, a new page has been added to
Configuration to create custom work day calendars.

To access this feature, navigate to Configuration > Calendar setup.

## 2.96 - May 31, 2021

## Canceled release

This scheduled release has been canceled. This cancellation will not affect future releases.

## 2.95 - May 10, 2021

## Maintenance release only

This release contains only bug fixes and servicing to support operational requirements.

## 2.94 - May 3, 2021

The Planning 2.94 release is now live in production environments. Your environment upgrades the
week commencing May 3rd on the chosen [upgrade day](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Opens in a new tab or window)"). This release contains the first item of a
multi-release set of changes called *Enhanced Configuration Experience*.

## Enhanced Configuration Experience: Line Item Filters

Over the next handful of releases, Planning is transitioning to a new configuration experience.
Items found in the Reference Data page will be migrated to the
Configuration page, supported by the *Apex* editing experience. In this
release, the Line Item Filters page has been migrated to the
Configuration page.

## To access Line Item Filters

1. In the left-hand navigation menu, select Configuration>Line Item
   Filters.

   ![](../../../../../03-media/apptio-planning/resources/planning_images/icon-itp-apex-add-filter.png)

   You can now add filters, sorting by dimensions or attributes columns. To
   add a new filter, select ![](../../../../../03-media/apptio-planning/resources/planning_images/icon-itp-apex-add-filter_20x20.png). For
   more information, see [Line Item Filters](../planning/itp-dependent-picklists.html "The Apptio Planning user interface uses drop-downs to allow users to enter data from a list of approved options. Line Item Filters allow you to restrict the options which can be selected from a drop-down list based on the value already entered in another column. This makes it easier for the user to select the right option, because they are not overwhelmed with a list of irrelevant options.").

## 2.93 - April 19, 2021

The Planning 2.93 release is now live in production environments. Your environment upgrades the
week commencing April 19th on the chosen [upgrade day](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Opens in a new tab or window)"). This release primarily consists of a single minor
feature: Asset Default Depreciation Method Override.

## Asset Default Depreciation Method Override

This feature allows users to select which Depreciation Method to apply to individual asset line
items.

Previously, asset line items used the Depreciation Method configured for the selected Asset
Class, and the Depreciation Method could not be changed at asset line granularity. Now, users can
change the Depreciation Method in the Expenses > Assets table in the
application. No settings need to be changed in config to enable this capability.

By default, asset line items continue to use the Depreciation Method defined in the Configuration
reference data for their Asset Class.

For more information, see [Plan for decreasing asset values with Depreciation Methods](../planning/depreciation-method.html "Apptio Planning applications use Depreciation Methods to model how the value of an asset decreases over time.")

## 2.92 - March 22, 2021

The Planning 2.92 release is following a unique release schedule. The following [community post](https://community.apptio.com/blogs/debbie-hagen1/2021/02/25/financial-management-292-simplified-versioning "(Opens in a new tab or window)") outlines the release schedule.

For customer environments upgrading during the week, your maintenance window will occur during
the chosen [upgrade day](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Opens in a new tab or window)") per usual.

For a select few customers, your maintenance window will occur over one of the next couple
weekends: 3/20, 3/27, 4/3, or 4/10. You will have already been notified of this upgrade day. Please
reach out to your account teams for further questions.

## New Custom List Editor

Creating, editing, and deleting custom lists has been moved out of reference data and under a tab
called configuration in the recently added, left-hand navigation.

## Public Layout Refresh

Behavior of how public layouts would refresh for other users has changed to be more intuitive.
When a layout is updated, the new layout will be pushed directly to all users upon next refresh of
the webpage.

## Group Editing

Due to the new Simplified Versioning UX introduced in summer of 2020, a pair of group editing
features regressed. This release introduces major Simplified Versioning back-end changes that
allowed us to reintroduce group editing.

The following group editing features have been added across all environments.

- Users can now edit line items that span multiple cost objects in a line item table.
- On the status page, submit/approve/reject actions can now be performed on group cost objects.

Now, rows of submitted cost objects are read-only at a group-level and can only be edited by
entering Edit mode.

## 2.91 - March 8, 2021

The Planning 2.91 release is now live in production environments. Your environment upgrades the
week commencing March 8th on the [chosen upgrade day](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Opens in a new tab or window)"). This release primarily consists of two
unrelated features: Plan-Based Comments and Auto-update Contract Total.

## Plan-Based Comments

Apptio's comments and collaborations service is now enabled in Planning. Users can now enter
comments and collaborate at the plan level with other users. [Learn more about using
comments](../../cnc/using-comments.html).

In Planning the comments icon is right aligned on the top menu bar, as shown below:

![](../../resources/images/it%20planning_images/release-notes/comments-icon.png)

## Auto-update Contract Total

The second feature, Auto-update Contract Total, is a relatively minor user experience change
requested by our userbase. Users have expressed that when manual amortization method is set on a
Contract Line Item, there is confusion around whether the contract amount column reflects the total
periodic costs of the contract. Additionally, some customers want the contract amount to be sourced
from a different system and would like to keep that number independent of the period cost
amortization schedule. This feature addresses both requests.

To enable or disable Auto-Update Contract Total, go to ![](../../resources/images/it%20planning_images/release-notes/settings-icon.png) > Company Profile, scroll down to Enable
Capabilities, and select the Auto-Update Contract Total
radio-button.

![](../../resources/images/it%20planning_images/release-notes/auto-update.png)

When Auto-Update Contract Total is enabled:

- The Amount column will automatically sum up the total periodic costs between the contract start
  and contract end date.
- When the start or end date is changed, the amount will update accordingly.
- When importing contract line items via csv, the amount will be overwritten and be replaced with
  the calculated amount using the start and end dates provided.

When Auto-Update Contract Total is disabled:

- The Amount column will work as it did previously. It will not automatically sum up the total
  periodic costs between the contract start and contract end date. Changing the start or end date will
  have no effect on the total amount.
- This feature will be disabled as default. When environments are upgraded, this feature will
  initially be turned off.
- When importing contract line items via csv, the amount should be included as it will not be
  automatically calculated.

## 2.90 - February 22, 2021

The Planning 2.90 release is now live in production environments. Your environment upgrades the
week commencing February 22nd on the [chosen upgrade day](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Opens in a new tab or window)"). This release primarily consists of
Bonus/Other Compensation handling.

## Bonus/Other Compensation handling

Bonus/Other Compensation handling enables Planning to include other components of labor
compensation in addition to base salary in a plan. Users can now understand and track the total
compensation of labor in Planning.

## To use Bonus/Other Compensation handling

1. On the Expenses page, navigate to the Labor
   table.

   If the Other Compensation column does not appear, right-click a
   header column or select the drop-down arrow to display a drop-down menu.
2. Select Show/Hide Columns.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_showing_column.png)
3. Select Other Compensation, and then click
   Show.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_selecting_other_comp.png)

   The Other Compensation column is now visible in the
   Labor table. The added compensation impacts the summary columns. Below, a
   $10,000 bonus is given to Andreas Delorbe. His cost for FY22 now includes the Other
   Compensation value.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_shown.png)

You can also allocate the Other Compensation rate to different
accounts.

1. To allocate Other Compensation to different accounts, access the
   Labor Allocation Rules in Reference Data.
2. From the Output Value Type drop-down menu, select Percent of
   Other Rate.

   The Labor Amortization Method and the Advanced Rules work the same as
   previously.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_percentage.png)
3. Publish the changes and update the reference data on the Expenses
   page.

   The expense updates as shown below. The Bonus Incentive Plan is set
   as 7% of the Other Rate.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_bonus_incentive_plan.png)

The adjustment percentage and the start and end dates of compensation do not affect
Other Compensation. The Other Compensation value is a
fiscal year value. If the plan covers multiple years, the same bonus value applies to each fiscal
year.

## 2.89 - February 8, 2021

The Planning 2.89 release is now live in production environments. Your environment upgrades the
week commencing February 8th on the [chosen upgrade day](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Opens in a new tab or window)"). This release primarily consists of
Detailed Error Logs, a feature to help users troubleshoot errors when uploading data to the
application. A downloadable file is provided to assist users in troubleshooting if there are errors
when uploading data to Reference Data, Spend Management, and individual line items. The file
highlights problematic rows by appending in-line error messages.

## Detailed Error Logs

Detailed Error Logs helps users quickly troubleshoot their own import issues, shortening the time
required for data entry and service tasks.

The help file containing the error logs can be accessed for Costing Standard Integration,
Reference Data Dimension, Spend Management, and line item imports, including external items. The
help file isn't provided when invalid entries are given on the Project Listing import. The help file
being provided for valid entries will be fixed in an upcoming release.

Detailed Error logs in the help file only include row based errors, not column errors. If an
invalid column is provided in the import attempt, the help file does not provide information
detailing how to troubleshoot the invalid column. Users can make the appropriate changes directly in
the help file and import it into the application. The uploader ignores the error columns.

Regardless of the import stage during which errors are detected, the Export Help
File button is displayed on the import dialog before accepting an import. You can click
the button when a file with error messages is available to download.

![Dialog Modal with Export Help File button](../../resources/images/it%20planning_images/release-notes/itp-r289-1.png)

## How to work with the improved error logs

To understand the feature, consider the following example:

- To be a valid entry, the Cost Object and Cost
  Center values for row 2 must match. We have made a purposeful error to trigger the error
  log.

  ![Simple invalid entry](../../resources/images/it%20planning_images/release-notes/itp-r289-2.png)
- When imported, a dialog is displayed showing the warning notifications. Notifications to be
  addressed in the help file can be found at the end of the message.

  ![A dialog showing a single invalid entry](../../resources/images/it%20planning_images/release-notes/itp-r289-3.png)
- The exported help file appends columns to a csv file of the applicable table. These new columns
  highlight the different errors experienced. Additional meta data is available for the row the error
  occurred in.

  ![An example of a help file for a single invalid entry](../../resources/images/it%20planning_images/release-notes/itp-r289-4.png)

  For entries with
  multiple errors, additional columns are appended at the end of the help file to address each of the
  errors.
- An additional invalid currency entry is made below.

  ![An example import file with multiple invalid entries](../../resources/images/it%20planning_images/release-notes/itp-r289-5.png)
- The dialog now displays multiple errors included in the help file.

  ![A dialog showing multiple invalid entries](../../resources/images/it%20planning_images/release-notes/itp-r289-6.png)
- The help file contains another column with the additional invalid entry.

  ![An example of a help file for multiple invalid entries](../../resources/images/it%20planning_images/release-notes/itp-r289-7.png)

In addition to import locations across Planning, this feature is also available on the Costing Standard Integration page. It functions identically as shown previously. The image below is an
example of a dialog that appears when an invalid entry is found in Costing Standard Integration.

![A dialog for an invalid entry in Cost Transparency Integration](../../resources/images/it%20planning_images/release-notes/itp-r289-8.png)

## 2.88 - January 25, 2021

Maintenance release only
:   This release contains only bug fixes and servicing to support operational requirements.

## 2.87 - January 11, 2021

Maintenance release only
:   This release contains only bug fixes and servicing to support operational requirements.
