---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Manage User Groups"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
  - "Manage Users and User Groups"
source_path: "admin/manage-user-groups.html"
images:
  - "images/Picture3.png"
  - "images/Picture4.png"
  - "images/Picture5.png"
  - "images/Picture6.png"
  - "images/Picture7.png"
  - "images/Picture8.png"
  - "images/View-assignment-visibility-for-User-Groups.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Manage User Groups

## Overview

A **User Group** in Cloudability is a logical collection of users created to simplify access
management and streamline assignment of Views.

By organizing users into groups, admins can more easily apply consistent settings, control view
access, and maintain governance across your FinOps practice.

## How to

**Prerequisites**

Before you start, ensure:

- You are a Cloudability Administrator.

## Create a User Group in Cloudability

To create a User Group:

1. Navigate to Settings > Users & Groups > User
   Groups tab.

   ![user groups screenshot ](../../../../03-media/cloudability-premium/images/Picture3.png)
2. To create a new user group, click ‘New User Group’. You can create
   multiple user groups at once by separating the names by commas.

   ![add user groups  screenshot ](../../../../03-media/cloudability-premium/images/Picture4.png)
3. Click Edit Users  and add users to the User Group from the list of
   users.

   ![edit user groups screenshot ](../../../../03-media/cloudability-premium/images/Picture5.png)
4. Click Save.

## Delete a User Group in Cloudability

To delete a User Group:

1. Navigate to Settings > Users & Groups  > User
   Groups tab.
2. Find the group you want to delete.
3. Click the ellipsis (…) icon and select 'Delete' menu option.

Note: Deletion of a group is prevented if it is currently assigned to any View. The following
error appears:

![ user gropus error screenshot ](../../../../03-media/cloudability-premium/images/Picture6.png)

## View assignment visibility for User Groups

If a User Group was used in View
assignment, the system blocked it's deletion. Admins can see a **read-only list of all Views**
where a group is assigned. The list displays the View names and clearly indicates when a group is
not used in any View, helping streamline group cleanup and reduce manual effort.

To identify
which Views are using the User Group.:

1. Navigate to Settings > Users & Groups  > User
   Groups tab.
2. Views column shows the number of Views where this User Group is assigned.
3. Find the group you want to validate.
4. Click the ellipsis (…) icon and select 'Show views' from the menu.
5. In side panel, you'll see the list of views where this User Group is assigned.

![View assiged to a User Group](../../../../03-media/cloudability-premium/images/View-assignment-visibility-for-User-Groups.png)

## Assign View Access to User Groups

To assign view's access to a User Group or multiple User Groups:

1. Navigate to Organize > Views and create or edit a View. Select the users
   and groups option and a value from the Shared With dropdown.

   Assign View
   to group(s) from the dropdown (under category ‘User Groups’).

   ![user groups view screenshot ](../../../../03-media/cloudability-premium/images/Picture7.png)

   Click
   Save  to assign the View to all users within the User Group(s).
2. Optionally, add a combination of User groups, Entra ID Groups and individual users
   to the View.

   ![user groups entra id screenshot](../../../../03-media/cloudability-premium/images/Picture8.png)
3. If a view was originally created as **Private** or **Org** level view, View Admin can
   change it to a shared with Users & Groups by selecting **“Users & Groups”** option view
   and assign the Users, User Groups and/or Entra ID groups.

**Parent topic:** [Manage Users and User Groups](../admin/manage-users-and-user-groups.html)
