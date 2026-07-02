---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Planning: What's new in 2020"
breadcrumb: []
source_path: "it-planning/release-notes/whats-new-2020.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planning: What's new in 2020

## 2.86 - December 28, 2020

New features
:   More detailed messages in the CTI status page
:   Users now receive more detailed and helpful messages when importing and exporting operations in
    CTI. Error messages include details necessary to debug and resolve the issue.

Minor enhancements
:   None

## 2.85 - December 7 - December 18, 2020

Maintenance release only
:   This release contains only bug fixes and servicing to support operational requirements.

## 2.86 - December 28, 2020

New features
:   Column Renaming
:   Admins can now change the column names users see during budget line item entry. Prior to this
    release, it was only possible to change column names for custom Dimensions or
    List columns; now it is possible to do so for System dimensions as well. To
    rename columns, simply edit the desired Line Item Table definition in Reference
    Data. The table editor now supports renaming of all columns of type Lookup
    and String.

    ![](../../resources/images/it%20planning_images/release-notes/column-renaming.png)

    Figure 1: Editing Line Item Table column definitions in Reference Data.

    Renaming columns does not require an Update Reference operation in order for a plan to pick up
    the change. Once renamed, users will see the new name in line item table column headers.

    ![](../../resources/images/it%20planning_images/release-notes/colrename-after.png)

    Figure 2: Renamed system columns in Line Item Table.

    Note: Renaming a column simply changes the display name used in the line item table, show/hide
    columns dialog, filter dialog, and grouping selectors in Summary page analytics. It does not change
    the underlying "code name" used in Import/Export or CTI operations

Manual Contract Amortization
:   We now support the ability to manually import, enter and edit the per period amortized expense
    amounts for a contract. To facilitate this, we've added a Manual amortization method and the ability
    to change (override) the amortization method defined by the Contract Type. As before, selecting a
    Contract Type will automatically fill in Contract Amortization field with the method defined in the
    Contract Type, but this field can now be changed. If the amortization method is set to Manual, the
    generated expense amounts become editable.

    ![](../../resources/images/it%20planning_images/release-notes/manual-amort.png)

    Figure 3: Overriding Contract Type default amortization method.

    A 'swirly' icon will appear when the default Contract Type amortization method is modified;
    clicking on it will revert to the method defined by the Contract Type and will force a
    re-calculation of the expense amortization amounts based upon the current contract Amount, Start/End
    Date and other relevant fields (Amortize, Extend, etc.).

    ![](../../resources/images/it%20planning_images/release-notes/manual-amort-2.png)

    Figure 4: Manual amortization method allows direct modification of expense amounts.

    NOTE: while in Manual amortization mode, any edits made to contract parameters (like Amount,
    Start/End Date, Extend, etc) have no impact on the per period expense amounts.

    It is also possible now to import contract line items with per period expense amounts instead of
    having Planning calculate the amounts for you. To do so, one must import the line items with the
    Contract Amortization Method set to Manual Amortization. If the Contract Type is using a different
    amortization method, then the Default Contract Amortization Method Overridden field must be set to
    TRUE.

    ![](../../resources/images/it%20planning_images/release-notes/import-template.png)

    Figure 5: Manual amortization method can be used to directly import contract expense amounts (per
    period).

    Finally, it is now possible to import contract line items as external line items. External line
    items are treated as sourced from an external system and read-only within Planning. Use this in
    conjunction with manual contract amortization to bring in periodic contract expense amounts that
    have been calculated by another system.

    ![](../../resources/images/it%20planning_images/release-notes/external-line-items.png)

    Figure 6: Importing external contract line items.

Dimension Grouping and Descriptions in Apptio BI
:   You can now view the list of dimensions grouped by the dimension type when configuring
    visualizations. In addition, you can hover over the help icon next to the dimension name to view a
    description of the dimension.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(3).png)

    Figure 7: Grouping of dimensions in Apptio BI

    SEE ALSO:

    User guide: [Planning data in Apptio BI](../planning/it-planning-data-self-servic-reporting.html "Apptio BI allows users to build and share their own custom reports using data from a variety of applications, including Planning.")

Minor enhancements
:   None

## 2.83 - November 9 - November 20, 2020

New features
:   Apex Shell Support

    ITP now runs in the new Apex shell. Users can toggle between the shell's new left-hand navigation
    panel or the current menubar-style navigation via their User Profile
    menu.

    For more information on Apex, see [Apex Design System: Navigation Update](https://community.apptio.com/docs/DOC-13878 "(Opens in a new tab or window)").

Minor enhancements
:   System maintenance updates only

## 2.82 - November 2, 2020

New features
:   Apex Styling Support
:   We’ve made minor changes to our UI styling to better align with the Apex look & feel. Apex is
    the new Apptio-wide common UX which will be introduced later this year. Basically, we've changed
    fonts and colors to give our apps a cleaner, more modern look. We also modified the styling of the
    plan header (the area just below the app menus and the start of the page content) to cleanly
    separate it from app navigation and to provide a crisper look, as you can see in the images
    below.

    New App Look and Feel

    ![](../../resources/images/it%20planning_images/release-notes/apex1.png)

    Here's a more detailed look at the changes in the plan header styling. There's no functional
    changes: everything still works the same, just looks a bit different, and better.

    Previous Plan Header Styling

    ![](../../resources/images/it%20planning_images/release-notes/apex2.png)

    New Plan Header Styling

    ![](../../resources/images/it%20planning_images/release-notes/apex5.png)

Department Level Dimensions in Apptio BI
:   We've added new dimensions (Level 1 and Level 2) to the Planning Apptio BI data sources. Level 1
    and Level 2 refer to the top and next top level department roll-up associated with a line item's
    cost object (department). Level 1 is the first list of departments that appear in the "All
    Departments" drop-down in Planning; Level 2 is the next list of departments that appear under Level
    1 departments. These dimensions support executive-level reporting by providing for aggregation of
    plan line item values up to executive and senior manager's department levels.

    ![](../../resources/images/it%20planning_images/release-notes/apex4.png)

    Figure 1: Level 1 and Level 2 values in Planning's "All Departments" drop-down list.

    ![](../../resources/images/it%20planning_images/release-notes/apex6.png)

    Figure 2: Level 1 and Level 2 dimensions can be found in Apptio BI visualization configuration,
    under "Add Dimensions" drop-down list

Minor enhancements
:   None

## 2.81 - September 28 - October 9, 2020

New features
:   Hide Sensitive Labor Data from Users
:   You can now identify sensitive labor columns and hide those sensitive labor data from users in .
    First, the administrator will identify the columns in the Labor expense tab
    that are sensitive and need to be hidden from users. Then the users who should not have access to
    sensitive labor data can be revoked access to those sensitive labor data. By default, the users will
    have access to the sensitive labor data.

    NOTE: After upgrading your Planning tenant, existing users will continue to have access to
    sensitive labor data. To revoke certain users from access to the sensitive labor data, revoke the
    user's access directly from Cost Object Permissions.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(2).png)

    Figure 1: Configure sensitive labor data

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_3%20(1).png)

    Figure 2: Grant access to sensitive labor data

    SEE ALSO: User guide: [Hide Access to Sensitive Labor Data in Planning](https://community.apptio.com/docs/DOC-13724 "(Opens in a new tab or window)")

Dependent Picklists
:   Dependent picklists give you the ability to filter the list of values displayed in a picklist
    based upon other values in the line item. For example, the list of Vendors can be filtered by the
    current Asset Class selection to show only Hardware or Software vendors. Dependent picklists make it
    easier for Admins to constrain the number of choices available to the user during line item data
    entry improving data quality while providing a better entry experience for users.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(2).png)

    Figure 3: Table with dependent picklist (right) is used to filter results, making it easier to
    make choices

Minor enhancements
:   None

## 2.80 - September 28 - October 9, 2020

New features
:   None

Minor enhancements
:   System maintenance updates only

## 2.79 - September 14 - September 25, 2020

New features
:   Shared CT instance support in CTI
:   You can now connect multiple ITP instances to a single shared CT instance - for example, a
    sandbox and main ITP environment - using Token Auth as the authentication
    method.

    For more information on the configuration process, see [Integrate with
    Cost Transparency](../planning/integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.") and CT Integration Panel.

Minor enhancements
:   None

## 2.78 - August 31 - September 11, 2020

New features
:   Enhanced Costing Standard Integration (CTI)
:   We have enhanced the Costing Standard Integration experience to provide centralized
    management and one-click import and export with Costing Standard. The existing CTI Settings page has
    been replaced with a menu page that centralizes all CTI tasks into one place, removing complexity
    and tedium from the process of exchanging data with Costing Standard.

    When you access CTI, you
    see a new panel with the following options:

    - Configure – configure and modify your integration settings.
    - Import Actuals – bulk import Actuals datasets from CT
    - Import Reference Data – bulk import Reference datasets from CT
    - Publish – bulk export plan data to CT
    - Status – view the status of data import & export requests

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_5.png)

    Note: You can still import and export to CT directly from individual reference
    data and plan line item tables via the Import from CT and Export
    to CT table actions. The new CTI experience simply provides a central place to perform
    bulk import and export operations.

    For more information on the configuration process, see
    [Integrate
    with Cost Transparency](../planning/integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.") and CT Integration Panel.

Minor enhancements
:   None

## 2.77 - August 14, 2020

New features
:   None

Minor enhancements
:   System maintenance updates
:   This release includes system maintenance and bug fixes only.
:   Fixed in this release:

    - External labor rates are now editable. Users can now edit the labor rates for line items in the
      Project > Activity > External
      table.
    - We added the Update Reference Data button to the header bar in Spend
      Management. Previously, this operation was only available via the Actions
      menu

## 2.76 - July 31, 2020

New features
:   Planning data in Apptio BI
:   You can now create and share custom reports in Apptio BI using plan data from Planning. You can
    create and view reports in Apptio BI that use the latest real-time plan data. Your reports can
    feature multiple visualizations, including visualizations from different data sources. For example,
    a single report can contain visualizations from both Costing Standard and Planning.

    Department expenses are available as Planning Financials, Labor, Contracts, or Assets data
    sources in Apptio BI. After selecting a data source, you can select any active plan in the
    Plan Name field to use for a visualization. The dimensions available for
    reporting are the same dimensions available in department's Expense tab in
    Planning, including custom dimensions. In addition to the existing Apptio BI date ranges, you can
    also select date range for Next Year, 2 years future, and up to 6 years future to use for your
    visualization.

    NOTE: After upgrading your Planning tenant, if your environment already have Apptio BI, ITP data
    sources will be available in Apptio BI within 1 hour. Refer to the full deployment schedule here.
    Existing Planning cost object level permissions will be enforced in Apptio BI.

    NOTE: This feature is currently not available to tenants running in GovCloud or IRAP.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1.png)

Import Existing Asset Depreciation
:   We added a new Manual Depreciation method which means you can now import and edit asset
    depreciation amounts. We also added support for external asset line items so that you can import
    asset details (and depreciation amounts) from an external system so that budget owners can view, but
    not edit, the imported line items.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_3.png)

Minor enhancements
:   None

## 2.75 - July 13, 2020

New features
:   None

Minor enhancements
:   System maintenance updates only

## ITP Apptio BI L1, L2 Dimension - February 11, 2020

◆ Applies to: Planning, Planning Foundation, Project Financial Planning, and/or Service Demand Planning as noted below.

In this release:

- [Department Level 1 and Level 2 Dimensions in Apptio BI](whats-new-2020.html)
- [Stay informed about product updates](whats-new-2020.html)

## Department Level 1 and Level 2 Dimensions in Apptio BI

You can now select 2 new dimensions (Level 1 and Level 2) from the Planning data sources in
Apptio BI. The Level 1 and Level 2 are the top and next top level department roll-up associated with
the line item's cost object. The Level 1 is the first list of departments that appear in the "All
Departments" drop-down list in Planning while selecting the department to view the plan. The Level 2
is the second list of departments that would appear under the Level 1 in the "All Departments"
drop-down list. This will allow the user to create a visualization that aggregates the plan for the
executive and senior manager's department levels in order to produce executive reports.

![](../../resources/images/it%20planning_images/itp-ssr-l1-l2-dimension-1_700x355.png)

Figure 1: Level 1 and Level 2 values in Planning's "All Departments" drop-down list. 1 indicates
Level 1 value while 2 indicates Level 2 value.

![](../../resources/images/it%20planning_images/itp-ssr-l1-l2-dimension-2_700x502.png)

Figure 2: Level 1 and Level 2 dimensions can be found in Apptio BI visualization configuration,
under "Add Dimensions" drop-down list.

SEE ALSO:

- [Use
  Planning data in Apptio BI](https://community.apptio.com/docs/DOC-13547 "(Opens in a new tab or window)")
- [Planning
  data exposed to Apptio BI](https://community.apptio.com/docs/DOC-13513 "(Opens in a new tab or window)")

## Stay informed about product updates

To be notified when this page is updated, click the Actions (gear) menu in
the upper right corner of this screen, and then click Follow. A link to the
updated topic will appear in your [Apptio Community Inbox](https://community.apptio.com/inbox "(Opens in a new tab or window)"). You can also see all historical product release
details; see Planning and Financial Management: [What's New
(Cumulative) and Upcoming Releases](https://community.apptio.com/docs/DOC-1302 "(Opens in a new tab or window)").

MORE RESOURCES:

- See also [Planning Weekly Maintenance
  Schedule](https://community.ibm.com/community/user/viewdocument/maintenance-schedule-update?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Opens in a new tab or window)").
- See if Apptio Planning applications have any
  current known issues in [Apptio Known Issues](https://community.ibm.com/community/user/viewdocument/introducing-known-issues-it-planni?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Opens in a new tab or window)").
