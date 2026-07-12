---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Manage User Groups"
breadcrumb:
  - "Administration"
  - "Manage Users and User Groups"
  - "Manage User Groups"
source_path: "SSVCLNQ/admin/manage-user-groups.html"
images:
  - "03-media/apptio-cloudability-standard/Picture3.png"
  - "03-media/apptio-cloudability-standard/Picture4.png"
  - "03-media/apptio-cloudability-standard/Picture5.png"
  - "03-media/apptio-cloudability-standard/Picture6.png"
  - "03-media/apptio-cloudability-standard/View-assignment-visibility-for-User-Groups.png"
  - "03-media/apptio-cloudability-standard/Picture7.png"
  - "03-media/apptio-cloudability-standard/Picture8.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Manage User Groups

## Overview

A User Group in Cloudability is a logical collection of users created to simplify access management and streamline assignment of Views.

By organizing users into groups, admins can more easily apply consistent settings, control view access, and maintain governance across your FinOps practice.

## How to

Prerequisites

- You are a Cloudability Administrator.

## Create a User Group in Cloudability

To create a User Group:

1. Navigate to Settings > Users & Groups > User Groups tab.
1. To create a new user group, click ‘ New User Group ’. You can create multiple user groups at once by separating the names by commas.
1. Click Edit Users and add users to the User Group from the list of users.
1. Click Save .

## Delete a User Group in Cloudability

To delete a User Group:

1. Navigate to Settings > Users & Groups > User Groups tab.
1. Find the group you want to delete.
1. Click the ellipsis (…) icon and select 'Delete' menu option.

![ user gropus error screenshot ](../images/Picture6.png)

## View assignment visibility for User Groups

If a User Group was used in View assignment, the system blocked it's deletion. Admins can see a read-only list of all Views where a group is assigned. The list displays the View names and clearly indicates when a group is not used in any View, helping streamline group cleanup and reduce manual effort.

To identify which Views are using the User Group.:

1. Navigate to Settings > Users & Groups > User Groups tab.
1. Views column shows the number of Views where this User Group is assigned.
1. Find the group you want to validate.
1. Click the ellipsis (…) icon and select 'Show views' from the menu.
1. In side panel, you'll see the list of views where this User Group is assigned.

![View assiged to a User Group](../images/View-assignment-visibility-for-User-Groups.png)

## Assign View Access to User Groups

To assign view's access to a User Group or multiple User Groups:

1. Navigate to Organize > Views and create or edit a View. Select the users and groups option and a value from the Shared With dropdown. Assign View to group(s) from the dropdown (under category ‘User Groups’). Click Save to assign the View to all users within the User Group(s).
1. Optionally, add a combination of User groups, Entra ID Groups and individual users to the View.
1. If a view was originally created as Private or Org level view, View Admin can change it to a shared with Users & Groups by selecting “Users & Groups” option view and assign the Users, User Groups and/or Entra ID groups.
