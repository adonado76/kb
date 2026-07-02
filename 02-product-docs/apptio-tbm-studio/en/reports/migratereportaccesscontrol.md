---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Migrate report access control"
breadcrumb: []
source_path: "reports/migratereportaccesscontrol.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Migrate report access control

◆ Applies to: TBM Studio 12.7 and later.

Prior to the Apptio TBM Studio 12.7 release, when users enabled role-based permissions for
reports, the system created an extra copy of the report for each role to which permissions were
granted. This article explains how to remove these extra reports when you want to start using the
improved permissions functionality available in TBM Studio 12.7 and later.

NOTES:

- Legacy functionality continues to work in TBM Studio 12.7. You do not need to remove reports
  before using the new permissions functionality. However, when configuration updates are made to a
  report that has legacy permissions, be sure to assess if you need to migrate the report to a version
  that's free of child reports.
- While not necessary, you can perform the steps described in this article in a branch as long as
  you follow the best practices outlined in [Branch projects](../admin/bp-branching-projects.htm "(Opens in a new tab or window)").

## Migrate reports

For all reports that you identify to migrate, capture the following information:

- Report Name.
- Report Collection (to help locate in Project Explorer).
- Which roles should have permission.
- Which role's copy of the report should be used to create the new report. If the answer is more
  than one report, then note all views and components that need to be retained or recreated at the end
  of the process.

Note: The following are instructions about how to check in reports and how to wait until the
calculation finishes before proceeding to the next step. Be sure to complete each step before you
move on to the next step. Otherwise, you may get unexpected results that could require a rollback or
other Support assistance.

1. In the Project Explorer, navigate to Reports, then check out the child report to use to
   create the new report (as identified in Before migrating reports above). This will cause the parent
   report and all children reports to appear to be checked out:

   ![](../../resources/images/studio_images/studioimages/studio_project%20explorer_reports_sui.png)
2. To create a copy of the report, first click the child report, then click Save As. Save it
   with the Copy of prefix that's automatically added. For example, Copy of <original name of
   report>, then click OK.

   ![](../../resources/images/studio_images/studioimages/reports/studio_reports_save_as.png)
3. Check in the new report and wait for the calculation to finish before proceeding.

   Note: After the calculation completes, the copy of the report might appear in a different report
   collection altogether.
4. Check out and remove permissions from the Copy of <original report>. On the Report
   tab, click Permissions, select Everyone, then click OK.

   ![](../../resources/images/studio_images/studioimages/reports/studio_reports_change_permissions.png)
5. Check in the report and wait for the calculation to finish.
6. Check out any *one* of the child reports attached to <Original Report>, then click
   Delete.
7. Check in the report and wait for the calculation to finish.

   Note: When working with OOTB reports, deleting one of the child reports causes the parent and the
   other child report(s) to disappear.
8. Check out the copy you created in the previous step. Create another copy of the Copy of
   <original report>, then rename the report to the <original Report> name. Finally, check in the
   report and wait for the calculation to finish.
9. After the calculation finishes, the original report displays:
   - In the original report collection
   - And with any additional child reports that were not explicitly deleted
10. To remove the rest of the child reports, perform the following steps, in this order, for each
    child report:
    - Check out the child report.
    - Delete.
    - Check In.
    - Wait for the calculation to finish after each check in before moving onto the next report.
    - Repeat this process until all child reports are deleted.

You now have the original report that does not have any child reports:

![](../../resources/images/studio_images/studioimages/studio_reports_auto%20calculate_sui.jpg)

## Revert to the Out-of-the-Box (OOTB) state

For OOTB reports that have intentionally been customized, you do not need to revert or set the
report back to the original version, so the migration process is finished. In this case, move on to
the following Customize migrated reports section.

If the end state you want for the report you plan to migrate must be set to the original version
of the report with no customizations, then complete the following additional migration steps. You
may need to do so because the end state you want for the report is the OOTB version, or you want to
see the latest version of the report before deciding which customizations to recreate. In this case,
follow these steps:

1. Make a customization to the report (for example, add a blank table component to the top of the
   report), then check in the changes.
2. Go to the components installation page for that report and revert the OOTB report.
3. When the calculation from the revert finishes, the report is restored to the original state
   without the customization made earlier.

## Customize migrated reports

When there is only one copy of the report with no child report copies, you can reapply any
permissions and customizations you need in the final copy of the migrated report.

For permissions only: To add permissions to the newly migrated report, see [Work with report
permissions](control-access-reports-11755.htm "(Opens in a new tab or window)").

For other customizations:

- If you identify that more than one report is needed to meet all the requirements, then determine
  the fewest number of reports you need to build to meet all the requirements.
- If role permissions are used to create reports for different roles where each role's report is
  then customized, one option is to use component visibility to help recreate a report where different
  roles have visibility to view different sets of components when you navigate to the same report. In
  this case, add one report group per role that contains the components that should be visible to that
  role. Each group is then configured to be visible to one role only, so that these groups can be
  layered on top of each other on the reporting surface. Doing so allows the user's role to determine
  which report group, and which components they see.

Note: If a user has two of the roles that groups are visible to, they will see the components for
the role that's on top of the stack of groups.
