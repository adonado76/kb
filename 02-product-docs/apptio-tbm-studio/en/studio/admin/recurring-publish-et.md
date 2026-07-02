---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Recurring publish of transform table"
breadcrumb: []
source_path: "studio/admin/recurring-publish-et.html"
images:
  - "resources/images/studio_images/12118-recsched.png"
  - "resources/images/studio_images/12118-transformtable.png"
  - "resources/images/studio_images/ap-1.jpg"
  - "resources/images/studio_images/ap-2.jpg"
  - "resources/images/studio_images/ap1.jpg"
  - "resources/images/studio_images/auto-promote-1.jpg"
  - "resources/images/studio_images/ef-recpub.jpg"
  - "resources/images/studio_images/en-feat.png"
  - "resources/images/studio_images/erp-1.png"
  - "resources/images/studio_images/rec-pub.png"
  - "resources/images/studio_images/rp-1.png"
  - "resources/images/studio_images/rp-main.png"
  - "resources/images/studio_images/rp-warning.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recurring publish of transform table

**Applies to**: 12.11.7 and later. The Recurring Publish option allows the TBMA to
schedule auto recurring publishing schedules for editable tables that have transform tables. Once
this feature is enabled, the 'Publish to period' option is converted to default schedule, and it
will be attached in the **Editable Table** pipeline, under **Transform Table**. All the
'Publish to period' will be converted to default schedule on Recurring Schedule page, and the
Transform linked to the schedule will be available on **Transform Table** page.

## Enable Recurring Publish for Transform Tables

Note: Before enabling the feature, you must set the Recurring Schedule under Promotion Options,
otherwise the 'Publish' on reporting surface will always publish to current period.

To enable this option in 12.11.7,, navigate to **Project** tab >
**Enable Features**, and then select the **Enable Recurring Publish for
Transform Tables** .

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/en-feat.png)

A confirmation message appears as shown.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rp-warning.png)

The Recurring Publish tab is enabled on the TBM Studio > Builds tab.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rec-pub.png)

Note: If **Recurring Publish** option is enabled, the **Promotion Options** > **Recurring
Updates for Editable Tables** button will be disabled.

From the Build tab, select **Recurring Publish** option. The Recurring Publish page appears
with two tabs.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rp-main.png)

## Transform Table

This is a read-only page that lists all transform tables sourced from an editable table.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/12118-transformtable.png)

It has the following information:

| Fields | Description |
| --- | --- |
| Table name | Name of the transform table. |
| Folder | Location of the transform table. |
| Editable table | Name of the editable table. In 12.11.8, the value is a hyperlink, clicking on which will open the linked editable table. |
| Schedule Name | Name given while creating the recurring schedule. |
| Recurrence | The recurrence type - hourly, daily, weekly, or monthly. |
| Publish to Period | The publish to period selected while creating the recurring schedule - values are First Period of the Current Fiscal Year, First Period of the Next Fiscal Year, First Period of the Project, current month, previous month, specific period, and no recurring update. |
| Enabled | If the recurring schedule was enabled or not - values are Yes or No. |
| Last Publish Date & Time | The timestamp of last publish in <mon dd, yyyy> <hh:mm> <AM/PM>< timezone> format.  If no recurring schedule is chosen, the value in NA  If the recurring schedule is yet to start, the value is Initial. |
| Next Publish Date & Time | The timestamp of the next publish in <mon dd, yyyy> <hh:mm> <AM/PM>< timezone> format.  If no recurring schedule is chosen, the value in NA  If the recurring schedule is yet to start, the value is Initial. |

## Recurring Schedules

This page has the list of all the default and available schedules.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rp-1.png)

It allows the TBMA to add, remove, or edit schedules. Addition of duplicate schedules will not be
allowed.

## Adding a Schedule

From Recurring Schedules tab, select **Add Schedule**. The Recurring Updates for Editable
Tables popup appears as shown:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/auto-promote-1.jpg)

Enter data in the following fields

| Fields | Description |
| --- | --- |
| Name | Enter a name for the recurring publish schedule |
| Publish Period | Select one of the values from the dropdown  First Period of the Current Fiscal Year (available in 12.11.8)First Period of the Next Fiscal Year (available in 12.11.8)  First Period of the Project (available in 12.11.8)  Current Period - as is  Previous Period - as is  Specific Period - as is, ability to manually select the desired period |
| Recurrence | **Repeat**: Select Hourly (default), Daily, Weekly, or Monthly **every** <frequency of repetitions> hour/days/month.  **Start time**: Enter the <hh:mm> <AM/PM> and select **UTC/GMT** < timezone> |
| Add new Start time | This button appears for Daily, Weekly, and Monthly recurrence.  Click the button to add **Repeat** and **Start time** values as mentioned above. You can click this button 23 times (to repeat the start time for every hour) after which the button will be disabled.  Click the x icon to delete any start time |
| Repeat On | This field appears for **Weekly** recurrence. Select the days on which you want the recurrence to work. |
| Enable | Select this checkbox to enable, disable, or temporarily suspend the schedule. |
| Auto Promote to Production | Applies to 12.11.10 and later. Select this checkbox to auto promote the recurring schedule to production. |

Select **Save**. A confirmation message appears and the schedule is added to the list.

- 'Default' is the initial, system generated value that appears when the feature is enabled.
- The 'Default - No Reoccurring Update' schedule does not have any reoccurring update, and it
  cannot be edited or deleted.
- All the schedules in this page will appear in Editable Table pipeline step of Transform
  Table.

## Editing Schedules

The TBMA can edit or delete the schedule by selecting the appropriate icon. On selecting
**Save**, a confirmation message appears as "*New Schedule is saved for editable table updates.
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

1. From the **Project** tab, select **Enable Features** and then select **Enable Recurring
   Publish for Transform Table** checkbox.

   If there are multiple tables, wait 10-15 minutes while
   the system checks and changes each transform
2. Expand the **Tables** section in Project Explorer, filter by **Using** > **Editable**
   to view that all transform tables have been checked out
3. From the **Build** tab, select the **Recurring Publish** feature.
4. Select the **Transform Table** tab to verify that the tables are listed.
5. Select the **Recurring Schedule** tab to view the “default” schedules that are based on the
   existing configuration.
6. Create new schedules, as desired, based on your unique editable table use cases.
7. Change each transform table from the “default” previous schedule to a new schedule, if
   desired.

Enabling the Recurring Publish feature will migrate only one project at a time. If there are more
than one projects with editable tables, these steps must be repeated for each project. It is
important to specifically, unselect then re-select the **Enable Recurring Publish for Transform
Table** under Enable Features

## 12.11.8 and later

The following enhancements are applicable from 12.11.8 and later.

- Enable this feature from **Project Settings** and then select **Enable Recurring Publish**
  checkbox.

  Note: If you are migrating from version 12.11.7 to 12.11.8, you must manually activate
  this feature from the Project Settings screen, as it will not be enabled by default. There will be
  no loss of configuration; schedules and transformations will remain intact and visible upon
  enabling.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/erp-1.png)
- Three more options are added to the "Publish To Period", namely "First Period of the Current
  Fiscal Year", "First Period of the Next Fiscal Year" and "First Period of the Project".
  - First Period of the Current Fiscal Year: This is the Starting Month of Fiscal Year set on
    Project Time Setting screen associated with the current year. Example: If the Starting Month of
    Fiscal Year is March, then the First Period of the Current Fiscal Year would be Mar:FY2024.
  - First Period of the Next Fiscal Year : This is same as First Period of the Current Fiscal Year,
    except that the year will change. Example: Mar:FY2025.
  - First Period of the Project: 'Start of Project' set on Project Time Setting screen will be the
    value for First Period of the Project. Example: If the setting is Apr FY2024, then First Period of
    the Project should be Apr:FY2024.
- Two new columns are added to the Recurring Schedule screen: "Run Now" and "Description."
- The "Run Now" feature allows Admins to run schedules instantly rather than waiting for the
  scheduled time.
- The "Description" column lets you add meaningful descriptions for each schedule.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/12118-recsched.png)

## 12.11.10 and later

A new column Auto Promote to Production is added to the Recurring Schedule tab. To see this
column, do the following:

1. Navigate to **Enable Features,** and select **Enable Auto-promote For Editable Table
   Recurring Schedules** option.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ef-recpub.jpg)
2. The **Auto Promote to Production** checkbox appears in the Recurring Updates for Editable
   Table popup.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ap-1.jpg)
3. On selecting this checkbox, warning message appears. The **Email Recipients** text box will
   appear, to add email ids of those you want to notify of the auto promotion.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ap1.jpg)

   Note: If the checkbox is not selected, the
   value of Auto Promote to production in the Recurring Schedules tab will be No.
4. The **Auto Promote to Production** column also appears in the Recurring Schedules tab.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ap-2.jpg)
