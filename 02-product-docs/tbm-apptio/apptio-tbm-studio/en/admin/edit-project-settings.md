---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Edit project settings"
breadcrumb: []
source_path: "admin/edit-project-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Edit project settings

Applies to: TBM Studio 12.0 and later. Some settings are available in later
versions of TBM Studio, as noted below.

After creating a project, you can edit the project settings.

1. To display the ribbon on the Applications/Projects menu, click TBM
   Studio.
2. On the Project tab, in the Project Setup group,
   click Project Settings. The Edit Project Settings dialog box appears.

Note: The Login Message field was deprecated in TBM Studio 12.4.1. For more information, refer to
the [release notes](../release%20notes/12.4/18-04-13.html "(Opens in a new tab or window)").

The fields in the Edit Project Setting dialog are described below. Fields
that require the Apptio Admin role are marked with an asterisk (\*). If you are not assigned to the
Admin role, you will not see these fields.

![](../../resources/images/studio_images/3707-edit.jpg)

- Domain - The domain is the Apptio environment established for your
  organization. All projects are created in the same domain. This field cannot be edited.
- Name - The name of the project and build created for your organization.
  This field cannot be edited.
- Derived From - If the project was derived from an existing project, the
  name of the source project is displayed in this field.NOTICE

  In TBM Studio
  R12, you cannot create a new project from an existing project. If you upgrade from v11 to R12,
  derived projects will display the source project in this field, but you will not be able to change
  the derivation.
- Components Version - Specify which version to use for component upgrades.
  To learn more, see [Specify version for component upgrades](specify-version-component.html "(Opens in a new tab or window)").
- Color Spec - Enter a color formatting string to change the color of an
  entity on all charts. For more information, see [Set the default colors for project metrics](set-default-colors.htm "(Opens in a new tab or window)").
- Base Currency - If the project uses multi-currency, select the default
  currency that will be used to display values in reports. Users can override this setting by choosing
  a different currency for the reports they view. To learn more, see [Configure
  multi-currency](configure-multi-currency.html "(Opens in a new tab or window)").
- Enable Multi-Currency Service - Introduced in TBM Studio 12.10.5, this setting lets you turn on
  Multi-Currency Service for your project. Multi-Currency Service provides a centralized platform to
  manage currency exchange tables for your Apptio products.

  [What is
  Multi-Currency Service](../../multi-currency/gettingstarted/mcs-overview.htm "(Opens in a new tab or window)")

  Multi-Currency Service is automatically enabled for all new
  projects that use a Gregorian calendar. For the existing projects that use a Gregorian calendar, you
  can manually enable Multi-Currency Service by selecting this checkbox. Currently, Multi-Currency
  Service does not support projects that use 13-period or 454 variant calendars.

  Note: Be aware that
  once Multi-Currency Service is enabled from the Project Settings dialog, you cannot reverse it
  without a rollback.

  Once you enable Multi-Currency Service and check-in the project
  settings, the exchange tables are automatically synchronized to match the data stored in
  Multi-Currency Service tables. The base currency is also updated to match the data stored in
  Multi-Currency Service. After Multi-Currency Service is enabled, the currency exchange tables in the
  project are no longer editable from TBM Studio; you can only edit these tables from the
  Multi-Currency Service interface.

  [Currency exchange table synchronization](../../multi-currency/admin/currency-exchange-table-sync.htm "(Opens in a new tab or window)")
- Locale - Select a country. The selection determines the number, currency,
  and date formats used in the project for reports and metrics.
- Sorting Locale - This is used for localized projects to determine how to
  sort the data. Select a country. The current options are the United States and Japan. The sorting is
  case insensitive/ kana insensitive/ width insensitive and diacritic sensitive.
- **Deferred Refresh** - This is used to defer time for the users to select filters, pickers,
  or slicers and see the updated results based in the report. For more information, see [here](https://help.apptio.com/en-us/studio/reports/delayed-refresh.htm "(Opens in a new tab or window)").
- Legacy Date Parsing - This is needed for backward compatibility to make
  date parsing work the same way after upgrades. Enable the check in for the Legacy Date Parsing
  icon.
- Enable Apex UI - This setting was introduced in TBM Studio 12.11.0. This
  is used to enable or disable the look and feel of the UI to GWT. For more information, see [here](../getting%20started%20with%20tbm%20studio/apex-ui-uplift%E2%80%8B.htm "(Opens in a new tab or window)").
- **Enable Recurring Publish** - This option is introduced in TBM Studio 12.11.8. It allows the
  TBMA to publish the editable table data to their transform by configuring a schedule. For more
  information, see [Recurring Publish](recurring-publish-et.html "Applies to: 12.11.7 and later. The Recurring Publish option allows the TBMA to schedule auto recurring publishing schedules for editable tables that have transform tables. Once this feature is enabled, the 'Publish to period' option is converted to default schedule, and it will be attached in the Editable Table pipeline, under Transform Table. All the 'Publish to period' will be converted to default schedule on Recurring Schedule page, and the Transform linked to the schedule will be available on Transform Table page.").
- **Disable Data Flow in Enriched Transform** - This option stops the data of the raw table
  from automatically moving to Transform table, in the development environment, only if the table is
  checked out. for more information, see [Disable Data Flow](../data_studio/create-table-from-et.html).
- **Allow Editable Table Save With Validation Errors** - This option it allows you to save the
  rows on the report even if there is some validation error.
- Number Compaction - (This setting was introduced in TBM Studio 12.3. For
  more information, refer to the [release notes](../release%20notes/12.3/17-07-28.html "(Opens in a new tab or window)") . Some industries (such as the oil and gas industry) use
  thousands and millions of different financial notations (such as K, KK, or MM) that are not employed
  in other industries. This notation is used by KPIs. To customize compaction abbreviations, click
  Custom, and then enter the abbreviation values you want.
- Currency symbols - If the project uses multi-currency, select the
  currency display option you want. To learn more, see [Configure multi-currency](configure-multi-currency.html "(Opens in a new tab or window)").
- Default Page Size\*- Sets the default page size for reports when the
  reports are printed. This field is available only to the Apptio Admin role.
- Enable Application Tabs\*- This option does not apply in the current
  release of the product. The field is available only to the Apptio Admin role.
- Plugin - This field is available only to the Apptio Admin role.
- Default Metric - The default model metric is Cost. If you have other
  metrics defined, they will be available from the drop-down list.
- Budgeting Project\* - This field is available only to the Apptio Admin
  role. It controls the time shifting behavior for cross-project legacy IT Planning metrics. Checking
  this option greatly improves processing speed. If you use the IT Planning Wizard to create a
  project, this field is set automatically.
- Enable Early Access - When this option is checked, users can access
  features that still are under development. In general, you should not check this option.
- Auto-calculate workspaces\* - Determines the default setting of the Auto
  Calculate icon on the Home tab. When checked, Auto Calculate will be active
  when a user logs in to a project. When a user checks in a document, the application will update all
  the documents the user has checked out. When the option is cleared, the user can manually run
  updates using the other Update options: Update Document and Update Workspace. The user also can
  activate the Auto Calculate option by clicking the icon.

  ![](../../resources/images/studio_images/studio_auto_calculate.png)

  For projects with
  large databases that take a significant amount of time to calculate, we recommend that you clear the
  option and leave it up to the user to determine if they want to activate auto calculation.
- Enable Mandatory Check in Descriptions - (Applies to TBM Studio 12.7.1.
  and later) This option can force users to enter a description each time they check in work. When the
  box is checked for this option, users will be unable to click Check In until something is typed in
  the message box (shown above). Before a message is typed, the cursor will appear as a red
  crossed-out circle with a screentip: Please add a message to check in.

  ![](../../resources/images/studio_images/studioimages/studio_check%20in_check%20in_sui.png)
- Show (Blank) value in tables/slicers - (Applies to TBM Studio 12.7.1. and
  later). This option updates how tables and slicers display blank values in the same way that charts
  automatically fill in blank values with (Blank). By default, tables and slicers will not show a
  value if a field is empty, seen on the Unchecked side below. When this box is checked, the system
  will populate empty cells in tables and slicers with (Blank) as shown on the Checked side below.
  This makes it easier to filter and perform operations on fields with a blank value.

  ![](../../resources/images/studio_images/studioimages/studio_project%20settings_unchecked%20checked_sui.png)
- Show signed values for .Unassigned - The "Unassigned " column in the
  .Unassigned table remains the absolute value of allocated Costs, as that is needed to properly
  calculate the % assigned values.
- Use regular expressions in Lookup Wild - The regular expressions in
  columns using Lookup\_Wild return values helps to obtain desired granularity in vendor allocation
  mapping.
- Automatically handle !ALL\_ROWS - It automatically adds and removes allows
  where needed. That is, it removes the need to check the all rows box on perspectives.
- **Default report for Landing/Home page** - This is the default report that appears for the
  user in their Landing or Home page.
- **AUM Metric** - This is list of modeled metrics to use for Spend Under Management
  calculations. It is a system variable that can be used in the Ad Hoc Component Configuration panel
  for a Published Table.
- **AUM Modeled Object** - This is the list of modeled objects to use for Spend Under
  Management calculations. It is a system variable that can be used in the Ad Hoc Component
  Configuration panel for a Published Table.
- Catalog Artifact Channel - The catalog channel that needs to be selected
  is Stable.
