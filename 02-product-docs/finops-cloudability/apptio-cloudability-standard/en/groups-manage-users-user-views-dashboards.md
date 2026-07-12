---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Manage Users, User Views and Dashboards"
breadcrumb:
  - "Administration"
  - "Manage Users and User Groups"
  - "Manage Users, User Views and Dashboards"
source_path: "SSVCLNQ/admin/create-and-manage-users.html"
images:
  - "03-media/apptio-cloudability-standard/pencil-icon.jpg"
  - "03-media/apptio-cloudability-standard/Manage-Users.png"
  - "03-media/apptio-cloudability-standard/add_and_manage_users_4.png"
  - "03-media/apptio-cloudability-standard/Picture2.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Manage Users, User Views and Dashboards

## Overview

As a Cloudability Admin, you can manage a user’s access to views and dashboards within Cloudability. This includes configuring their default view, setting a default dashboard, and granting access to specific views. Other user management tasks, such as adding or removing roles, are handled through Access Administration .

Roles and permissions in Cloudability

Learn how to manage user permissions and roles in Access Administration .

## Managing user views and dashboards

1. Navigate to Settings > Users & Groups > Users tab .
1. Select the check box next to the name of user you want to manage, then select .
1. You can also search for the user using either the user name or email.
1. To edit views and dashboards for multiple users, select at least two users, and then select Edit Multiple .
1. In the Edit a User pane that appears, you can configure the following settings for the user: Default View – Sets the view the user sees by default upon login Default Dashboard – Specifies the default dashboard assigned to the user View Access – Grants the user access to specific views. You can filter them based on all ‘Selected’, ‘Unselected’ and ‘All’ criteria. Note: Hierarchical views can only be assigned/unassigned via the Views Permission page. Note: When users are assigned a view, they can not see any data until they have the ViewsFeatureFullAccess permission. For more information, visit Managing user permissions and roles
1. Select Save .

## Setting a Default View for a New User

Cloudability allows you to configure a default view that new users see when they log in for the first time, as long as they’ve been granted access to that view. This default view is often referred to as the org-level default view .

If an admin hasn't set a default view for a user, or if the user hasn’t configured one in their profile ( Manage Profile > Preferences ), Cloudability will automatically default them to this org-level default view upon login.

To configure the default view, select a value from the New User Default View dropdown.
