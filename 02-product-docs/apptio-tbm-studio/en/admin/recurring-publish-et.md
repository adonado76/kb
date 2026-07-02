---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Recurring publish of transform table"
breadcrumb: []
source_path: "admin/recurring-publish-et.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recurring publish of transform table

Applies to: 12.11.7 and later. The Recurring Publish option allows the TBMA to
schedule auto recurring publishing schedules for editable tables that have transform tables. Once
this feature is enabled, the 'Publish to period' option is converted to default schedule, and it
will be attached in the Editable Table pipeline, under Transform Table. All the
'Publish to period' will be converted to default schedule on Recurring Schedule page, and the
Transform linked to the schedule will be available on Transform Table page.

## Enable Recurring Publish for Transform Tables

Note: Before enabling the feature, you must set the Recurring Schedule under Promotion Options,
otherwise the 'Publish' on reporting surface will always publish to current period.

To enable this option, navigate to Project tab > Enable Features, and then select
the Enable Recurring Publish for Transform Tables .

A confirmation message appears as shown.

A new option Recurring Publish will appear on the TBM Studio > Builds
tab.

Note: If Recurring Publish option is enabled, the Promotion Options > **Recurring
Updates for Editable Tables** button will be disabled.

From the Build tab, select Recurring Publish option. The Recurring Publish page appears
with two tabs.

## Transform Table

This is a read-only page that lists all transform tables sourced from an editable table.

It has the following information:

| Fields | Description |
| --- | --- |
| Table name | Name of the transform table. |
| Folder | Location of the transform table. |
| Editable table | Name of the editable table. |
| Schedule Name | Name given while creating the recurring schedule. |
| Recurrence | The recurrence type - hourly, daily, weekly, or monthly. |
| Publish to Period | The publish to period selected while creating the recurring schedule - values are current month, previous month, specific period, or no recurring update. |
| Enabled | If the recurring schedule was enabled or not - values are Yes or No. |
| Last Publish Date & Time | The timestamp of last publish in <mon dd, yyyy> <hh:mm> <AM/PM>< timezone> format.  If no recurring schedule is chosen, the value in NA  If the recurring schedule is yet to start, the value is Initial. |
| Next Publish Date & Time | The timestamp of the next publish in <mon dd, yyyy> <hh:mm> <AM/PM>< timezone> format.  If no recurring schedule is chosen, the value in NA  If the recurring schedule is yet to start, the value is Initial. |

## Recurring Schedules

This page has the list of all the default and available schedules.

It allows the TBMA to add, remove, or edit schedules. Addition of duplicate schedules will not be
allowed.

## Adding a Schedule

From Recurring Schedules tab, select Add Schedule. The Recurring Updates for Editable
Tables popup appears as shown:

Enter data in the following fields

| Fields | Description |
| --- | --- |
| Name | Enter a name for the recurring publish schedule |
| Publish Period | Select one of the values from the dropdown  Current Period - as is  Previous Period - as is  Specific Period - as is, ability to manually select the desired period |
| Recurrence | Repeat: Select Hourly (default), Daily, Weekly, or Monthly every <frequency of repetitions> hour/days/month.  Start time: Enter the <hh:mm> <AM/PM> and select UTC/GMT < timezone> |
| Add new Start time | This button appears for Daily, Weekly, and Monthly recurrence.  Click the button to add Repeat and Start time values as mentioned above. You can click this button 23 times (to repeat the start time for every hour) after which the button will be disabled.  Click the x icon to delete any start time |
| Repeat On | This field appears for Weekly recurrence. Select the days on which you want the recurrence to work. |
| Enable | Select this checkbox to enable, disable, or temporarily suspend the schedule. |

Select Save. A confirmation message appears and the schedule is added to the list.

- 'Default' is the initial, system generated value that appears when the feature is enabled.
- The 'Default - No Reoccurring Update' schedule does not have any reoccurring update, and it
  cannot be edited or deleted.
- All the schedules in this page will appear in Editable Table pipeline step of Transform
  Table.

## Editing Schedules

The TBMA can edit or delete the schedule by selecting the appropriate icon. On selecting
Save, a confirmation message appears as "*New Schedule is saved for editable table updates.
There might be few Transforms checked-out. Please check-in Transforms.*"

Note: The default
schedules are established using legacy configurations found in "Promotion Options > Recurring
Updates for Editable Tables" and "Publish to Period" of transform tables source to editable
tables.

## Migrating existing configurations to new recurring publish

Follow the mentioned steps if you want to enable the feature to migrate existing
configurations.

Note: Before you enable the Recurring Publish feature, ensure all the transforms off
editable tables are checked in, or changes are reverted. Do not proceed if transform tables are
checked out.

1. From the Project tab, select Enable Features and then select **Enable Recurring
   Publish for Transform Table** checkbox.

   If there are multiple tables, wait 10-15 minutes while
   the system checks and changes each transform
2. Expand the Tables section in Project Explorer, filter by Using > Editable
   to view that all transform tables have been checked out
3. From the Build tab, select the Recurring Publish feature.
4. Select the Transform Table tab to verify that the tables are listed.
5. Select the Recurring Schedule tab to view the “default” schedules that are based on the
   existing configuration.
6. Create new schedules, as desired, based on your unique editable table use cases.
7. Change each transform table from the “default” previous schedule to a new schedule, if
   desired.

Enabling the Recurring Publish feature will migrate only one project at a time. If there are more
than one projects with editable tables, these steps must be repeated for each project. It is
important to specifically, unselect then re-select the **Enable Recurring Publish for Transform
Table** under Enable Features
