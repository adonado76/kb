---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Create a report"
breadcrumb: []
source_path: "reports/create-a-report.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create a report

Applies to: TBM Studio 12.0 and later

You can create an unlimited number of reports. After creating a report, you can save it, rename
it, restrict dates, and delete the report. When you create a report, a tab is displayed at the
bottom of the workspace. To create a report, switch to TBM Studio, click the
Home tab, click New, and then click
Report.

Watch these videos from Apptio Education Services:

- [Create a
  New Report](https://community.apptio.com/videos/1439 "(Opens in a new tab or window)")
- [Build a
  Unit Rate Report](https://community.apptio.com/videos/1894 "(Opens in a new tab or window)")

Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## How roles affect report creation

Your options for creating reports are controlled by your role and the permissions assigned to
that role. There is an Edit Personal Reports permission that, if assigned to
your role, will let you create personal reports that only you can view. This permission is by
default assigned to the Analyst role but can be assigned to any role. Check
with your Apptio administrator to see if you have been assigned to a role that has this
permission.

## Create a report

1. Switch to TBM TBM Studio.
2. Click the Home tab, click New, and then click
   Report. Note that the items displayed in the dialog will depend on your role
   permissions.![](../../resources/images/studio_images/studioimages/reports/rep339.png)
3. Enter a name for the report.NOTICE

   If you will be exporting reports to
   Excel, be aware that Excel limits sheet names to 31 characters. If a report name is greater than the
   character limit, Excel truncates the name and places "-0" at the end.
4. Enter a description of the report.The description will be displayed in the **Report Finder**,
   so it is important that you enter a description that will be useful to an end user that is viewing
   and printing reports.
5. If you are creating the report one or more levels down in the report hierarchy, and you want the
   report to be created at the top level, check the Create as Top Level Report
   option.
6. Select who can view the report.If you create reports that only you can view, the **Viewable
   By** options will not be displayed in the dialog.
7. Select the layout for the report and whether or not you want a heading added to the report
   (Add Heading checkbox at the right).

   After you create the report, you can
   change the layout and choose to display or not display the heading.
8. Choose the size of screen that will be used to layout the report.
   - Standard: 1024 pixels wide
   - Widescreen: 1440 pixels wide
9. For certain reports, an Advanced option will be displayed in the dialog
   that lets you choose when the report will be displayed by selecting options from the drop-down
   lists. The lists available will depend on the parent report and whether the report data was
   filtered. A breakdown report is one in which a user drills down from one object report to another.

   |  |  |  |
   | --- | --- | --- |
   | Type of report | Option | Description |
   | Non-breakdown | Even when showing a breakdown | Displays the report even if the data being fed to the report is breakdown data. |
   | Only when not showing a breakdown | Displays the report only if the data being fed to the report is not breakdown data. |
   | Breakdown | Even when not showing a breakdown | Displays the report even if the data being fed to the report is not breakdown data. |
   | Only when showing a breakdown | Displays the report only if the data being fed to the report is breakdown data. |
   | Filtered | Only when filtered like this | This option is available for filtered reports only. It displays the same report but only if the filtering is the same. The filtering is the same if filters have been defined for the same columns in the source tables. |
   | Even if filtered some other way | This option is available for filtered reports only. It displays the same report (even if different sets of filters have been defined). |
   | Unit | For All Units | This option is available for unit reports only. It applies the report to all units in the unit identifier column. |
   | For *unit* only | This option is available for unit reports only. It applies the report to only the unit specified in the filter. |
10. To save the report and close the dialog, click OK.

After creating a report, you can add tables, charts, and formatting and navigation
components.

## Creating and applying color palettes

You can create and manage color palettes for a report. To know more, see [Custom Color Palette](../admin/color-enhancement.htm "(Opens in a new tab or window)").

## Save a report

When you first create a report, the application automatically saves the report. If you make
changes to a report and then navigate away, the report is automatically saved.

When you make a change to a report, an asterisk (\*) is displayed in front of the report name on
the Report tab at the bottom of the report edit workspace. The asterisk is a reminder that you need
to save the report.

To save a report, click the Save icon ![](../../resources/images/studio_images/studioimages/icons/save.png) on the
Home tab.

## Save a report with a new name

To make a copy of the report and save it to a new report name:

1. Open the menu under the Save icon and click Save
   As.The Save As dialog is displayed as shown in the following
   image:![](../../resources/images/studio_images/studioimages/studio/stu514.png)
2. Enter a name and description for the report.
3. If you are creating the report one or more levels down in the report hierarchy, and you want the
   report to be created at the top level, check the Create as Top Level Report
   option.
4. Select who can view the report.If you create reports that only you can view, the **Viewable
   By** options will not be displayed in the dialog.
5. To save the report and close the dialog, click OK.

## Delete a report

1. In the Project Explorer, click the name of the report that you want to
   delete.
2. On Home tab, click Delete.
3. Save the report.
4. Check in the report.

## Restrict dates for a report

By default, reports are visible during all dates in a project. However, you can restrict the
dates when a report is visible by setting the Earliest Applicable Date
option. This can be useful if you are building a report and want to hide it until it is ready for
users to view.

To set the earliest applicable date:

1. Click the report in the Project Explorer.
2. Check out the report.
3. On the Report tab, click the Start Date icon. The
   **Configure Earliest Applicable Date** dialog is displayed as shown in the following image:![](../../resources/images/studio_images/studioimages/reports/rep126.png)
4. Click the calendar icon at the end of the As of field and select a
   date.

   When you set an earliest date, and a user tries to view the report before that date, the
   application displays a message explaining that the report is not yet viewable. The user is given the
   opportunity to click a link that takes them to the first viewable period.

## Preload a report

The data displayed in some reports can take a long time to calculate. In most cases, you will
want to ensure the data for a report has been preloaded before users access the report. To do this,
check the Active option in the Advanced group on the
Report tab.

If your domain has been configured to prevent users from viewing reports that have not been
preloaded, a message will be displayed that tells users that they cannot view the report because it
has not been preloaded.

## Master a report

If you want to use the report as a master template for other reports, click the **Master
Report** option. For more information about using master reports, see [Work with master reports](master-reports.htm "(Opens in a new tab or window)").
