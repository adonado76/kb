---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Users and User Groups FAQs"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
  - "Manage Users and User Groups"
source_path: "admin/users-and-user-groups-faqs.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Users and User Groups FAQs

## Are Entra ID and IDP synonymous?

Entra ID is one of the most widely used IDP (Identity Provider). There are many other IDPs such
as Okta, PingIdentify. At present, we’re only supporting Microsoft Entra ID (aka Azure AD).

## Which role in Cloudability can access the features?

The feature is accessible with existing permission ‘UserManagementFeatureFullAccess’
itself. So if an user had access to ‘User Management’ feature earlier, they'll also have access
to User Groups and Entra ID Groups features.

## How many User Groups or Entra ID Groups can be created in Cloudability?

There is no limit on how many User Groups or Entra ID Groups can be created.

## Is there a limit to how long a user group name can be?

Yes, group names in Cloudability can be up to 63 characters long. This limit aligns with the
character limit for Entra ID groups in Microsoft Entra ID.

## How much time it takes for changes to take effect when assigning Views to Groups?

Changes would be almost immediate. The users who get access to View via Groups would be able to
see the views almost immediately.

## Will changes done at Entra ID side automatically reflect in Cloudability?

The changes done on Entra ID side will not flow to Cloudability automatically. Cloudability
Admins would need to manually sync using the ‘Sync Entra ID Groups’ button.

## How much time it takes to Synchronize the Entra ID Groups?

It may take from few milliseconds to a few minutes based on the number of groups being synced and
the number of users in each group. If sync process is taking longer, you’ll need to wait. You can
always come back and verify the “Last Synced” Date field to know if Sync was completed.

## What happens if a user who is member of Entra ID Group doesn’t exist in Cloudability?

While Syncing, Cloudability performs a check whether the Entra ID group's users exist in
Cloudabilty or not. If a user doesn’t exist in Cloudability, it won’t be imported. So, if you had 10
users in an Entra ID Group and only 8 existed in Cloudability then only 8 users will be
imported.

Note: Bringing non-cloudability users is not useful as they cannot login to Cloudability
anyway.

## When synchronizing Entra ID group(s), why are some users not being imported into Cloudability?

This typically happens when users in Entra ID (Azure AD) do not have a valid email address
configured **or** if the configured email does not match the user's email in Cloudability. Even
if the user exists in the group, Cloudability will only import users whose email addresses are both
present and matches with those in the Cloudability. Please check the email id of user is not
missing, empty or mis-configured in Entra ID.

## Can a user be part of multiple User Groups?

Yes, users can be part of multiple Groups, in both Entra ID groups and Manual User Groups.

## Can we use these Groups with HVs (Hierarchical Views)?

Yes. Both User Groups and Entra ID Groups will be available with HVs as well.

## What is the roadmap for supporting User Groups and Entra ID Groups for sharing Reports, Dashboard, Alerts etc?

Support for **User Groups** and **Entrap ID Groups** is planned but not yet available
across all features. Currently, these groups cannot be used for sharing or alerting in the areas
listed below:

1. Sharing Report and Dashboards: Currently it only has option to share across Entire Organization
   or Users.
2. Sharing Container Dashboards: Currently it only has option to share across Entire Organization
   or Users
3. Creating Alerts for Anomaly detection
4. Sharing Workload Plans
5. Creating Alerts for CFP Plan

The above capabilities are on the roadmap and we are actively working to expand group-based
sharing and alerting across these features. Updates will be communicated as functionality becomes
available.

## Are these Groups supported in Apptio BI?

No, User Groups and Entrap ID Groups are not supported in Apptio BI. Not to mention that
Cloudability Reports and Dashboard will honor the Views access based on these Groups.

**Parent topic:** [Manage Users and User Groups](../admin/manage-users-and-user-groups.html)
