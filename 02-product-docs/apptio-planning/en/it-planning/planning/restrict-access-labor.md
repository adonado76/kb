---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Restrict Access to Labor Salary Details"
breadcrumb:
  - "Planning"
  - "Labor Planning"
source_path: "it-planning/planning/restrict-access-labor.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Restrict Access to Labor Salary Details

The tasks below can only be performed by users assigned to the Admin role. See Frontdoor
permissions and roles.

Your organization may want to protect sensitive information, such as compensation rates. You can
block users from viewing the Labor tab (including labor salary details) by assigning a custom
role that disables the ViewLabor permission.

## Create a custom role that restricts access to the Labor tab

Create custom roles to provide unique permissions. For example, in Apptio Planning applications,
all built-in roles allow access to labor salary details (if present) on the Labor tab of the Line
Items view. An Admin can create a custom role that blocks access to the Labor tab and then assign
certain users to that role using the following instructions:

1. Enable the labor planning features. See [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").
2. On the Apptio Planning menu, click the Settings
   button (![settings icon](../../resources/images/it%20planning_images/icon_gear.png)), then click **Access
   Administration**.
3. Select Roles.
4. Verify that the custom role does not currently exist. You can view permissions and details for
   roles by clicking View in the Actions column for that role.
5. Select the Budget Process Owner role to use as a template to create the new, custom role.
   In the Actions column for that role, click Clone.
6. Enter a name and description for the role (for example, BPO without access to Labor).
7. In the Permission column, clear the ViewLabor permission. Note that restricting access to
   the Labor tab does not affect other permissions and capabilities in Apptio Planning
   applications.
8. Click Next, then click Save.
9. On the main menu, click Applications. If the visibility of any application has been
   modified and the new, custom role applies to that application, you need to add the new custom role
   to that application visibility.
10. Use the instructions in Modify user roles to assign users to the new, custom role.

The next time the user logs into an Apptio Planning application, access
to the Labor tab will be restricted. For more information on the **Access
Administration**
service, see About Frontdoor, the Apptio Access Administration
console.

## Adjust labor summary options

Labor-related financial line items appear in the Expenses table. These are summarized to
Cost Centers and Accounts, which may provide salary details. In addition to limiting access to the
Labor tab, you can prevent users from discerning salary details by adjusting how the labor-generated
financial values get summarized.

1. On the Component menu, select Planning. See [Navigate in Apptio Planning applications](navigate-apptio-planning.html "This topic provides an overview of how the Apptio Planning navigation is organized. The menu items shown in your account depend on your user permissions."). > Expenses.
2. In the Summary tab, select Actions > Labor Summary Options.
3. Select the data dimensions and attributes to summarize for labor-related financial data.
   Selecting more dimensions and attributes results in more granular labor data; selecting fewer
   options results in less granular labor data.
