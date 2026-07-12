---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Manage Entra ID Groups"
breadcrumb:
  - "Administration"
  - "Manage Users and User Groups"
  - "Manage Entra ID Groups"
source_path: "SSVCLNQ/admin/manage-entra-id-groups.html"
images:
  - "03-media/apptio-cloudability-standard/manage-entra-id-groups_image1.png"
  - "03-media/apptio-cloudability-standard/manage-entra-id-groups_image2.png"
  - "03-media/apptio-cloudability-standard/manage-entra-id-groups_image3.png"
  - "03-media/apptio-cloudability-standard/manage-entra-id-groups_image4.png"
  - "03-media/apptio-cloudability-standard/manage-entra-id-groups-auto-sync1.png"
  - "03-media/apptio-cloudability-standard/manage-entra-id-groups-auto-sync2.png"
  - "03-media/apptio-cloudability-standard/manage-entra-id-groups_image5.png"
  - "03-media/apptio-cloudability-standard/View-assignment-visibility-for-Entra-ID-Groups.png"
  - "03-media/apptio-cloudability-standard/Picture14.png"
  - "03-media/apptio-cloudability-standard/Picture15.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Manage Entra ID Groups

## Overview

The Entra ID Groups integration allows Cloudability Admins to manage user access by syncing user group information directly from Microsoft Entra ID (formerly Azure Active Directory). Instead of manually creating and maintaining user groups within Cloudability, you can import existing Entra ID groups and assign them to Views for controlled access.

This feature streamlines permission management by aligning Cloudability access controls with your organization's Entra ID Groups. Any updates to group membership in Entra ID (e.g., when users join or leave teams) are automatically reflected in Cloudability during sync - ensuring consistent, up-to-date access without manual intervention.

## How to

Prerequisites

- You are a Cloudability Administrator.
- You have completed credentialing of Microsoft Entra ID tenant. To learn more, visit Connect Microsoft Entra ID

## Import Entra ID Groups into Cloudability

Entra ID Groups cannot be created manually in Cloudability and they must be imported or synced from your Entra ID tenant. To import:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Click Sync Entra ID Groups button.
1. In the dialog that appears, enter the criteria (Scope and the text filter basis which Cloudability will import the Entra ID Groups) and click Next .
1. Click Sync Now to begin importing. This action pulls in all Entra ID Groups from the credentialed tenant that match your specified criteria. Note: Entra ID Groups are read-only : These groups or it’s users cannot be modified within Cloudability. While you can delete an imported Entra ID group from Cloudability, you cannot modify the group name or its users. Import Criteria : You can use different sync criteria to import Entra ID groups into Cloudability Sync Duration : Syncing may take a few seconds to a few minutes depending on the number of groups and users being imported. Sync Behavior : An existing group will be overwritten during the sync. Any addition or removal of users from Entra ID would get synced. If a group has been deleted in Entra ID , it will not be automatically removed from Cloudability. You must delete it manually. Only one group can be deleted at a time. Rationale for Sync Behavior : Cloudability cannot distinguish if a group is missing due to deletion in Entra ID or due to a change in sync criteria. A group might still be associated with active View assignments. Automatically deleting such a group could unintentionally revoke access for multiple users.
1. Click a group eye icon to check the list of users belonging to the group.

## Setup Auto-Sync for Entra ID Groups

Changes to Entra ID groups happen continuously, which can make it difficult to keep Entra ID groups in Cloudability fully up to date through manual syncing. To eliminate this manual effort, Cloudability allows you to configure an automatic sync schedule.

You can set up a daily, weekly, or monthly auto-sync using specific filter criteria. Entra ID Groups will then be automatically synced based on the configured schedule.

To set up auto-sync for Entra ID Groups:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Click on the Pencil (Edit) Icon next to Auto Sync.
1. To enable auto-sync, turn on the Enable auto sync toggle.
1. In the Auto Sync Configuration modal: Review or update the filter criteria. Select the sync frequency ( Daily , Weekly , or Monthly ). Choose the sync time and timezone .
1. Click Save to enable the auto-sync schedule.
1. To disable auto-sync at any time, turn off the Enable auto sync toggle and Save.

## Delete Entra ID Groups in Cloudability

If a group was deleted on the Entra ID side, it will not be automatically deleted in Cloudability - you must delete it manually.

To delete an Entra ID Group:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Find the group you want to delete.
1. Click the ellipsis (…) icon and select 'Delete' menu option.

## View assignment visibility for Entra ID Groups

If an Entra ID Group was used in View assignment, the system blocked it's deletion. Admins can see a read-only list of all Views where a group is assigned. The list displays the View names and clearly indicates when a group is not used in any View, helping streamline group cleanup and reduce manual effort.

To identify which Views are using the Entra ID Group.:

1. Navigate to Settings > Users & Groups > Entra ID Groups tab.
1. Views column shows the number of Views where this Entra ID Group is assigned.
1. Find the group you want to validate.
1. Click the ellipsis (…) icon and select 'Views' from the menu.
1. In side panel, you'll see the list of views where this Entra ID Group is assigned.

![View assiged to a Entra ID Group](../images/View-assignment-visibility-for-Entra-ID-Groups.png)

## Assign View Access to Entra ID Groups

To assign view's access to an Entra ID Group or multiple Entra ID Groups:

1. Navigate to Organize > Views and create or edit a View. Click Permissions > Select ‘ Users & Groups ’ and Shared With dropdown. Assign View to the imported Entra ID groups from the drop down. Save this to assign the View to all users within the Entra ID Group(s).
1. Optionally, add a combination of User Groups, Entra ID Groups and individual Users to the View.
1. If a view was originally created as Private or Org level view, View Admin can change it to a shared with Users & Groups by selecting “Users & Groups” option view and assign the Users, User Groups and/or Entra ID groups.
