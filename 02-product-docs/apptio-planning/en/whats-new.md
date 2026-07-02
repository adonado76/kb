---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "whats-new.html"
title: "Recent releases"
breadcrumb: []
source_path: "whats-new.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Recent releases

## 3.88 - March 17, 2025

Restricted Access Dimensions

This release introduces the ability for Admins to designate specific dimensions as "Restricted
Access", ensuring that only authorized users can modify them. This enhancement helps maintain data
integrity and prevents unintended changes.

Key Enhancements 

- New “Restricted Access” Setting  : Admins can mark specific dimensions as Restricted
  Access in the Edit System Attribute dialog within the Schema.
- Granular Permissions  : Only users with the new EditRestrictedDimensions permission can
  edit these dimensions.

  ![](../resources/images/it_planning_images/3.88-1.jpg)
- Read-Only Display  : Users without this permission will see Restricted Access dimensions as
  read-only across the Expenses table.
- New View Tooltip  : A tool tip will appear when hovering over Restricted Access fields,
  indicating that the dimension is read-only.

  ![](../resources/images/it_planning_images/3.88-2.jpg)
- Import Behavior  :
  - Users with EditRestrictedDimensions permission can import and modify Restricted Access
    dimensions.
  - Users without EditRestrictedDimensions permission will have Restricted Access dimensions
    automatically skipped during import, preserving existing values.
  - A warning message will notify users when Restricted Access dimensions are ignored during import.
- Change History  : Changes to Restricted Access dimensions are tracked in Change History.
- Permissions  : A new  EditRestrictedDimensions  permission has been introduced
  and assigned to Admin and Budget Process Owner roles in Frontdoor.

Enhanced Variance Threshold Configuration with AND/OR Operator

This update introduces an "AND/OR" operation type in variance configurations, giving users
greater flexibility when setting variance thresholds. Users can now choose between:

- AND  – Variance must meet both absolute value and percentage thresholds.
- OR  – Variance must meet either the absolute value or percentage thresholds.

  ![](../resources/images/it_planning_images/3.88-3.jpg)

Updated Community Links

Community resource links have been updated to their new locations on the IBM Community platform.

Bug Fixes 

- Exported FTE periodic values are now correctly rounded and limited to two decimal places.

## 3.87 - March 3, 2025

Maintenance release only

This release contains system maintenance updates and bug fixes.

Bug Fixes 

- Optimized the Delegation calculation logic to prevent performance degradation when adding line
  items.
- Resolved an issue in Apptio BI where a user was unable to access the "Planning" data source
  under Data Source Management.
- Removed the duplicate Project dimension in Apptio Costing integration when Integrated Investment
  Planning is enabled. (Requires Apptio Standard).
- Resolved an issue where date dimensions displayed as NaN when line items were grouped in the New
  View.
- Fixed an issue where Grouping settings in the New View do not persist as expected.

## 3.86 - February 17, 2025

Enhanced Variance Analysis

This release expands variance analysis capabilities, allowing Admin users to compare Forecasts
against plans (Budgets or Forecasts) in Open and New states for any selected time period, such as
full-year variance.

Key Enhancements 

- Users can now configure variance analysis between Forecast and Plan (Budget or Forecast) for
  flexible time periods, enabling more comprehensive financial tracking and planning.
- All active plans in Open and New states are now available in the Compare To Plan dropdown when
  configuring variance analysis. However, please note that Cost Center Owners will not have access to
  view variance analysis when comparing to a plan in the New state.
- The Account Category column has been added to the Variance Analysis table, enabling better
  categorization and tracking of financial data.

  ![](../resources/images/it_planning_images/3.86a.jpg)
- Previously, variance analysis was limited to Forecast versus Actuals, but this enhancement
  provides greater flexibility to analyze financial performance across different scenarios.

  Note:
  When comparing to  Forecast Periods  , Admin users can select "  Update Variance Analysis
   " to refresh variance calculations, ensuring variance amounts reflect the latest forecast
  updates. This option is available in the "..." menu on the Variance Analysis page.

  ![](../resources/images/it_planning_images/3.86b.jpg)

Variable Contract Extensions for External Contracts

We have expanded the Variable Contract Extension Adjustments feature to support External
Contracts, which are used to import contract line items as read-only.

- Set up compounding contract extension adjustments for External Contracts.
- Define unique adjustment percentages for each contract extension.

By incorporating these adjustments, you can achieve more accurate financial modeling, accounting
for factors such as inflation and rate changes over multi-year planning cycles. To know more, see
 [here](planning/vrbl-cntc-ext-adj.htm "(Opens in a new tab or window)") .

## 3.85 - February 3, 2025

Remaining Forecast Total in Forecast Plans

This release introduces a new feature in the New View that allows users to toggle the Remaining
Forecast column on or off in Forecast Plans. Remaining Forecast provides a sum of all forecast
periods in the first plan year, offering a quick and consolidated view of remaining forecasted
amounts.

Bug Fixes 

- Fixed an issue where filter settings were not retained when switching between tabs on the
  Expenses page.
- Fixed an issue in Apptio BI reporting where Labor Activity FTE data was incorrectly displayed
  when grouped by quarterly, half-yearly, or yearly intervals. This fix applies to Integrated
  Investment Planning.
- Resolved an issue where importing Cost Object Permissions did not trigger an error for
  non-existent usernames in Frontdoor.
- Addressed an issue where exported plan data did not adhere to the configured number formatting
  settings.
- Resolved an issue where the Boolean Cost Center attribute value was incorrectly displayed as
  "false" in plan comparisons.
- Fixed an issue where Cost Center is not automatically populating in the Labor tab after creating
  a new line item.
- Fixed an issue where Automated Data Management (ADM) loaded forecast data into the wrong fiscal
  year for fiscal calendars with non-January start dates.
- Fixed an issue where the commenting feature is disabled when using the Japanese Locale
  setting.
- Resolved an issue where the "Contract Type" field was not saved when adding a new row in the
  Contracts tab while using Japanese language settings.

## 3.84 - January 20, 2025

Variable Contract Extension Adjustments

This release introduces the Variable Contract Extension Adjustments feature, providing enhanced
flexibility in modeling contract costs. With this functionality, you can:

- Apply compounding extension adjustment on each contract renewal.
- Extend the contract for a duration less than plan length over current default behavior of always
  extending the contract for the full plan length.
- Set different extension adjustment percentages for each contract renewal.
- Provide comments to support each renewal adjustment

This feature enables more accurate modeling by accounting for specific financial changes, such
as inflation or rate adjustments, across multi-year planning cycles.

Note  : This feature is available only when the New View is enabled.

![](../resources/images/it_planning_images/release-notes/3.84.jpg)

![](../resources/images/it_planning_images/release-notes/3.84-1.jpg)

To know more, see [Variable Contract Extension Adjustment](planning/vrbl-cntc-ext-adj.htm "(Opens in a new tab or window)")  .

Project Expense KPIs

This release introduces new Project expense KPIs available when Integrated Investment Planning
is enabled, along with tooltips added to all KPIs for improved usability:

- Project Total  : Displays the combined total of operational (OpEx) and capital
  expenditures (CapEx) associated with a project. This is calculated as the sum of financial line
  items where Project ID is not null.
- Charges Total  : Shows the total credits applied from Project Labor Activity expenses,
  calculated as the sum of line items where Cost Type = Charges.

These KPIs are accessible on  Expenses  >  Summary  ,  Dashboard  and
 Summary  pages. Additionally, the  Charges Total  KPI is included in  Expenses
 >  Labor Activity  . With the addition of tooltips, users can now view detailed
explanations for each KPI directly within the interface, enhancing clarity and usability.

![](../resources/images/it_planning_images/release-notes/384-1.jpg)

IBM Planning Analytics Integration

We are excited to announce the integration of IBM Planning Analytics with IBM Apptio, enabling
seamless connectivity between these platforms to enhance financial planning and analysis. This
bi-directional integration allows users to unify their planning processes, align financial data, and
drive more accurate, data-informed decisions across their organization.

Key Features  :

- Automatically sync financial data between IBM Planning Analytics and IBM Apptio to ensure a
  consistent view of budgets, forecasts, and actuals.
- Combine Apptio’s IT financial management capabilities with IBM Planning Analytics’ planning and
  forecasting tools for more comprehensive and integrated planning processes.
- Reduce manual effort and errors with automated data exchange, ensuring financial plans are
  always up-to-date.

To enable the IBM Planning Analytics data connectors, refer to the configuration guide linked
below.

[IBM Planning Analytics Integration Configuration Guide](../datalink/dlfinancials/ibm-planning-egress-connection.htm "(Opens in a new tab or window)")

Note  : This integration requires IBM Planning Analytics Software as a Service (cloud).

![](../resources/images/it_planning_images/3.84-ibm.jpg)

Bug Fixes 

- Resolved an issue where admin users were unable to view columns marked as sensitive after
  assigning cost object permissions with view restrictions.
- Fixed an issue with Forecast Plan baselining, where selecting a forecast start month in Year 2
  caused the baseline plan to fail in copying lines for all years.
- Addressed an issue in  Expenses  > Contracts  , where default values were not
  populated when adding a new contract line with hidden "Start date" or "End Date" dimensions.
- Resolved an issue with Actuals import where providing a project code instead of a cost object
  code resulted in an invalid cost object and cost center mapping error.
- Migrated the  Create Variance Analysis  dialog to the modern user interface. Note: This
  update is purely a visual enhancement with no functional changes.
- Resolved an issue where importing lists with special characters adds unintended double quotes to
  text values.

[Planning 2024 release
notes](release-notes/whats-new-2024.htm "(Opens in a new tab or window)")
