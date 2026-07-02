---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Recent releases"
breadcrumb:
  - "Planning"
  - "Release Notes"
source_path: "it-planning/whats-new.html"
images:
  - "resources/images/it_planning_images/5.25itp.png"
  - "resources/images/it_planning_images/5.26-a.png"
  - "resources/images/it_planning_images/5.26b.png"
  - "resources/images/it_planning_images/5.26c.png"
  - "resources/images/it_planning_images/518-rn.png"
  - "resources/images/it_planning_images/append-li.png"
  - "resources/images/it_planning_images/imp-layout-1.png"
  - "resources/images/it_planning_images/imp-layout-2.png"
  - "resources/images/it_planning_images/release-notes/516-io.png"
  - "resources/images/it_planning_images/release-notes/516-other.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Recent releases

## Release 5.26 - Sandbox: June 22 – 26, 2026 | Main: June 29 - July 3, 2026

**REST API for Asynchronous Expense Data Import**

- The **POST** endpoint initiates an asynchronous import of expense data in CSV format for a
  specified Plan and returns a unique import identifier.
- The **GET** endpoint retrieves the current status of the import operation using the provided
  import identifier.

This enhancement enables organizations to efficiently automate and scale expense data
imports, particularly for frequent or high-volume updates.

To learn more, visit [Plan APIs](planning/plan-data-api.html#plndataapi__async).

**Currency Support for Plan Export REST API**

The Plan Export REST API has been
enhanced to support currency selection during data export.

Export plan data in either:

- **Original Currency** (default) – Exports financial data in the same currency specified for
  each line item, with no currency conversion applied.
- **Company Currency** – Exports financial data in the company's default currency. All monetary
  values are automatically converted using the applicable exchange rates.

This enhancement provides greater flexibility for reporting and analysis across
multi-currency plans. To learn more, visit [Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=overview-plan-apis#plndataapi__title__3 "(Opens in a new tab or window)").

**Calendar Day–Based Amount Spreading for Other Expenses** 

Monthly amount
distribution in **Expenses > Other** can now be based on the number of calendar days in each
month.

**Key Capabilities**

- Administrators can configure **Calendar Days** as the default spreading method in **Company
  Profile** settings.
- When enabled, amounts entered at the **quarterly** or **annual** columns are automatically
  distributed across months based on the number of calendar days in each month.
- Users can override the default spreading method at the **Expenses table** level and choose
  between:
  - **Even Spread**
  - **Calendar Days Spread**

This provides greater flexibility and improves the accuracy of expense allocation across
reporting periods.

![data spread setting in company profile](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.26-a.png)

![data spread setting in expenses page](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.26b.png)

![data spread settings options](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.26c.png)

**Bug Fixes** 

- Fixed visibility issues with the Plan Versions and Variance Drivers dropdowns for
  single-department leaf groups, ensuring proper display and permission-based access.
- Fixed an issue in the Summary tab where drilling down into the Spend Waterfall chart while
  comparing plans resulted in a blank popup with an E10000 error. Users can now successfully drill
  down into waterfall charts when comparing forecast plans to budget plans, and the comparison popup
  displays line items correctly.
- Fixed an issue in the New Expenses view where the Total row disappeared when adding a plan
  comparison.
- Fixed an issue in the New Expenses view where the Year to Date (YTD) column disappeared when its
  containing fiscal year was deselected in Date Groups.
- Fixed an issue in the Labor tab where dependent picklist fields (such as Cost Center Code) were
  not automatically populated when adding new lines until the page was refreshed.
- Fixed an issue where user permissions could not be saved in Plan Settings when Department Name
  was not defined in the Department reference data.

## Release 5.25: Sandbox: June 8 – 12, 2026 | Main: June 15 - 19, 2026

**Time‑Effective Labor Allocation Rules at Plan Level**

You can now define
**time**‑**effective Labor Allocation Rules at the plan level**, enabling more flexible
modelling of fully burdened labor costs across multi‑year plans. This allows you to apply different
rule values over time—such as **benefits, bonuses, training, and other cost components**—without
impacting global reference data.

**Key capabilities**

- Extend **global labor allocation rules** with **plan**‑**specific effective date
  timelines**
- Define **Effective From** values to control when rule changes take effect
- Automatically apply the correct rule during labor cost generation based on the relevant
  period

This enhancement enables more accurate, scenario‑driven labor cost planning with changing
assumptions over time.

To learn more, see [Time-Effective Labor Allocation Rules](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-labor-allocation-rules#laballrul__title__6 "(Opens in a new tab or window)").

**Cost Object Permissions Moved to Reference Data**

The **Cost Object Permissions
page** is now available as a tab within **Reference Data**, bringing permissions management
alongside related configuration elements in a single, unified location.

![image of cost object permissions](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.25itp.png)

**Bug Fixes** 

- Fixed an issue where the "Insert Row Above" and "Insert Row Below" options were missing when
  right-clicking on rows in the Cost Object Permission table. These row insertion options now appear
  correctly, allowing users to add new permission rows as needed.
- Fixed an issue in the Old Expense view where selecting or deselecting date columns (Month, FY
  Total, YTD, Quarters) using the "Show/Hide Columns" menu did not work. Users can now successfully
  show and hide these period-related columns, and the "Select All" button functions correctly to add
  all available columns to the report.
- Improved the Variance Analysis Actuals tab to default to the last period containing actual data
  within the configured date range, rather than defaulting to the last period of the entire range.
  This ensures users see relevant actual data by default when analyzing variances, eliminating the
  need to manually select the correct period.
- Fixed an issue where having multiple reference data entries with identical names but different
  codes (such as Account Categories) caused incorrect grouping and filtering behavior in dashboards.
  When grouping by name, all associated line items now display correctly, and expanding grouped rows
  shows all relevant data instead of only a subset.
- Fixed an issue where dropdown columns affected by Line Item Filters displayed only the "Name"
  value instead of the expected "Code - Name" format. Dropdowns now consistently show the Code-Name
  combination for all columns, whether or not Line Item Filters are applied, ensuring uniform data
  presentation across the application.
- Fixed an issue in the New Expense View where filters were not being saved within layouts.
  Filters now persist correctly when saving layouts, ensuring users' filter preferences are retained
  across sessions.
- Fixed an issue where custom list values containing trailing spaces caused grouping, filtering,
  and expansion to fail. The system now properly handles values with extra spaces, ensuring that
  grouped rows can be expanded and filtered correctly without displaying "No results" errors.

## Release 5.24 - Sandbox: May 25 – 29, 2026 | Main: June 1 - 5, 2026

Maintenance Release 

This release contains
system maintenance updates and bug fixes.

Bug Fixes 

- Fixed an issue where the **Working Hours per Day** field was disabled when creating or
  editing working calendars, even with **Integrated Investment Planning** enabled. Users can now
  update working hours as expected for accurate labor planning.
- Fixed an issue where removed column grouping in the **Expenses (New View)** was automatically
  re‑applied after a refresh. Layout changes now persist correctly without reintroducing removed
  groupings.
- Fixed an issue where KPIs showed incorrect currency when multiple cost objects were selected in
  **Currency: Original** view. Aggregations now use the **cost object currency** when all
  selected cost objects share the same currency, and default to **company currency** only when
  currencies differ.
- Fixed an issue where **comparison data was not included** when exporting using Export Layout
  option from the **Contracts** and **Assets** tabs. Exports now correctly include comparison
  columns, consistent with other expense tabs.
- Fixed an issue where updates on the **Targets** page were not reflected immediately and
  required a page refresh. Changes now appear instantly, ensuring a consistent and accurate view
  without manual refresh.
- Fixed an issue where users encountered errors when importing data into the **Contracts** tab.
  Imports now complete successfully with proper validation, ensuring a smoother workflow during
  planning updates.
- The **“Update Actuals Data”** action is now renamed to **“Update Financial Actuals”**
  across all tabs in the **Expenses** page. This updated naming is also reflected in the dialog and
  **Change History**, providing clearer and more consistent terminology.
- Fixed an issue where newly created users were not immediately visible in **Plan Permissions**
  and **Cost Object Permissions**. Users now appear correctly, allowing permissions to be assigned
  without delay.
- Fixed an issue in Project Financial Planning (PFP) Project List where selecting a file in the
  Import Projects dialog did not trigger upload or enable the import action. File selection and import
  now work as expected, ensuring uninterrupted project data uploads.

## Release 5.23 - Sandbox: May 11 – 15, 2026 | Main: May 18 - 22, 2026

**Actuals Identification in Forecast Plans**

- In Forecast plans, line items that include actual amounts are now automatically identified with
  **Actuals as Line Item Type**, while forecast lines remain unchanged.
- This enables clearer reporting and more accurate analysis when grouping, filtering, or comparing
  data by **Line Item** **Type**.

**Improved Extension Handling for Duration Based Contracts**

- Contract extensions are now applied more accurately for contracts using **Straight Line by
  Duration** and **Straight Line Duration Custom Calendar** amortization methods.
- A new **Extension Offset** option lets you control whether an extension starts on the **Next
  Day** or the **Next Month**, preventing misaligned renewal dates and incorrect
  amortization—especially calendar year contracts and leap years.
- This ensures extended contracts align cleanly with fiscal periods and user expectations.

**Fixed Period Labor Allocation Methods**

Two new amortization methods are now
available for **Labor Allocation Rules**, enabling cost distribution based on **fixed period
ratios**.

- **Straight Line Using Calendar Days Fixed Period**: Distributes costs based on the number of
  calendar days in each fiscal period relative to the full fiscal year, without prorating employment
  start or end dates.
- **Straight Line Using Working Days Fixed Period**: Distributes costs based on working days in
  each fiscal period, using the configured working calendar, without prorating employment start or end
  dates. Falls back to even period distribution when working calendars are fixed.

**Plan Specific Descriptions in the Plan Header**

- Admins and Budget Process Owners can now add a **plan**‑**specific description** to
  provide context, guidance, or key assumptions using the **Description** field in the **Edit
  Plan** dialog.
- The description appears in the **Plan Header**, making important information easy to access
  while working in the plan. Users can show or hide the description at any time using the **bell
  icon** in the plan header.

**Display Period Date Ranges in Expenses (New View)**

- Administrators can now enable a **Show Period Date Ranges** setting in the **Company
  Profile** to show start and end dates for each period in the Expenses (New View) table.
- When enabled, period date ranges follow the company’s fiscal calendar and respect user locale
  for date formatting, providing clearer time period context in the table.

**Bug Fixes** 

- Fixed an issue where users couldn’t edit variance driver notes when there were unpublished
  changes in Account Category Reference Data. Editing now works correctly without requiring those
  changes to be published.
- Fixed an issue in the **Expenses (New View)** where expanding rows from a comparison plan
  caused an error. Rows now expand correctly, allowing users to view detailed data without
  interruptions.
- Fixed an issue where configuring **Variance Analysis** showed an error when **Labor
  Summarizations** was disabled. Configuration now works as expected without requiring the setting
  to be enabled.
- Fixed an issue where entering values in the **FY column** while **quarter columns were
  hidden** resulted in incorrect distribution across months and inaccurate quarter totals. Period
  calculations now correctly align across months, quarters, and yearly totals.
- Comparison data in the **Expenses table** is now visually differentiated, with grouped
  columns and a subtle background highlight. This makes it easier to distinguish comparison data from
  the base plan.

## Release 5.22 - Sandbox: April 27 – May 1, 2026 | Main: May 4 - 8, 2026

**Period‑over‑Period Comparisons in Expenses (New View)**

You can now compare
periods within the same plan—year‑over‑year, quarter‑over‑quarter, or month‑over‑month—directly in
**Expenses > New View**, making it easier to analyze trends and changes over time.

**Key
capabilities**

- Compare **years, quarters, or months** based on the period you select
- View and sort by **absolute or percentage variance**
- Available across all tabs that support Plan‑to‑Plan comparisons, with the same default grouping
  behavior

To learn more, see [Period to Period Comparison](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-compare-versions#Compareversionsorplans__title__2 "(Opens in a new tab or window)").

**Restore Department Budget to Previous Version**

**Cost Center Owners** can now
restore a previous snapshot and make it the current version of plan data for their department. This
makes it easy to recover from unwanted changes and continue planning from a known, trusted point in
time.

**Key capabilities**

- Restore a prior snapshot for a specific department if user has Edit access on the
  Department
- Available when Plan is in Open state and the Department is in-progress state.
- Tracks restore actions in Change History for full visibility and auditability

To learn more, see [Restore Snapshot](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=collaboration-snapshots-versioning#snapshot__title__6 "(Opens in a new tab or window)").

**Cost Object Permissions UI Modernization**

The **Cost Object / Department
Permissions** screen is now modernized to align with the **unified Apptio UX**, while
preserving existing behavior and workflows.

**Key capabilities**

- Consistent permissions management experience aligned with the unified Apptio UX and enterprise
  grid standards
- Full support for **inline editing**, import, export
- List and hierarchy views, column visibility, and role‑based access work as before

**Publish Cost Object Permissions to Plans**

With **Plan Level User
Permissions** enabled, Admins and Budget Process Owners can now publish **global Cost Object
Permissions** directly to selected plans. This simplifies centralized permission management and
keeps multiple plans aligned without manual effort.

**Key capabilities**

- Publish global permissions to **one, multiple, or all plans**, including archived plans
- Control how permissions are applied using **Update Permissions** or **Replace All
  Permissions**

To learn more visit [Publish global permissions to Plans](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-cost-object-permissions#cop__title__6 "(Opens in a new tab or window)")

**Bug Fixes** 

- Fixed an issue where the **Total** column on the **Labor** tab showed incorrect values
  during plan comparisons across fiscal years. Totals now correctly reflect the comparison plan’s
  values for accurate analysis.
- Fixed an issue where the **YTD** column in **Labor Activity (Hours mode)** showed an
  average instead of a sum. YTD values now correctly calculate as **sum** for both grouped and
  ungrouped rows.
- Fixed an issue where the **Expenses Summary page** failed to load for users without access to
  sensitive columns after a sensitive attribute was deleted. The page now loads correctly without
  errors.
- Fixed an issue where users without **All Departments** access saw incorrect default
  selections and were unable to expand projects in the **Project** dropdown. The dropdown now
  correctly reflects user permissions and supports normal navigation.

## Release 5.21 - Sandbox: April 14 – 17, 2026 | Main: April 20-24, 2026

**Change History Export API** 

**Export Change History Logs:** The POST endpoint
allows users to export Change History event logs as a CSV file based on the applied filters.

To learn more visit [Planning REST APIs Overview](planning/plan-api.html "The Apptio Planning REST APIs provide secure, programmatic access to plans, planning data, metadata, and related artifacts within Apptio Planning. These APIs are designed to support automation and system integrations for planning, forecasting, analysis, governance, and data exchange use cases.").

**Import Labor Activity by Resource External Code** 

You can now plan and import
labor activity using **Resource External Code** (such as Employee ID), simplifying labor planning
integrations with external HR systems.

- **Plan labor lines using unique Resource External Codes**

  Define and manage labor resources using a stable external identifier (for example, Employee ID).
- **Import labor activity allocations by Employee ID**

  Labor Activity imports now resolve resources using **Resource: External Code**.

Note: Requires **External Code** feature to be enabled.

To learn more visit
[External Codes](planning/external-unique-identifier.html "When you import or refresh expense data (e.g. labor, labor activity, contracts, assets) from external systems (HR systems, vendor databases, etc.), you need a consistent, unique identifier to match lines in your plan with records in the source system."), [Import Labor Activity by External
Code](planning/iip/unique-labor-resource-identification.html)

**Improved External Code Alignment in Expense Summary** 

- When **External Code** is used as a user‑defined unique identifier on expense lines,
  generated financials from expense lines (Labor, Contracts, Assets, and Labor Activity) are
  summarized in the **External Code** column on the **Expenses > Summary** tab. This makes it
  easier to align Forecast and Actual lines using the same External Code.
- Previously, **External Code** for generated financials appeared only in the Source External
  Code column, which made matching Forecasts and Actuals by External Code difficult.

Note: Requires **External Code** feature to be enabled.

To learn more visit [External Codes](planning/external-unique-identifier.html "When you import or refresh expense data (e.g. labor, labor activity, contracts, assets) from external systems (HR systems, vendor databases, etc.), you need a consistent, unique identifier to match lines in your plan with records in the source system.").

**Reference Data Navigation Update**

**Labor Allocation Rules** and **Line Item Filters** have been reorganized into separate
tabs under **Reference Data** in the left navigation. This brings **reference data** into a
single, centralized location—making it easier to find and manage related dimensions.

**Bug Fixes** 

- Updated the picklist dropdown in the Expenses New View to dynamically adjust its width based on
  content length, ensuring all values are fully visible without truncation.
- Fixed the Project Navigation dropdown to correctly display the topmost parent project when
  multiple projects across different hierarchy levels are selected. Instead of showing “All Projects,”
  the header now reflects the highest-level parent, providing more accurate and meaningful context.
- Fixed an issue in the Targets page where selecting a department with a single standalone
  sub-department caused the parent department to be hidden, preventing its Target from being edited.
  The dropdown now correctly displays the parent department, allowing Target values to be viewed and
  updated as expected.
- Fixed an issue in the Expenses New View where pinned columns would snap back to their original
  position when reordered for the first time. Pinned columns can now be reordered correctly and retain
  their new position as expected.
- Fixed an issue in the Expenses New View where users without the EditExternalLine permission were
  able to duplicate External Line Items. The system now correctly enforces permissions, preventing
  duplication for users without the required access.
- Fixed an issue where parent (generated) attributes were incorrectly displayed in the Other
  table. These attributes are now restricted to the Summary table as intended and no longer appear in
  the Other table.

## Release 5.20 - Sandbox: March 30 – April 3, 2026 | Main: April 6-10, 2026

**REST APIs for Spend Management and Table Layout**

We have introduced the following new REST APIs in this release.

- **Export Data from Spend Management:** The POST endpoint exports actuals data from
  Spend Management
- **Import Data into Spend Management:** The POST endpoint imports actuals data into
  Spend Management
- **Export Spend Management import error help file:** The GET endpoint exports a help
  file in CSV format that contains Spend Management data import errors, enabling users to
  analyze and troubleshoot import failures.
- **Export Expenses Table Layouts:** The GET endpoint exports all table layouts that
  the user has access to.
- **Export Plan Data by Layout:** The Post endpoint for Plan data export is enhanced to
  support a new parameter, **layoutId**, which allows exporting plan data in a specific
  layout format.

**Enhanced Expense Summary with Source Line Context**

You can now view detailed attributes from source line items such as Contracts, Assets,
Labor, and Labor Activities directly within generated financials in the Expenses Summary
tab. This enhancement provides greater transparency, context and traceability, helping you
better analyze and understand spend.

- **Richer Data Context:** Financials now include additional attributes such as
  contract details, asset properties, and resource information.
- **Source-to-Financial Traceability:** Easily trace generated financials back to their
  originating line item using additional attributes in the Summary tab.
- **Layout Support:** Newly added attribute columns are hidden by default but can be
  enabled, saved, and exported via **Export Layout** or **Export All** data export
  options.

The list of newly added summarization attributes for the supported expense types is
provided below.

**Contracts Tab**

|  |  |
| --- | --- |
| **Attribute Name in Contract tab** | **Mapped Attribute Name in Summary tab** |
| Amount | Contract Amount |
| Start Date | Contract Start Date |
| End Date | Contract End Date |
| Contract Amortization Method | Contract Amortization Method |
| VAT Rate | Contract VAT Rate |
| Amount with VAT | Contract Amount with VAT |

**Assets Tab**

|  |  |
| --- | --- |
| **Attribute Name in Asset tab** | **Mapped Attribute Name in Summary tab** |
| Asset Class | Asset Class |
| Asset Life (months) | Asset Life (months) |
| Residual Value (%) | Asset Residual Value (%) |
| Balance Rate (%) | Asset Balance Rate (%) |
| Asset Depreciation Method | Asset Depreciation Method |
| Purchase Price | Asset Purchase Price |
| In-Service Date | Asset In-Service Date |
| Quantity | Asset Quantity |
| Is Existing Asset | Is Existing Asset |

**Labor Tab**

|  |  |
| --- | --- |
| **Attribute Name in Labor tab** | **Mapped Attribute Name in Summary tab** |
| Employee Name | Resource |
| Role | Resource Role |
| Project Labor Role | Resource Role |
| Employee Type | Employee Type |
| Quantity | Resource Quantity |
| Start Date | Resource Start Date |
| End Date | Resource End Date |
| Is Existing Employee | Is Existing Employee |

**Labor Activity Tab**

|  |  |
| --- | --- |
| **Attribute Name in Labor tab** | **Mapped Attribute Name in Summary tab** |
| Resource Cost Center | Resource Cost Center |
| Resource Role | Project Labor Role |
| Activity Type | Resource Activity Type |

User Permission Interpretation for Plan Comparison

When the Plan Level Cost Object Permissions feature is enabled, permissions are applied as
follows during Plan Comparison:

- **Expenses Data**: Comparison data is visible according to the user’s permissions in
  the source plan.
- **Labor Sensitive Data**: Labor sensitive columns and financials are visible only if
  the user has access in all compared plans.
- **Variance Analysis Details**: Variance analysis is displayed according to the user’s
  permissions in the source plan.

**Bug Fixes** 

- Resolved an issue where users were still redirected to their last accessed plan even
  after it had been deleted by an admin, resulting in navigation to a soft-deleted plan on
  login.
- Resolved an issue in setting Labor End Date beyond year 2045 resulted in an
  error.
- Fixed an issue where the Variance Analysis waterfall chart defaulted to the last month
  of the year; it now correctly defaults to the last month of the selected comparison
  period.
- Fixed an issue to ensure users without the *ExternalLineEdit* permission are
  prevented from deleting external lines.
- Fixed an issue where labor expense calculations did not respect the configured hours
  per day in the calendar. Calculations now correctly use the defined working hours,
  including mid–period labor start scenarios and working day–based allocation rules.

## Release 5.19 - Sandbox: March 16-20, 2026 | Main: March 23-27, 2026

**Intelligent Forecasting** 

We’ve expanded **Intelligent Forecasting**
to support Labor, Labor Activity (Hours), Contracts, and Assets, enabling broader
AI‑driven forecasting across planning.

**Labor & Labor Activity**

- Predictive forecasting is now available on Labor and Labor Activity (Hours) tabs.
- Forecast previews show correct units: Headcount for Labor, Hours for Labor Activity.
- Applying forecasts updates labor and labor activity financials automatically.

**Contracts & Assets**

- Forecasting now supports Manual Amortization Contracts and Manual Depreciation Assets.
- Forecasting for unsupported contract and asset rows is disabled.
- Applying forecasts generates updated financials for both Contracts and Assets.

These enhancements bring AI‑powered forecasting to more parts of the planning
workflow, helping users create faster, more accurate, and more consistent forecasts with
less manual effort across labor, activity, contract, and asset planning.

**Bulk Delete User Permissions**

When managing User Permissions at Plan
level, Administrators and BPO users can now quickly remove a user’s permissions across all
the Plans. A new **Delete Permission from All Plans** option is available when one or
more permission rows are selected.

Bulk Delete Action:

- Removes selected permission from all plans (New, Open, Final, and Archived).
- Removes permission from Cost Object Permissions reference data.

**Filter‑Aware KPIs in Summary Charts**

- KPIs on the Summary page (Financials and Headcount) now update automatically based on
  the filters you apply.
- This enhancement ensures that KPI values always reflect the same filtered dataset as
  the underlying charts, providing consistent and accurate insights across the Summary
  view.

**Summarize Labor Financials by Employee Name** 

- You can now summarize labor financials by Employee Name in the Expenses > Summary
  view.
- This update helps you better analyze total labor cost per resource. It can be enabled
  in Labor Summarization settings.

**REST APIs for User Permissions** 

We have introduced REST APIs that allow
programmatic import and export of user permission data within Apptio Planning.

Key
capabilities include

- **Import Permission data:** The POST endpoint imports plan data for user
  permissions or global cost object permissions.
- **Export Permission import error help file:** The GET endpoint exports a help
  file in CSV format that contains permission data import errors, enabling users to
  analyze and troubleshoot import failures.
- **Export Permission data:** The POST endpoint exports user permissions or global
  cost object permissions.

**Bug Fixes** 

- Fixed an issue where renamed Labor custom fields did not appear in the Labor
  Summarization attributes list. Renamed fields now display correctly in Company Profile
  and Summary.
- Improved the Project dropdown so it accurately reflects selected projects—showing the
  project name for single selections and the appropriate project group with a selection
  count for multiple or hierarchical selections—now consistent with the Department
  dropdown.
- Resolved an issue where “Submit All Changes and Finalize” showed an unexpected error.
  Finalization now completes without interruption.
- Fixed a problem that prevented creating a new hyperlink attribute after deleting a
  previous one.
- Resolved an issue during plan creation and Update Actuals where duplicate actuals
  could occur when summarized by unsupported attributes.
- Fixed an issue preventing actuals from updating in forecast plans with more than one
  year of historical data.
- Improved department filtering in User Permissions so searches by code, name, or both
  return correct results.
- Fixed an issue where budget plans could not be deleted after the related forecast plan
  was removed in Variance Analysis.
- Resolved an issue where saving and refreshing a layout caused a duplicate layout to
  appear.
- Fixed an issue in the Expenses → New View where deleted layouts remained visible until
  the page was refreshed.
- Corrected an issue where Costing Integration published incorrect column names due to
  outdated metadata.

## Release 5.18 Sandbox: March 2-6, 2026 | Main: March 9-13, 2026

**Configurable Control for Plan‑Level Permissions** 

You can now enable or
disable **Plan Level User Permissions** from **Company Profile → General
Configuration**, giving you flexibility to manage access the way that works best for
your organization.

- Use **global Cost Object permissions** for centralized control
- Or enable **plan‑level permissions** for more granular access management

To enable or disable Plan Level User Permissions:

1. Navigate to **Settings****(Gear icon)** → **Company Profile**.
2. Select **General Configuration → Access & Permissions**
3. Use **Enable Plan Level Cost Object Permissions** checkbox setting to enable or
   disable the feature.

**Expanded Fiscal Calendar Support for Cloudability Financial Planning
Integration** 

Apptio Planning now supports integration with Cloudability Financial
Planning (CFP) for organizations using **Gregorian calendars with non‑January fiscal year
start months**.

**Enhanced Filtered Line Item Import** 

This update improves how you
selectively replace data when importing line items, giving you more precise control when
using **Replace All Data with Dimension Filter**.

1. **Custom Dimensions** and **Custom Lists** are now supported in dimension
   filtering
2. Dimension and value filters now display in a clear **<code> – <name>**
   format for easier selection

**Customizable Period Column Display**

This enhancement gives you greater flexibility in how period columns are displayed in the
**Expenses New View.**

- Enable or disable **monthly** and **quarterly** columns independently for each
  year
- Save configurations as **reusable table layouts**

![image of customizable period columns](../../../../03-media/apptio-planning/resources/images/it_planning_images/518-rn.png)

**Enhanced Plan Data Export API** 

The Plan Export API now supports
additional export options to better fit your planning workflows.

- Export Labor Activity data as FTE or Hours using the new **laborDisplayType**parameter
- Use the new **isForReimport** parameter to export data in a re‑import‑ready
  format.

**Bug Fixes** 

- Fixed an issue in the Expenses New View that prevents automatically setting Cost
  Object value on setting Cost Center.
- Corrected Targets page dropdown behavior to consistently display the selected parent
  object and its lowest-level descendants, regardless of the number of child objects or
  page refresh, ensuring stable and accurate hierarchy resolution.
- Fixed an issue on the Contracts tab that prevented expanding the final line item group
  when using a 4-level column grouping.
- Fixed an issue allowing invalid cost centers to be applied to Labor Activity lines
  when copy-pasting line items.
- Fixed an issue in the Export for Re-import option on the Labor tab so that both Code
  and Name columns are exported for custom dimensions added to the Labor tab.
- Updated Export Settings in Costing Integration to publish plan data with full
  precision (8 decimal places) and in the original currency defined in Planning.

## Release 5.17 Sandbox: February 16-20, 2026 | Main: February 23-27, 2026

Cloud Financial Planning Integration

This release introduces integration between **Apptio Planning** and **IBM
Cloudability’s Cloud Financial Planning (CFP)**, enabling customers to incorporate cloud
spend into budgeting and forecasting workflows.

**Cloud Tab**

- Customers can enable a new **Cloud tab** in the Expenses New View to manage cloud
  costs directly within Apptio Budgets and Forecasts.
- The Cloud tab can be enabled independently and does not require CFP integration.

**CFP Integration**

- Customers can connect Apptio Planning with Cloud Financial Planning (CFP) to import
  cloud budgets and forecasts from CFP in a single action.
- Imported cloud expenses are automatically mapped to Planning’s financial structure.

**Additional Details** - Use of the Cloud tab and CFP integration requires an **Apptio
Planning Standard license**.

To learn more, visit [Connect to Cloudability Financial Planning](planning/connect-cfp.html).

Improved Layouts in New View

Layouts in New View has been redesigned to improve clarity and layout management:

- The Layouts dropdown now always displays the currently applied layout.
- Layouts created in either the Legacy View or the New View are automatically synchronized
  across both views, eliminating the need for manual syncing.
- Layout management is simplified with the new Manage Layouts experience, allowing users to:
  - View all Public and Private layouts
  - Search layouts by name
  - Rename layouts
  - Change layout visibility between Public and Private
  - Delete layouts

  ![improved layout screen](../../../../03-media/apptio-planning/resources/images/it_planning_images/imp-layout-1.png)

  ![improved layout page](../../../../03-media/apptio-planning/resources/images/it_planning_images/imp-layout-2.png)

Append & Filtered Line Item Import

We’re excited to announce the release of the Append & Filtered Line Item Import
feature—designed to give users more control and flexibility when importing data into
Planning.

**You can now:**

- Append new line items to existing plans without overwriting all current data.
- Filter imports by specific dimensions, such as Project, Account, etc. to selectively
  update and replace subsets of line items.

![append line item](../../../../03-media/apptio-planning/resources/images/it_planning_images/append-li.png)

For more details, see the help documentation [Bulk Upload Lines.](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-bulk-upload-line-item-values "(Opens in a new tab or window)")

Planning Entity Name Update in Automated Data Management (ADM) 

- Planning entity names in Automated Data Management (ADM) have been updated to clearer,
  action‑oriented labels—Import and Publish, to make naming clear and intuitive.
- These updates apply to display names only; all ADM functionality remains unchanged.

For more details, see the help documentation [Connect to Apptio Costing](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=integrations-connect-apptio-costing "(Opens in a new tab or window)").

Plan Approval Status Export API

- Apptio Planning now supports programmatic export of plan approval status data through
  the Export API.
- The POST endpoint allows exporting approval status details in CSV format for external
  processing.

For more details, see the help documentation [Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(Opens in a new tab or window)").

Other Improvements

- The expenses table schema across all expense types (Other Financials, Labor, Contract,
  Assets, and Labor Activity) has been updated to include **Plan Status** as a standard
  attribute, displaying the current status (In Progress, Submitted, Approved, or Returned)
  for each expense line.
- Spend Management now includes **Charge** as a standard Cost Type, alongside the
  existing **Build** and **Run** cost types. This enhancement allows Project Labor
  Activity actuals to be categorized as Charge.
- Spend Management now supports uploading Actuals by **External Code**. When enabled,
  users can import and summarize financials Actuals by **External Code.**
- You can now filter Standard and Custom numeric columns in the Expenses > New View using
  operators such as **equals**, **does not equal**, **greater than**, **greater
  than or equal to**, **less than**, **less than or equal to** and **between**.
  This update makes it easier to quickly find the values you need. Supported numeric fields
  include
  - **Period Columns:** Months, Quarters, Fiscal Year totals, Plan Total, Remaining
    Forecast Total, YTD Total
  - **Labor:** Base Compensation, Labor Quantity, Project Labor Rate
  - **Labor Activity:** Project Labor Rate, Monthly Capacity
  - **Contracts:**Contract Amount
  - **Assets:**Purchase Price, and Asset Quantity.

Bug Fixes

- Fixed an issue that prevented plan comparisons from displaying despite users having the
  appropriate permissions on the selected plans.
- Fixed an issue where graph titles did not update when switching between the
  **Financial** and **Headcount** tabs in a plan’s Summary. Titles now change as
  expected without requiring a page refresh.
- Fixed an issue in **Expenses > New View** where plan comparisons could not be added
  when the view was ungrouped. In contrast to the old view—which automatically grouped data
  by **Account** and **Cost Object**—the New View now handles this scenario correctly
  by automatically applying the necessary grouping when a plan comparison is enabled.
- Improved cost object snapshotting performance. Snapshot time has improved by nearly 50%.
- Fixed an issue where contracts using the Straight Line by Duration (Custom Fiscal
  Calendar) amortization method did not extend when creating a new plan using baseline plan.
  Contracts with end dates prior to the new plan’s start date were not extending as
  expected; they now extend correctly during plan creation.
- Fixed an issue in Plan Export API that prevented data export due to missing parameter.

## Release 5.16 - Sandbox: February 2-6, 2026 | Main: February 9-13, 2026

Intelligent Forecasting

Intelligent Forecasting introduces AI-driven forecasting to automatically generate more
accurate forecasts with less manual effort. The system evaluates historical spend patterns
at the line-item level and applies the most suitable forecasting model to each item.

In this release, Intelligent Forecasting is available for Other expense line items only.
Support for additional line-item types is planned for 2026.

**Key benefits include:**

- Automated model selection based on historical trends
- Outlier detection to improve forecast accuracy
- More accurate and consistent forecasts
- Increased transparency and control, with the ability to review and refine results

This capability helps teams spend less time managing forecasts and more time analyzing and
acting on insights.

For more details, see the help documentation [Intelligent Forecasting Overview](planning/intelligent-forecasting.html "Intelligent Forecasting introduces advanced time-series forecasting techniques into Apptio Planning, empowering teams to produce more accurate, consistent forecasts with less manual effort. The feature analyzes historical spend patterns and automatically applies the most suitable model for each line item.")

![intelligent forecasting](../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/516-io.png)

Variance Analysis Export API 

- Apptio Planning now supports programmatic export of plan-level variance analysis data
  through the **Variance Analysis Export API**.
- The POST endpoint allows exporting plan level variance analysis data in CSV format for
  external processing.

For more details, see the help documentation [Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(Opens in a new tab or window)").

Other Improvements 

- The **Dashboard** now supports **selecting custom date ranges**, allowing
  analysis of reports and charts over any desired time period.

  ![other improvement](../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/516-other.png)
- The **Plan Import API** has been extended to support **External Lines** through
  a new parameter, **externalItems**. When set to **true**, all line items marked as
  external are imported; when set to **false**, they are excluded. For more details,
  see the help documentation [Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(Opens in a new tab or window)").

Bug Fixes 

- Fixed an issue with Snapshot comparison in the Expenses New View.
- Fixed an issue affecting Export Layouts for non-admin users when plan comparison is
  enabled.
- Fixed an issue where period columns (Months, Quarters, Years) were not retained in the
  saved layout in the Expenses New View.
- Resolved an issue with the Export All plan data export setting when sharing Asset Plan
  data using Automated Data Management or legacy Costing Integration.
- Fixed asset depreciation calculations when declining balance even period asset
  depreciation method is used.

## Release 5.15 - Sandbox: January 19-23, 2026 | Main: January 26-30, 2026

External Line Support for Labor and Labor Activity

External line support has been extended to include Labor and Labor Activity. Admins and
Budget Process Owners can now import external lines for both line-item types.

Editing and deletion of external lines in the UI are available to Admins, Budget Process
Owners, and any user assigned the **ExternalLineEdit** permission.

For more details, see the help documentation [External lines](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-external-line-items "(Opens in a new tab or window)")

Export Settings for Costing Integration

A new Export Settings configuration is now available on the Apptio Costing Integration page
when Cost Transparency Integration or Automated Data Management is enabled. This
configuration allows you to define default export behavior for all plan datasets in a
single, centralized location.

**Key capabilities include:** 

- **Export Format Options:** Choose to publish either the full schema (Export All) or
  a re-importable format (current behavior).
- **Currency Settings:** Publish using the organization’s default currency or in
  original currency.
- **Date Format and Decimal Precision:** Configure the date format used when
  publishing to Costing. Decimal precision defaults to organization settings defined in
  the Company Profile.
- **Sensitive Data Filters:** Enable or disable filtering of sensitive labor and
  financial details during publishing.
- **Export Structure:** The option to publish months as rows or columns has been
  moved from the Configure section into this new Export Settings configuration.

For more details, see the help documentation [Connect to Apptio Costing.](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=integrations-connect-apptio-costing "(Opens in a new tab or window)")

Other Enhancements 

- Improved email notifications for the Multi-Level Approval workflow to ensure users
  receive notifications only when relevant to their edit level and position in the
  approval chain. Only the next-level approver receives an email when an approval request
  is submitted. Users with Edit Level: Owner, Edit & Submit, or Edit receive
  notifications when their submitted departments are approved or returned.
- Newly created Memo attributes now support up to 1,024 characters.
- Users with the Admin or Budget Process Owner role can publish the plan-level Project
  List from Apptio Planning to Apptio Costing through Automated Data Management.

For more details, see the help documentation, [Manage Email Notifications](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-manage-email-notifications "(Opens in a new tab or window)"), [Publish Project List to Apptio Costing](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-publish-projects-list-apptio "(Opens in a new tab or window)").

**Bug Fixes** 

- Corrected the Update Reference Data preview dialog to properly classify department
  updates instead of showing them as project updates.
- Fixed an issue in plan creation and the Update Actuals process that could result in
  duplicate actuals when actuals were summarized by attributes not present in Spend
  Management.
- Updated the Help Center link to take users directly to the Apptio Planning
  documentation on the IBM Documentation site.
- Fixed an issue in the Departments dropdown where searching for departments could
  result in errors.
- Fixed an issue where column filters did not correctly filter Project attributes
  according to user permissions.
