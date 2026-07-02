---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Create and Manage Views"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
source_path: "admin/create-and-manage-views.html"
images:
  - "images/Add-View-new.png"
  - "images/create_and_manage_views_4.jpg"
  - "images/manage-view.jpg"
  - "images/specified-dimensions.png"
  - "images/view_clone_duplicate.png"
  - "images/views_show_default_usage.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Create and Manage Views

## Overview

View in Cloudability is a powerful data filtering tool to organize and control how cloud cost and
usage data is presented and shared among Cloudability users for your organization. They act as
application-wide filters that help you focus on the data that matters most.

With Views, you can:

- Filter and Segment data by accounts, vendors, tags, account groups, or business mappings.
- Control visibility by sharing some data broadly while restricting sensitive information to
  specific users or groups.
- Enable flexibility by allowing admins to create multiple views, such as cost data by business
  unit or environment.

Administrators can configure Views with different sharing settings—Private, Entire Organization,
or Specific Users/Groups—to ensure the right level of data access to right set of users. Each View
provides a tailored perspective on your cloud resources, empowering teams to analyze costs, optimize
usage, and make informed decisions.

**Example Use Cases:**

- A finance team needs a View to monitor **monthly spend by vendor** across all accounts.
- A business unit leader needs a View to track **cost allocation by department**.
- A DevOps team need to have a View to analyze **compute costs in production vs. staging
  environments**.

## How to

## Create a view

1. Navigate to  Organize > Views  .
2. Select  New View  . The  Add a view  panel opens.

   ![add views screenshot](../../../../03-media/cloudability-premium/images/Add-View-new.png)
3. In the  Name  field, enter a name for your view.
4. In the Description field, describe the purpose for your view.
5. In the  Privacy  section, indicate your privacy settings.

   - Select  Private  to prevent others from accessing your view.
   - Select Entire Organization  to make your view accessible to all
     non-restricted users and administrators in your organization.
   - Select the Individuals to share your view with specific users. Use the
     Shared With dropdown to select specific users to share the View with.

   Note:

   When users are assigned a view, they can not see any data until they have the 
   ViewsFeatureFullAccess  permission. For more information, visit  [Managing user permissions and roles](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Opens in a new tab or window)")
6. In the  Filters  section, select the  Add Filter  button to
   narrow the scope of your view.

   1. In the  Measure  field, select the dimension you want to include in your filter
      argument.
   2. In the  Operator  field, select the operator for the filter, for example  equals
       .
   3. In the  Value  field, type a string of text to use as the value to filter
      on.
   4. Select  Submit  .
   5. For example, this filter limits the scope of the view to the Business Unit called 
      engineering  .

   ![filter views screenshot](../../../../03-media/cloudability-premium/images/create_and_manage_views_4.jpg)
7. (Optional) If you want to include another filter in your view, select  Add Filter
    again. When entering multiple filter arguments in a single view, the system will infer
   an implied OR between the same dimension and an implied AND across two dissimilar dimensions.

## Duplicate a View

As a **View Admin**, you often need to create multiple
views that share similar filters and permissions. Manually recreating each view by applying the same
filters and settings can be time-consuming and repetitive. With the **Duplicate View**
feature,

- You can clone or duplicate a view in just one click.
- All filters, permissions, and settings will be copied.
- You simply rename the view and make any adjustments needed.

This feature helps you save time, reduce errors and making it easier to customize and
organize Views for your teams.

1. To duplicate, navigate to  Organize > Views  .
2. Click the ellipsis (…) icon on the row of the view you want to clone/duplicate and select
   Duplicate.
3. This will open a side panel with all the data prefilled with the information. Simply rename the
   view and make any adjustments in filter conditions and permissions as needed.

![Clone duplicate a view](../../../../03-media/cloudability-premium/images/view_clone_duplicate.png)

## Manage an existing view

You can edit, share, and delete existing views in Cloudability.

Edit a view

1. Navigate to  Organize > Views  .
2. Click the ellipsis (…) icon on the row of the view you want to edit and select
   Edit.
3. If you want to edit multiple views at once, select the check boxes to the left of the views,
   then select the  EDIT MULTIPLE  icon. The  Edit a view  panel will open.

## Delete a View

When a View is deleted, the following behavior applies for users who have it set as their default
view:

- If a default view (including an HV) is deleted, the user’s default will automatically revert to
  the **Org-level default view**.
- If no org-level default exists, the default view will be set to **blank**.
- A **warning** now appears when deleting a view to inform admins that it may impact user
  defaults.

Before deleting, Admins can see who is using a specific view as their default via: **View → Show
Default Usage**. Also, Users can always update their default view at any time via: **Manage
Profile → Preferences**.

**To Delete a View:**

1. Navigate to  Organize > Views  .
2. Click the ellipsis (…) icon on the row of the view you want to delete and select
   Delete.
3. If you want to delete multiple views at once, select the check boxes to the left of the views,
   then select the Delete Views icon.

## Change privacy permissions of an existing shared view

Views authors can change the permissions (increase or decrease) of an existing Shared View.
However, when permissions are decreased or removed, the following behavior applies:

- If a default view's (including an HV) access is removed from the user, user’s default will
  automatically revert to the **Org-level default view**.
- If no org-level default exists, the default view will be set to **blank**.
- A **warning** now appears when modifying its permissions to inform admins that it may impact
  user defaults.

Before modifying the permissions, Admins can see who is using a specific view as their default
via: **View → Show Default Usage**. Also, Users can always update their default view at any time
via: **Manage Profile → Preferences**.

To change the permission:

1. Navigate to Organize > Views.
2. Click the ellipsis (…) icon on the row of the view you want to edit.
3. Change the permission between ‘Private’, ‘Entire Organization’ and ‘Individuals’.

## Identify Users using the View as Default

Before deleting or restricting access to a view, Admins can now see who is actively using it as
their default view, helping them make informed decisions when restricting view permissions or
deleting it. The feature shows exactly which users rely on a specific view as their default -
whether it was shared directly, through User Groups, Entra ID Groups, or with the Entire
Organization.

1. Using 'Show Default Usage' option:
   1. Navigate to Organize > Views.
   2. Click the ellipsis (…) icon on the row of the view and select 'Show Default Usage'.
   3. In side panel, you'll see the list of users who're using this view as their default view.![show default view users](../../../../03-media/cloudability-premium/images/views_show_default_usage.png)
2. Using CSV Export:
   1. Navigate to Organize > Views.
   2. Use the 'Export' button to download the list of all the views.
   3. In the CSV, the **View Default Users** column lists all users who have set that view as their
      default.

## Set a Default View

Your default view is the view you see when you initially log in, and it also applies to your
daily Cloudability emails. To set your default view:

1. Click on your Profile icon on the top right, then click  Manage Profile 
   .
2. On your  Profile  page, click the  Preferences 
   tab.
3. Under  Default Account View , select a view.

   Note: You can also select
   Hierarchical View (HV) as your default view. Only HVs to which a user has access to will appear in
   the drop down list and only the highest level node, can be set a default.

   Note: Cloudability
   remembers the last view you accessed and saves it in your browser cache. On your next login, it
   restores that same view instead of your default one. If you clear your browser cache and log in
   again, Cloudability will load your default view.

   ![set default views screenshot](../../../../03-media/cloudability-premium/images/manage-view.jpg)
4. Click  Save Settings .

## Select a View

Selecting a view narrows the scope of the data you see throughout Cloudability according to the
filter conditions of your view. To select an existing view:

1. Click the  Current View  drop-down in the top navigation.
2. Choose a view from the list.

Cloudability will now display data based on the filters configured in the selected view.

![Dropdown list displaying dimensions specified in your view](../../../../03-media/cloudability-premium/images/specified-dimensions.png)

Note:

 The **'Showing all data'** option is available only to users with the **Admin** role.
Non-admin users can only access views that have been assigned to them.

## Frequently Asked Questions

**Q1: Why do new users see multiple Views even though no specific access was granted?**

If a View Admin has shared Views with the “Entire Organization” permission, those Views become
accessible to all users by default, including newly added users.

**Q2: How does bulk editing (Edit Multiple) work for Views? (with examples)**

You can select multiple Views and use Edit Multiple to update their permissions in bulk. Filters
cannot be bulk edited because each View has its own unique filters. When bulk editing, the combined
permissions of all selected Views are displayed.

Examples:

- *Example 1:* If View A is Private and View B is shared with the Entire Organization, the
  bulk edit screen will show Entire Organization as selected. Any changes you make will apply to both
  Views.
- *Example 2:* If View A is shared with users *u1, u2* and group *g1*, and View B
  with *u2, u3*, the bulk edit screen will show *u1, u2, u3* and *g1* selected. Saving
  will apply these combined permissions to both Views.

Important: If you only want to add one new user to multiple Views, bulk edit may not be ideal.
For example, adding *u4* to both Views using bulk edit will also merge all existing
permissions, resulting in both Views having *u1, u2, u3, u4* and *g1*.

**Best Practice Tip: When to use bulk edit vs. individual edits**

Use **Edit Multiple** only when you want to standardize permissions across multiple Views. If
your goal is to make small, specific changes (like adding a single user), edit each View
individually to avoid unintentionally merging permissions.

**Q3: Why don't I see duplicate view option for Hierarchical Views?**

Duplicating or Closing feature is not available for Hierarchical Views. This is because each
Hierarchical View A Hierarchical View is built from a Hierarchical Business Mapping. To create a new
Hierarchical View group, a new Hierarchical Business Mapping needs to be added first. This limits us
from duplicating the Hierarchical View.

**Q4: Why isn’t my default view selected when I log in to Cloudability?**

Cloudability remembers the last view you accessed and saves it in your browser cache. On your
next login, it restores that same view instead of your default one. If you clear your browser cache
and log in again, Cloudability will load your default view.

**Q5: What happens when Admin deletes a View or removes a permission of view from a user?**

A user can expect following behavior when Admin deletes a View or removes a View's permissions
from an user:

1. The user’s default will automatically revert to the Org-level default view.
2. If no org-level default exists, the default view will be set to blank.
3. Users can always update their default view at any time via: Manage Profile → Preferences.

## Troubleshooting

- Can't see any data under a View? Ensure you have the ViewsFeatureFullAccess permission.

## Best Practices

- Use consistent naming conventions for Views (e.g., BU\_Prod\_Cost) to make them easy to
  identify.
- Provide a clear description for each View to explain its purpose and intended use.
- Limit “Entire Organization” sharing to essential Views only. Overusing this option can reduce
  the effectiveness of Views by making too many accessible to everyone.
- Regularly review and clean up unused Views to maintain an organized and efficient
  environment.

- **[Organize Views using Hierarchical Views](../admin/hierarchical-views.html)**
- **[Views Feature Compatibility](../admin/views-feature-compatibility.html)**
