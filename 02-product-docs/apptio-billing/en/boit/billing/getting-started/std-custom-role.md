---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Overview and roles"
breadcrumb:
  - "Billing"
  - "Getting started"
  - "User Roles and Permissions"
source_path: "boit/billing/getting-started/std-custom-role.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Overview and roles

User roles and permissions control who can see and work with Benchmarking. A Role is a
collection of permissions that is assigned to a user, and no one can access an IBM Apptio
product without at least one Role on their account, which is managed in Access Administration.
In Access Administration, authorized Admins create and manage user registrations, assign or
remove Roles, and control which Roles can access each product endpoint, which endpoints are open
to any eligible Role, and which endpoints are hidden entirely.

For details on how to assign roles, manage user accounts, and access to IBM Apptio products,
see the documentation for [Access Administration](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas "(Opens in a new tab or window)").

## User Roles

Highlighted below are some of the roles which have access to Billing:

- **Admin**
  - Full access to all features in Billing (including Costing and TBM Studio).
  - Includes administrative access to Frontdoor and ability to create custom roles.
- **Apptio Partner**
  - Close to same level of access as an Admin, but cannot register, deactivate, or
    delete user accounts for a customer unless granted separate role with appropriate
    permissions.
  - Role can only be assigned/unassigned by IBM Support.
- **Business Consumer**
  - **Notice: Applies to Billing Standard only.**
  - Grants access to reports in the “Service Charges” report collection and the
    “Business Owner” group appearing on the home report.
- **Business Owner**
  - **Notice: Applies to Billing Standard only.**
  - Grants access to reports in the “Service Charges” and “Business Relationship
    Management” report collections and the “Business Owner” and “Business Relationship
    Manager” groups appearing on the home report.
- **Service Manager**
  - **Notice: Applies to Billing Standard only.**
  - Grants access to reports in the “Service Charges” and “IT Service Provider” report
    collections and the “Business Owner” and “Service Provider” groups appearing on the
    home report.

For Billing Essentials, Standard roles granted access to a Costing Essentials project with
Billing Essentials components installed will have access to all reports in the “Billing”
report collection.

Periodically review Access Administration (in Frontdoor) and Billing’s report collections
to identify other Roles given access to Billing content.

## Custom Roles

You can create custom roles in Frontdoor. Custom roles allow you to tailor access to meet
your organization’s specific needs.
