---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Manage Entra ID Groups"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
  - "Manage Users and User Groups"
source_path: "admin/manage-entra-id-groups.html"
images:
  - "images/Picture14.png"
  - "images/Picture15.png"
  - "images/View-assignment-visibility-for-Entra-ID-Groups.png"
  - "images/manage-entra-id-groups-auto-sync1.png"
  - "images/manage-entra-id-groups-auto-sync2.png"
  - "images/manage-entra-id-groups_image1.png"
  - "images/manage-entra-id-groups_image2.png"
  - "images/manage-entra-id-groups_image3.png"
  - "images/manage-entra-id-groups_image4.png"
  - "images/manage-entra-id-groups_image5.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Manage Entra ID Groups

## Overview

The **Entra ID Groups integration** allows Cloudability Admins to manage user access by
syncing user group information directly from Microsoft Entra ID (formerly Azure Active Directory).
Instead of manually creating and maintaining user groups within Cloudability, you can import
existing Entra ID groups and assign them to Views for controlled access.

This feature streamlines permission management by aligning Cloudability access controls with your
organization's Entra ID Groups. Any updates to group membership in Entra ID (e.g., when users join
or leave teams) are automatically reflected in Cloudability during sync - ensuring consistent,
up-to-date access without manual intervention.

Note: Entra ID has nothing to do with SSO.

## How to

**Prerequisites**

Before you start, ensure:

- You are a Cloudability Administrator.
- You have completed credentialing of Microsoft Entra ID tenant. To learn more, visit [Connect Microsoft Entra ID](connect-microsoft-entra-ID.html)

## Import Entra ID Groups into Cloudability

Entra ID Groups cannot be created manually in Cloudability and they must be imported or synced
from your Entra ID tenant. To import:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
2. Click Sync Entra ID Groups button.

   ![sync entra id screenshot](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image1.png)
3. In the dialog that appears, enter the criteria (Scope and the text filter basis which
   Cloudability will import the Entra ID Groups) and click **Next**.

   ![enter sync criteria screenshot](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image2.png)
4. Click **Sync Now** to begin importing.

   ![sync now screenshot](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image3.png)

   This action pulls in all Entra ID Groups from the credentialed tenant that match your
   specified criteria.

   Note:
   - Entra ID Groups are read-only: These groups or it’s users cannot be
     modified within Cloudability.
   - While you can delete an imported Entra ID group from Cloudability, you cannot modify the group
     name or its users.
   - Import Criteria: You can use different sync criteria to import Entra ID
     groups into Cloudability
   - Sync Duration: Syncing may take a few seconds to a few minutes depending
     on the number of groups and users being imported.
   - Sync Behavior:
     - An existing group will be overwritten during the sync. Any addition or
       removal of users from Entra ID would get synced.
     - If a group has been deleted in Entra ID, it will
       not be automatically removed from Cloudability. You must delete it
       manually.
     - Only one group can be deleted at a time.
   - Rationale for Sync Behavior:
     - Cloudability cannot distinguish if a group is missing due to deletion in Entra ID or due to a
       change in sync criteria.
     - A group might still be associated with active View assignments. Automatically deleting such a
       group could unintentionally revoke access for multiple users.
5. Click a group eye icon to check the list of users belonging to the group.

   ![eye icon screenshot](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image4.png)

## Setup Auto-Sync for Entra ID Groups

Changes to Entra ID groups happen continuously, which can make it difficult to keep Entra ID
groups in Cloudability fully up to date through manual syncing. To eliminate this manual effort,
Cloudability allows you to configure an automatic sync schedule.

You can set up a **daily, weekly, or monthly auto-sync** using specific filter criteria. Entra
ID Groups will then be automatically synced based on the configured schedule.

To set up auto-sync for Entra ID Groups:

1. Navigate to Settings > Users & Groups  > Entra ID
   Groups tab.
2. Click on the **Pencil (Edit)** Icon next to Auto Sync.

   ![](../../../../03-media/cloudability-premium/images/manage-entra-id-groups-auto-sync1.png)
3. To enable auto-sync, turn on the **Enable auto sync** toggle.
4. In the **Auto Sync Configuration** modal:
   1. Review or update the filter criteria.
   2. Select the sync frequency (**Daily**, **Weekly**, or **Monthly**).
   3. Choose the sync time and **timezone**.![](../../../../03-media/cloudability-premium/images/manage-entra-id-groups-auto-sync2.png)
5. Click **Save** to enable the auto-sync schedule.
6. To disable auto-sync at any time, turn off the **Enable auto sync** toggle and Save.

## Delete Entra ID Groups in Cloudability

If a group was deleted on the Entra ID side, it will **not** be automatically deleted in
Cloudability - you must delete it manually.

To delete an Entra ID Group:

1. Navigate to Settings > Users & Groups  > Entra ID
   Groups tab.
2. Find the group you want to delete.
3. Click the ellipsis (…) icon and select 'Delete' menu option.

Note: Deletion of a group is prevented if it is currently assigned to any View. The following error
appears:

![deleting entar id groups](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image5.png)

## View assignment visibility for Entra ID Groups

If an Entra ID Group was used in
View assignment, the system blocked it's deletion. Admins can see a **read-only list of all
Views** where a group is assigned. The list displays the View names and clearly indicates when a
group is not used in any View, helping streamline group cleanup and reduce manual effort.

To
identify which Views are using the Entra ID Group.:

1. Navigate to Settings > Users & Groups  > Entra ID
   Groups tab.
2. Views column shows the number of Views where this Entra ID Group is assigned.
3. Find the group you want to validate.
4. Click the ellipsis (…) icon and select 'Views' from the menu.
5. In side panel, you'll see the list of views where this Entra ID Group is assigned.

![View assiged to a Entra ID Group](../../../../03-media/cloudability-premium/images/View-assignment-visibility-for-Entra-ID-Groups.png)

## Assign View Access to Entra ID Groups

To assign view's access to an Entra ID Group or multiple Entra ID Groups:

1. Navigate to Organize > Views and create or edit a View. Click
   Permissions > Select ‘Users & Groups’ and
   Shared With dropdown. Assign View to the imported Entra ID groups from the
   drop down.

   ![assigning views screenshot](../../../../03-media/cloudability-premium/images/Picture14.png)

   Save this to assign the View to all
   users within the Entra ID Group(s).
2. Optionally, add a combination of User Groups, Entra ID Groups and individual Users
   to the View.

   ![edit views screenshot](../../../../03-media/cloudability-premium/images/Picture15.png)
3. If a view was originally created as **Private** or **Org** level view, View Admin can
   change it to a shared with Users & Groups by selecting **“Users & Groups”** option view
   and assign the Users, User Groups and/or Entra ID groups.

**Parent topic:** [Manage Users and User Groups](../admin/manage-users-and-user-groups.html)
