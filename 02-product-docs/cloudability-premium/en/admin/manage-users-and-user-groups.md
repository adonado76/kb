---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Manage Users and User Groups"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
source_path: "admin/manage-users-and-user-groups.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Manage Users and User Groups

In Cloudability, users and user groups help define who can access the platform and what they can
see or do. There are three key components:

A ***User***inCloudability is an individual who has been granted access to the platform. Each user
has a unique identity, typically linked to an email address. Users are created and authenticated
through **FrontDoor**, which handles both authentication and authorization. Once provisioned in
FrontDoor, the user can be assigned specific Cloudability roles such as MSP Admin, Billing Manager,
or Cloudability User/Admin. These roles determine the user's permissions and access levels within
the platform.

Learn more **[Manage Users, User Views
and Dashboards](create-and-manage-users.html)**

A ***User Group***in Cloudability is a set of users bundled together to simplify access management and view
assignment. Admins can create user groups and add individual users to them. Once created, these
groups can be assigned to specific Views to control visibility and access efficiently.

Learn more **[Manage User
Groups](manage-user-groups.html)**

An ***Entra ID Group***in Cloudability refers to user group managed within Microsoft Entra ID (formerly Azure Active
Directory), Microsoft's cloud-based identity and access management service. Instead of manually
creating user groups in Cloudability, organizations can import Entra ID Groups along with their
associated users.

Learn more **[Manage Entra ID
Groups](manage-entra-id-groups.html)**

- **[Manage Users, User Views and Dashboards](../admin/create-and-manage-users.html)**
- **[Manage User Groups](../admin/manage-user-groups.html)**
- **[Manage Entra ID Groups](../admin/manage-entra-id-groups.html)**
- **[Users and User Groups FAQs](../admin/users-and-user-groups-faqs.html)**
