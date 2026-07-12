---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Control access to reports through role-based permissions"
breadcrumb: []
source_path: "reports/control-access-reports-11755.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Control access to reports through role-based permissions

Applies to: Apptio TBM Studio 12.7 and later.

Report permissions allow the administrator to control end-user access to reports by setting
permissions to reports by role. See [Working with user roles and permissions in Apptio Studio](https://community.apptio.com/docs/DOC-1391 "(Opens in a new tab or window)").
Before the TBM Studio 12.7 release, setting individual report permissions could cause the system to
create extra copies of reports per role. This approach was difficult to maintain. In TBM Studio12.7
and later, setting permissions no longer creates role-specific child reports. You can now configure
permissions at the Report Collections level. See [Create and manage report collections](creating-report-collections.htm "(Opens in a new tab or window)"), in addition to the report
level.

To get the most out of using report permissions, consider the following:

- Existing report permissions will continue to work - If users have set role-based
  permissions in reports set before 12.7, these legacy permissions will continue to work in 12.7 but
  may be difficult to modify.
- "Access Denied" page - Previously, when users did not have permission to see a report,
  they would see a report page with only a blank report component. Users found this confusing. In TBM
  Studio 12.7 and later, the system assesses a user's role when they attempt to access the report.
  Users without sufficient permission will see the Access Denied screen.
- Report permissions aren't applied while in TBM Studio - This can help administrators test
  permissions before checking them. Testing helps ensure permissions' accuracy and that users don't
  configure permissions in a way that locks all users out of a given report view.
- Report Permissions are project-level settings - This means users won't have to check out
  permissions to set them, but the permissions must be checked in and the instance calculated before
  without sufficient permission would see the Access Denied screen.
- Report Filter by Role - In TBM Studio, users have an option to filter the list of reports
  in the project by role. Doing so shows which reports have specific permissions set for that role. To
  do so:
- Select the report filter. Then, select Roles. This displays a list of all roles in the
  instance.
- Select a role from the list to have the report list display only the reports with permissions
  specifically set for that role.NOTICE

  Reports with permissions set to "Everyone" (all OOTB
  reports until customized) will not appear in these filtered lists.

  ![](../../resources/images/studio_images/studioimages/studio_reports_search.png)

## Set permissions

You can set report permissions by role at either the report or report-collection level.

## Set report collection permissions

1. In TBM Studio, on the Project tab, in the Project Data group, select **Report
   Collections**.
2. In the Manage Report Collections dialog box, select the report collection that will have
   its permissions modified.
3. Under Viewable By, select Selected Roles, and in the drop-down list that appears,
   select which roles will have access to this report collection.
4. Once permissions have been set, close the dialog and check in the updates. Permissions changes
   will appear in the Check In dialog as the name of the report collection where permissions were
   modified.

After each environment has calculated, for example, Development and then Staging, other users
will be able to see the permissions applied in the calculated environment. Like other project
settings, these settings will need to be promoted to Production.

## Set individual report permissions

1. To set permissions for one report, first check out that report. Then, on the Report tab,
   in the Advanced group, select Permissions.
2. In the Change Permissions dialog box, under Viewable By, select **Selected
   Roles**, and in the drop-down list that appears, select which roles will have access to this
   report.
3. Once the roles have been set, save the permissions and check in the updates. Permissions changes
   will appear in the Check In dialog box as the name of the report where permissions were
   modified.

After each environment has calculated, for example Development and then Staging, other users will
be able to see the permissions applied in the calculated environment. Like other project settings,
these settings will need to be promoted to Production.

## Permissions best practices

With the permissions abilities introduced in TBM Studio 12.7, it is easier for users to modify
report-level permissions without all the issues that were created when users used permissions before
12.7. Use the following tips to get the most out of these abilities:

- When setting new permissions, start with Report Collections when possible - When updating
  permissions, do as much as possible at the Report Collection level before making changes to
  individual reports. This will help to ensure that changes made to report-level permissions don't
  conflict with the permissions for the entire collection.
- Make notes when checking in work - The standard description that will appear in the
  Check-in History for updates to report permissions will only contain the name of the collection or
  report for which permissions have been updated. Capturing more descriptive notes when checking in
  work can help with troubleshooting later.
- Populate the Support email address - This email address can be especially helpful when a
  user tries to access a report they don't have permissions to access. While this isn't as necessary
  in smaller organizations, the number of users can grow quickly in size, so it's helpful to have this
  value set so new users can channel their questions through a single email address. To do so:
  1. On the Project tab, in the Domain group, click Domain Settings.
  2. In the Tenant Settings dialog box, Support email field, add your TBMO's email
     address. TIP - If you want to revert the Access Denied screen back to its original content
     with no email address, replace the custom email address above with [support@apptio.com](mailto:support@apptio.com "(Opens in a new tab or window)").
- Watch out for conflict warnings - If you set permissions that could conflict with
  permissions set at a higher level (collections) or at a lower level (reports), be sure to watch for
  the permissions conflict warnings that have been added to the report- and report-collection-level
  dialog boxes.NOTICE

  Due to the way this conflict is detected, this warning will appear only
  after role-based permissions for a report have been set, checked in, and the instance has finished
  calculating.
- Report-level view with conflicts at collection level - Shows permissions already being
  narrowed down for the collection that contains the report.
- Collection-level view with conflicts in underlying reports - Shows that the permissions
  set for the report collection conflict with the permissions set on the App Portfolio report.
- Testing and validation suggestions - Many customers use secure sign-on (SSO), which can
  make testing this new functionality difficult. Below are some suggestions to help users:
  - Since report permissions aren't applied in TBM Studio, any administrator can modify permissions
    for a report in TBM Studio and then navigate out of TBM Studio and back to the application (for
    example, to Costing Standard) where permissions are enforced. If the administrator doesn't have the
    appropriate permissions to view a report, they will see the Access Denied screen when not in TBM
    Studio.
  - When testing many roles, it can be helpful to coordinate a small group of end users who are
    willing to test by clicking around reports after an administrator has modified report permissions
    (and possibly user roles if testing many roles).

## Work with prior permissions

As mentioned above, if you have reports that have been configured to use report permissions
before 12.7, then those permissions will continue to work. However, at some point, a new requirement
or role will come in that needs to be added to one of the role-customized reports. In this case,
refer to the [Report Access
Control Migration Guide](migratereportaccesscontrol.htm "(Opens in a new tab or window)").

## FAQ

**Q: If I have customized reports using permissions prior to 12.7, will I still be able to use
these reports?**

A: Yes. Upgrading to 12.7 doesn't change how you navigate to and access role-customized reports.
It provides a cleaner experience for any new permissions that need to be applied going forward.

**Q: Do I have to make any changes to my instance to start using the new permissions
functionality when I upgrade to 12.7?**

A: No. Old report permissions will continue to work in parallel with the new functionality, so
you can decide when you want to start using the new functionality.

Q: How can I see which reports have set permissions for my role?

A: In Project Explorer, you can apply a filter by role to the Reports list to see all reports
that have permissions set for a given role.

Q: Why is my role list missing custom roles?

A: This is usually due to Enhanced Access Administration not being configured correctly, causing
the instance to not properly connect to Enhanced Access Administration where the full list of custom
roles is maintained.

**Q: Which Check-In History record captures the permissions I applied to a given report
collection in case I need to roll back?**

A: If you did not add notes to qualify when a report collection was modified, it can be difficult
to tell what was checked in as a part of a given record. Check-In History only contains the name of
the report or report collection after the records have been expanded.
