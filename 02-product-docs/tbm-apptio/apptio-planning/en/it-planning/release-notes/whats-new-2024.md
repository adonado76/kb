---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "2024 Release Notes"
breadcrumb:
  - "Planning"
  - "Release Notes"
source_path: "it-planning/release-notes/whats-new-2024.html"
images:
  - "resources/images/it_planning_images/3.71-1.jpg"
  - "resources/images/it_planning_images/3.71-2.jpg"
  - "resources/images/it_planning_images/3.72-1.jpg"
  - "resources/images/it_planning_images/3.72-3.jpg"
  - "resources/images/it_planning_images/3.72-5.jpg"
  - "resources/images/it_planning_images/3.73-rn.jpg"
  - "resources/images/it_planning_images/3.74-1.jpg"
  - "resources/images/it_planning_images/3.80-1.jpg"
  - "resources/images/it_planning_images/3.80-2.jpg"
  - "resources/images/it_planning_images/3.80-4.jpg"
  - "resources/images/it_planning_images/3.80-5.jpg"
  - "resources/images/it_planning_images/3.803.jpg"
  - "resources/images/it_planning_images/fcs-1.jpg"
  - "resources/images/it_planning_images/fcs-2.jpg"
  - "resources/images/it_planning_images/finalize-plan.jpg"
  - "resources/images/it_planning_images/fixed-cal1.jpg"
  - "resources/images/it_planning_images/release-notes/3.75-1.jpg"
  - "resources/images/it_planning_images/release-notes/3.75-2.jpg"
  - "resources/images/it_planning_images/release-notes/3.78_rn.jpg"
  - "resources/images/it_planning_images/release-notes/3.81.jpg"
  - "resources/images/it_planning_images/release-notes/3.82-1.jpg"
  - "resources/images/it_planning_images/release-notes/3.82.jpg"
  - "resources/images/it_planning_images/release-notes/3.83.jpg"
  - "resources/images/it_planning_images/release-notes/apptio-bi-ba.jpg"
  - "resources/images/it_planning_images/release-notes/dash-after.jpg"
  - "resources/images/it_planning_images/release-notes/left-navigate-ba.jpg"
  - "resources/images/it_planning_images/release-notes/name-after.jpg"
  - "resources/images/it_planning_images/release-notes/name-before.jpg"
  - "resources/images/it_planning_images/release-notes/summary-after.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# 2024 Release Notes

## 3.83 - December 23, 2024

This release introduces the Variable Labor Compensation Adjustments feature, providing enhanced
flexibility in modeling labor costs. With this functionality, you can:

Variable Labor Compensation Adjustments 

- Apply percentage adjustments to base salaries on a monthly basis, allowing for precise
  compensation planning.
- Define default compensation cycles and merit increases by role to streamline salary adjustments
  across your workforce.
- Model dynamic changes in compensation driven merit increases, market adjustments, or policy
  updates.

  ![plan labor compensation](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.83.jpg)

  For more information, see  [Setting up Labor Compensation
  Adjustments](../planning/plan-labor-compensation.html "Labor Compensation Adjustments allow organizations to model compensation increases (or decreases) over time within Apptio Planning. This feature provides a structured way to account for planned salary adjustments such as merit increases, market adjustments, promotions, or cost-of-living changes.")  .

Bug Fixes 

- Resolved an issue where importing Labor Activity data failed to populate the Resource Cost
  Center.
- Resolved an issue where fields were not displayed on the Contracts tab in the New Expense view.
- Fixed an issue where rows in the Projects dimension became unsearchable when the record count
  exceeded 10,000.
- Fixed an issue where renaming a Project attribute incorrectly logged two events in the Change
  History instead of a single event.
- Enhanced the Create Plan event log to include details indicating whether the Copy Over Line Item
  Codes option was selected (True) or unselected (False).
- Fixed an issue where Change History did not log failure events when a Create Plan action failed.
  Change History will now correctly capture and display logs for failed plan creation attempts.

## 3.82 - December 2, 2024

Select Source Period for Plan Import from Apptio Costing

Cost Center Owners now have the ability to select the source period when importing plan baseline
data from Apptio Costing. Previously, the system defaulted to the latest period.

![replace all data](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.82.jpg)

Contract Total KPI

For Forecast plans, the Contract Total KPI now displays both the Contract Total (actual plus
forecast) and the Forecast Contract Total for the selected time period.

Contract Total  : Total contract amount for historical and forecast periods.

Forecast Total  : Total contract amount for forecast periods only.

![contracts](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.82-1.jpg)

Enhanced Logging for Variance Analysis

This update introduces detailed logging for variance analysis activities, providing greater
transparency and traceability for key actions:

Creating New Variance Analysis  : Logs are now generated when a new variance analysis is
created, capturing information such as the plan name and variance settings.

Adding/Modifying Variance Analysis Explanations  : Any additions or modifications to
variance analysis explanations are logged, including details like before-and-after text, cost
object, account, and associated plan.

Bug Fixes 

- Resolved an issue where "Is Existing Employee" was missing from the Expenses > Labor table in
  the Legacy View when Streamlined Labor was enabled.
- Addressed a problem where import and export functionality did not work for custom lists
  containing the '/' character in the name.
- Corrected a problem where exporting plan data containing an "&" or "," symbols resulted in a
  misformatted file.
- Fixed an issue where dimensions marked as mandatory were not being enforced as required.
- Corrected an issue where null fiscal periods were being sent in the entity pull request to ADM,
  causing ADM to default importing plans from the current calendar fiscal period instead of the
  selected fiscal period.
- Fixed an issue where users with "Can View Sensitive Data" and "Can View Sensitive Financials"
  permissions were unable to publish sensitive Labor data to Apptio Costing.
- Addressed an issue where switching between Legacy View and New View would fail if more than 20
  private layouts were present. • Fixed an issue on the New View where the filters would reset upon
  selection, preventing users from successfully applying filters.
- Resolved an issue where, if SDP or PFP is not enabled, Transaction Type would incorrectly appear
  in the Group By menu on the Summary tab.

## 3.81 - November 18, 2024

User-Specific Date and Number Format

Planning now integrates with Frontdoor’s
User Locale settings, automatically adjusting date and number formats to match each user’s
configured locale. This enhancement allows users to customize how dates and numbers are displayed,
creating a more personalized experience. Each country or region follows distinct standards and
conventions for representing numbers. Variations may include the symbols used for decimal
separation, grouping formats, currency display, and the order of year, month, and day in
dates.

What to Expect

- Starting with Release 3.81, Planning will display dates and number formats based on the User
  Locale settings configured in Frontdoor, rather than the browser’s locale settings.
- The default locale in Frontdoor is en\_US, so if users have not set a preferred locale, dates and
  numbers will appear in en\_US format.
- This change applies only to viewing and entering dates and numbers within the application. For
  import/export files, Frontdoor locale settings are not applied; users should specify
  date and number formats in the formatting options of the import/export dialog.

  ![preferred location field](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.81.jpg)

  For more information, see [Configure Date and Number
  Format](../planning/config-date-num-format.html).

Bug Fixes

- The Comparison Plan dropdown in the Add Comparison or Compare Shortcut dialog now displays plan
  names in alphabetical order, making it quicker and easier to locate the desired plan for
  comparison.
- Fixed an issue where import and export functionality did not work for custom lists containing
  the '/' character in the name.
- Fixed an issue with sorting in the "User Name" column in the Configuration > Cost Object
  Permissions table.
- Fixed an issue where the project export template provided incorrect headers for import into
  project reference data.
- Fixed an issue in PFP environments that prevented reference data updates due to incomplete
  cleanup of custom dimensions in the Allocation and Demand tables.

## 3.80 - November 4, 2024

Custom Comparison Periods for Variance Configuration

Budget Process Owners can now select a custom Comparison Period when configuring variance
analysis to compare actuals to plan. To improve clarity, actuals column names have also been updated
to include "Actuals," such as "Sept FY24 Actuals."

This is an initial release aimed at supporting future enhancements, which will enable
Plan-to-Plan comparisons across any time range such as a full-year variance.

![new comparison period](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-1.jpg)

![comparison end and start date](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-2.jpg)

Expenses User Interface

The import and export buttons for Expenses data have been relocated to the options menu above
the expenses table, creating a cleaner user interface. You can now access these functions directly
from this menu.

![import and export financials](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.803.jpg)

Labor View Enhancement

The Labor tab in the Expenses New View has been upgraded with an "All" sub-tab, bringing
together both planned and existing labor resources into one unified view for easy reference.

The "All" sub-tab includes an Existing Labor column to clearly indicate whether a labor line is
planned or existing. Users can shift labor resources between Planned and Existing by editing the
checkbox in the Existing Labor column.

![existing labor checkbox](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-4.jpg)

Assets View Enhancement

The Assets tab in the Expenses New View now features an "All" sub-tab, combining both planned
and existing assets into a single, unified view for easy management.

In the "All" sub-tab, an Existing Asset column clearly indicates whether each asset line is
planned or existing. Users can move assets between Planned and Existing by adjusting the checkbox in
the Existing Asset column.

![assets view enhancement](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.80-5.jpg)

Bug Fixes 

- Fixed an issue in Integrated Investment Planning (IIP) where updating Projects in the Project
  List using the Project dimension in reference data caused errors if a custom List attribute in
  Project reference data contained null values.
- Also resolved an issue in Summary > Headcount trend chart, which previously displayed the year
  timeline twice along the x-axis.

## Apptio Community Transition to IBM TechXchange - November 1, 2024

Today, Apptio Community has fully transitioned to IBM TechXchange.

Use and bookmark  [this new homepage](https://community.ibm.com/community/user/apptio/home "(Opens in a new tab or window)")  for the Apptio topic groups.

- Access the topic group that is relevant to your needs; Some of the topic groups with which you
  are familiar have been combined into new topic groups.

  The following topic groups are available:
- [Apptio](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=4100dfb8-fc23-4203-83c7-019253cf7c0b "(Opens in a new tab or window)")  : Costing Essentials, Costing Standard (CT-Foundation), Apptio Planning (ITP/ITFMF), Billing (Billing Standard), Benchmarking (Benchmarking), ServiceNow Integration

  - [Planning Release Notes](https://community.ibm.com/community/user/apptio/viewdocument/apptio-planning-whats-new-cumula?communitykey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Opens in a new tab or window)")
  - [TBM Studio and Applications Release Notes](https://community.ibm.com/community/user/apptio/viewdocument/tbm-studio-and-applications-r12-rel?communitykey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Opens in a new tab or window)")
- [Cloudability](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=15c0e07d-35c0-49de-a84b-019253d13376 "(Opens in a new tab or window)")  : Cloud ability Financial Planning, Cloudability TotalCost,
  Apptio Turbonomic Integration
- [Targetprocess](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=55a3712d-1835-4ec2-bcd7-603e88cd9dd2 "(Opens in a new tab or window)")
- [Platform](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8 "(Opens in a new tab or window)")  : Apptio BI, ATUM, Automated Data Management, DataLink,
  Frontdoor, TBM Studio
- [Apptio for All](https://community.ibm.com/community/user/apptio/communities/community-home?communitykey=2e85ed45-9b8a-486c-bd55-019253d466eb "(Opens in a new tab or window)")
- Once you are in your topic group, read and contribute to all the usual content such as quick
  links, discussions, questions, and blogs.
- Check out  [these
  resources](https://community.ibm.com/community/user/participate/resources "(Opens in a new tab or window)")  on how to navigate and utilize community.
- Start submitting Requests for Enhancements on  [IBM Ideas](https://login.ibm.com/idaas/mtfim/sps/idaas/login?client_id=nwnjmzc5njetmzlkyi00&target=https%3a%2f%2flogin.ibm.com%2foidc%2fendpoint%2fdefault%2fauthorize%3fqsid%3dc75ff073-50e8-4426-8979-7e4b6b992e80%26client_id%3dnwnjmzc5njetmzlkyi00 "(Opens in a new tab or window)")  .

  - IBM uses a unified ideas portal at   [ideas.ibm.com](https://ideas.ibm.com/ "(Opens in a new tab or window)")   for you to raise ideas against all products. As of today,
    that list has expanded to include the products recently acquired from Apptio. Ideas submitted prior
    to the acquisition will be made available to product teams and may be added to the portal at a
    future date to ensure continuity.

Contact the community team at our new email,   [support@communitysite.ibm.com](mailto:support@communitysite.ibm.com "(Opens in a new tab or window)") 
with any questions or needs.

## 3.79 - October 21, 2024

Maintenance release only

This release contains system maintenance updates and bug fixes.

Bug Fixes

- Resolved the issue where updating Actuals caused the generated actuals on the Ledger page to be
  deleted for Project Financial Planning customers.
- Resolved the issue in Update Actuals functionality for Project Financial Planning (PFP)
  environments when actuals are deleted from Spend Management and user want to remove actuals from the
  forecast plan using Update Actuals feature.
- Resolved the issue in Update Actuals functionality when Generate costs in actual periods
  settings is enabled in Project Financial Planning (PFP) > Labor Activity.

## 3.78 - October 7, 2024

Sync Legacy Layouts

Users can now transfer their Expenses Table layouts from the Legacy View to the New View with a
single click, eliminating manual migration and saving time.

To sync layouts, simply click on the Layouts icon in the New View and select "Sync Legacy
Layouts." This will automatically copy your layouts from the Legacy View to the New View. Please
note that you will need to sync layouts for each tab in the Expenses Table individually to complete
the migration from the Legacy View to the New View.

![sync legacy layouts](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.78_rn.jpg)

Bug Fixes 

- Resolved an issue where data uploads were incomplete when using the Japanese locale
  setting.
- Resolved an issue where updating Actuals caused the generated actuals on the Ledger page to be
  deleted for Project Financial Planning customers.
- Resolved an issue where the page would not load after applying comparisons and filters and
  saving the settings to a layout on the New Expense Page.
- Resolved an issue where admin users could not see columns marked as sensitive after assigning
  cost object permissions with view restrictions.

## 3.77 - September 23, 2024

Maintenance release only

This release contains system
maintenance updates and bug fixes.

Bug Fixes

- Resolved an issue where the Contracts tab failed to load when accessed in the New View.
- Resolved an issue where sorting a column in the Cost Object Permissions table caused the page to
  display blank.

## 3.76 - September 9, 2024

Fiscal Calendar Service Integration

Apptio Planning is now integrated with the
Fiscal Calendar Service (FCS), a centralized platform service within Apptio. FCS is designed to
manage fiscal calendars across all Apptio products, allowing customers to define their fiscal
calendar once and apply it across all subscribed products. This integration simplifies fiscal
calendar management with a user-friendly interface that makes it easy to view, edit, and update
calendar configurations.

Please note: If you're using a 445 Variant or 13 Period calendar, you
will manage your calendar definitions through the Fiscal Calendar Service. Calendar types can only
be set during the initial configuration.

How to access Fiscal Calendar Service

FCS is accessible to
users with Admin role. FCS is available as a new application in your Frontdoor
environment.

![fiscal calendar](../../../../../03-media/apptio-planning/resources/images/it_planning_images/fcs-1.jpg)

![fiscal calendar config](../../../../../03-media/apptio-planning/resources/images/it_planning_images/fcs-2.jpg)

For more information, see [Fiscal Calendar
Services](../../fiscal-calendar-services/home.html).

Bug Fixes

- You can now create layouts for sub-tabs within the Expenses tab, such as Existing or Planning
  Labor, in the New View.
- Resolved an issue with exporting Plan data to Apptio Costing (Cost Transparency) when using the
  "Publish Months for all Fiscal Years as columns in a single row" format. The Plan data export now
  correctly adheres to the configured export format settings.
- Fixed an issue in Update Actuals where Project actuals were not being properly distributed
  during the update process.

## 3.75 - August 26, 2024

Starting on Monday, August 26, 2024, main production tenants will begin upgrading to release
3.75. Apptio will be launching the following feature in this release.

Schedule Publishing Plan Data to Apptio Costing

Admin users can
now create daily, weekly and monthly schedules as well as select a time to run the
schedule using Automated Data Management integration to publish Plan data from Apptio Planning to Apptio Costing (Cost Transparency). Additionally,
users can also specify a period in Apptio Costing for which the data should be
published.

This enhancement eliminates the need for manual data publishing and
streamlines the data integration process between Planning and Costing.
Automated Data Management (ADM) will be upgraded on September 4, 2024, to
enable scheduling for publishing plan data to Apptio Costing.

For more
information, see [Schedule
Publishing Plan Data](../planning/adm/adm-sch-pub-plan-to-costing.html "Admin users can now create daily, weekly and monthly schedules as well as select a time to run the schedule using Automated Data Management integration to publish Plan data from Apptio Planning to Apptio Costing (Cost Transparency). Additionally, users can also specify a period in Apptio Costing for which the data should be published.").

![add schedule](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.75-1.jpg)

![add schedule](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.75-2.jpg)

Bug Fixes

- The "Update Actuals" feature was found to have a bug where actuals data was not being updated as
  expected, despite the operation reporting success.
- We have resolved an issue where the summary row totals for Base Compensation (Labor tab),
  Contract Amount (Contract tab), and Purchase Price (Asset tab) displayed incorrect values when
  multi-currency was enabled. Previously, the totals were inaccurate due to improper currency
  conversion. The calculation logic has been updated to ensure that, with multi-currency enabled, the
  summary row totals for Base Compensation, Contract Amount, and Purchase Price are now correctly
  calculated using the average Plan Rate for the selected currency. The average Plan Rate is
  determined by averaging all plan rates for a specific currency over the duration of the plan.
- Resolved an issue where updating actuals with multi-currency enabled resulted in an error. The
  issue occurred when actual line items contained multiple transactions in different currencies for
  the same "Cost Object," "Cost Center," and "Account."
- Fixed the issue where month, quarter, and year data were not visible in the Expenses > New View.
  If you still can't see these columns, follow these steps: Click the Layout button and select "Reset
  columns to default layout." This should display all the period columns (months, quarters, and year).
  Once the columns are visible, go to Layout > Public Layout > Default Layout, and click "Save" to
  save the changes to the default layout.

## 3.74 - August 12, 2024

Starting on Monday, August 12, 2024, main production tenants will begin upgrading to release
3.74. Apptio will be launching the following feature in this release.

Selective Exclusion of Labor Allocation Rules from Fully Burdened Labor
Calculation

In Planning release 3.74, we have introduced a new feature allowing Admin users to
exclude specific Labor Allocation Rules from the fully burdened labor calculation in the Labor tab.
This enhancement ensures that these rules will still generate financial line items on the Summary
tab but will not affect the FY totals displayed in the Labor tab.

Previously, in Planning
release 3.71, we enhanced the budget owner's ability to view the fully burdened labor cost directly
in the Expenses > Labor > FY Total column, eliminating the need to navigate to the Expenses >
Summary section. For more details, please visit the 3.71 release notes.

To accommodate
organizations that prefer not to include certain labor allocation rules in the FY Total shown on the
Expenses > Labor tab, the following updates are
introduced in this release:

- A new column, "Exclude from Labor Calculation," has been added to the Labor Allocation Rules
  table.
- Admin users can select to exclude a rule directly within the table interface.
- Rules are included from the Labor FY Total calculation by default. To exclude a rule, check the
  corresponding checkbox.
- When a rule is marked for exclusion, it does not impact the FY Total displayed in the Labor tab
  but continues to generate a financial line item on the Summary
  tab.

  ![exclude from labor calculation](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.74-1.jpg)

  For more information,
  please refer to [Labor
  Allocation Rules](../planning/manage-labor-allocation-rules.html).

Bug Fixes

- Budget owners will now see the "Fully Burdened Cost" for the fiscal year correctly displayed as
  the sum of all generated costs from actual periods and the generated costs from forecast periods.
  Previously, the absence of Labor actuals led to the Fully Burdened Fiscal Year column displaying
  amounts significantly lower than the Base Compensation amount in Forecast plans. With this fix,
  actual periods are calculated using the Labor Allocation Rules and included in the fully burdened
  "Labor Cost" amounts in the Labor tab; however, financials are not generated for historical periods
  in the Summary tab.

## 3.73 - July 29, 2024

Starting on Monday, July 29, 2024, main production tenants will begin upgrading to release 3.73.
Apptio will be launching the following feature in this release.

Expenses Full-Screen ModeTable Layouts in New Expenses View

The
Expenses Table in the New View now offers enhanced customization capabilities, including
the ability to customize column structure, grouping, filters, and save changes as a
layout. Individual users can create up to 50 private layouts, while admin users can create
up to 50 public layouts. This represents an increase from the previous limit of 30 layouts
in both public and private settings in the Expenses Legacy View.

In a future release
later this year, users will also gain the ability to sync existing layouts from the
Expenses Legacy View to the New View, ensuring continuity and ease of
transition.

![default layout](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.73-rn.jpg)

For more information, please refer to [Table
Layouts](../planning/customize-save-share-apx.html).

Bug Fixes

- Resolved a bug that prevented comparison values from updating when navigating to a specific
  Department from the Status page with a comparison active.
- Fixed a bug where using the Matching Fiscal Years alignment method to add a comparison caused
  the comparison values to display as blank.
- Corrected an issue where the error message for adding a duplicate Project Code incorrectly
  displayed as "Server error, please try again."

## 3.72 - July 15, 2024

Starting on Monday, July 15, 2024, main production tenants will begin upgrading to release 3.72.
Apptio will be launching the following features in this release.

Expenses Full-Screen Mode

The Expenses table now supports
full-screen mode. This setting allows users to maximize screen space for efficiently
viewing and editing expense lines. Note that, the New View table experience is required to
enable full-screen mode.

![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.72-1.jpg)

For more information, please refer to [Working with Apex
line items](../planning/working-with-apex-line-items.html "This topic explains how to manage Apex line items in the application, including adding, inserting, duplicating, importing, exporting, and deleting line items.").

Contract Delegation

Users can now delegate contract expenses to
a different cost center starting from a specified date. This enhancement allows for
accurate allocation of expenses to the appropriate cost center. For projects with multiple
phases (e.g., build/run), delegating expenses to specific cost centers aids in tracking
the financial performance of each project phase effectively.

![image dashboard](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.72-3.jpg)

For more information, please refer to [Delegate Project
Costs](../planning/iip/delete-project-costs.html).

Fixed Monthly Working Calendar

Integrated
Investment Planning now supports a Fixed Monthly Working Calendar, which allows
users to set a fixed total number of work hours per month. This feature allows for
converting FTE labor activity allocations to hourly labor activity
allocations.

![add calendar configuration](../../../../../03-media/apptio-planning/resources/images/it_planning_images/fixed-cal1.jpg)

![calendar setup](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.72-5.jpg)

For more information, please refer to [Working
Calendar](../planning/configure-working-days.html "Working Calendar defines how many working days and hours are used for labor planning, which influences full-time-equivalent (FTE) conversion, amortization of labor costs, and monthly expense calculations.").

Bug Fixes

- Previously, when actuals were empty on the Spend Management page and a user attempted to update
  actuals on the plan for all months with empty actuals, the forecast plan lines were not deleted as
  expected. This issue has now been fixed.
- Fixed an appearance and resolution issue with the Apptio logo in automated messages used to
  inform users of Plan workflow updates.
- Implemented a fix to ensure that when Base Compensation and Labor Allocation Rules are not
  present, the FY total columns in the Labor tab correctly

## 3.71 - July 2, 2024

Starting on Tuesday 07/02/2024, main production tenants begin to upgrade to release 3.71. Apptio
is launching the following feature in this minor release.

View Fully Burdened Labor Cost

Budget owners can now easily
view the fully burdened labor cost directly in the Expenses > Labor > FY total columns,
eliminating the need to navigate to the Expenses > Summary section for this information.
Previously, this column only displayed Base Compensation x Quantity.

For example, in
the Labor tab, you can see a labor line with a FY24 total of USD 196,888. This amount
represents the fully burdened labor cost calculated based on the configured Labor
Allocation Rules.

![full burden labor cost](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.71-1.jpg)

The fully burdened labor cost is the
sum of the general ledger accounts generated from Labor Allocation Rules in the Summary
tab. As shown, the FY24 total in the Summary tab matches the FY24 total in the Labor
tab.

![summary](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.71-2.jpg)

## 3.70 - June 17, 2024

Starting on Monday 06/17/2024, main production tenants begin to upgrade to release 3.70. Apptio
is launching the following features in this minor release.

- Resource Cost Center Selection: It is now possible to easily recognize
  the locked Cost Center in the Resource Cost Center dropdown in Expenses New
  View > Labor Activity. A validation message is shown when locked
  cost center is selected to allocate labor resource to a project. To know more, see [here](../planning/iip/allocate-labor-project.html).
- Finalize Plan: A new option "Finalize Plan" is added in New Expense
  action menu.

  ![finalize plan](../../../../../03-media/apptio-planning/resources/images/it_planning_images/finalize-plan.jpg)

## 3.69 - May 26, 2024

Starting on Monday 05/26/2024, main production tenants begin to upgrade to release 3.69. This
release contains Maintenance updates only.

Maintenance release only

This release contains system
maintenance updates.

## 3.68 - April 22, 2024

Starting on Monday 04/22/2024, main production tenants begin to upgrade to release 3.68. Apptio
is launching the following features in this minor release.

- Show/Hide Period Columns – You can now activate grouping in the
  Expenses > New View. This feature allows you to
  show/hide Month, Quarter and Year columns. To know more, see [Working with Apex columns](../planning/working-with-apex-columns.html "When an Admin or Budget Process Owner enables the Apex Line Item Table feature, users with non-administrator role can change the table view between Classic View and New View.").
- Variance Analysis Fiscal Year Alignment – It is now possible to align the
  fiscal year of the comparison plan in the variance analysis to match the fiscal year of source plan.
  To know more, see [Analayze budget variance](../planning/analyze-budget-variance.html "The Variance Analysis feature helps you compare a current forecast plan against a baseline (budget or previous forecast), identify significant differences, and build a commentary trail that explains the drivers behind variances.").

## 3.67 - April 8, 2024

Starting on Monday 04/08/2024, main production tenants begin to upgrade to release 3.67. Apptio
is launching the following features in this minor release.

- Labor Activity Allocation Analysis - It is now possible to configure
  overallocation and under-allocation thresholds for resource-level labor activity planning. This
  empowers users to analyze labor demand vs labor capacity and make informed decisions regarding labor
  utilization, reallocation, hiring, balancing work and resources. To know more, see [Enable/disable labor activity.](../planning/iip/enable-disable-labor-activity.html)
- Update Actuals Data - You can now update Actuals in an existing forecast
  plan, whether it is in New or Open state. This eliminates the need to recreate forecast plan to
  update the actuals data, resulting in time saving and increased efficiency in monthly forecasting
  cycle. To know more, see [Update Actuals Data](../planning/update-actuals-data.html).

## 3.66 - March 26, 2024

Starting on Monday 03/26/2024, main production tenants begin to upgrade to release 3.66. This
release contains Maintenance updates only.

Maintenance release only

This release contains system
maintenance updates.

## 3.65 - March 11, 2024

Starting on Monday 03/11/2024, main production tenants begin to upgrade to release 3.65 Apptio is
launching the following features in this minor release.

## 3.64 - February 26, 2024

Starting on Monday 02/26/2024, main production tenants begin to upgrade to release 3.64. Apptio
is launching the following features in this minor release.

- Variance Analysis: This feature is used to flag the expense variance
  caused due to expense reported in one plan but absent in another plan. To know more, see [Analyze budget variance](../planning/analyze-budget-variance.html "The Variance Analysis feature helps you compare a current forecast plan against a baseline (budget or previous forecast), identify significant differences, and build a commentary trail that explains the drivers behind variances.").
- Prevent Overallocation: This feature ensures that labor resources are not
  over allocated to projects or investments during Labor Activity Planning, thereby enhancing resource
  management efficiency. To know more, see [Labor Activity Over/Under Allocation Analysis](../planning/iip/manage-over-under-allocation.html).
- Dense Mode: You can now activate Dense Mode on the
  Expenses > New View. This feature applies the latest
  styling changes to the table, optimizing space usage and allowing for maximum rows to be
  accommodated. To know more, see [Working with Apex tables](../planning/working-with-apex-table.html "When an Admin or Budget Process Owner enables the Apex Line Item Table feature, users with non-administrator role can change the table view between Classic View and New View. This topic provides instructions on managing Apex tables, including changing views, selecting date ranges, and adjusting table options.").
- Async Plan Creation (GA) : Async plan creation will be enabled in all the
  main environments starting March 4th, 2024. Plan creation process is now asynchronous. Users can
  begin the plan creation process and continue to use Planning application for performing other tasks.
  Once the plan is created, user will be notified. To know more, see [Async Plan
  Creation.](../planning/create-budget-plan.html)

## 3.63 - February 12, 2024

Starting on Monday 02/12/2024, main production tenants begin to upgrade to release 3.63. Apptio
launches Bulk Delete Expenses in this minor release.

Bulk Delete Expenses

It Is now possible to select multiple
expense lines and delete then in a single click using the Expenses > New
View.

For more information, see [Bulk Delete Expenses](../planning/working-with-apex-line-items.html "This topic explains how to manage Apex line items in the application, including adding, inserting, duplicating, importing, exporting, and deleting line items.")

## 3.62 - January 29, 2024

Starting on Monday 01/29/2024, main production tenants begin to upgrade to release 3.62. In this
minor release, the Product "IT Planning" is renamed to "Planning". This change doesn’t impact any
existing functionality.

Some of the UX changes to align with new product naming are shown below:

Frontdoor app tile/switcher

![name before](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/name-before.jpg)

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/name-after.jpg)

Left navigation panel

![name after](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/left-navigate-ba.jpg)

Apptio BI report collection name

![apptio bi](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/apptio-bi-ba.jpg)

Summary and dashboard charts

The dashboard and summary charts
have been renamed to Spend Breakdown, Spend Waterfall, Spend Tends and Spend Variances,
respectively.

![after summary](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/summary-after.jpg)

![spend variations](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/dash-after.jpg)

## 3.61 - January 15, 2024

Starting on Monday 01/15/2024, main production tenants begin to upgrade to release 3.61. This
release contains Maintenance updates only.

Maintenance release only

This release contains system
maintenance updates.
