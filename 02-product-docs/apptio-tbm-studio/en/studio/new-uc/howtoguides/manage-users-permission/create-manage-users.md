---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create and Manage Users"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "User Management"
source_path: "studio/new-uc/howtoguides/manage-users-permission/create-manage-users.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create and Manage Users

**Objective:** Create new user accounts and manage existing users in TBM Studio.

**When to use:** When onboarding new team members, updating user information, or
managing user lifecycle (activate/deactivate accounts).

**Time estimate:** 5-10 minutes per user

**Prerequisites**

- You must have the Admin role or a custom role with user management permissions.
- Access to Enhanced Access Administration (Frontdoor).
- The user's email address (used as login ID), full name, and intended role.

## Steps to Create a New User

1. **Access Enhanced Access Administration.** From TBM Studio, click the **Project**
   tab and select **Control Access to Apptio Applications**. This opens the Enhanced Access
   Administration interface.
2. **Navigate to Users.** In Enhanced Access Administration, locate the **Users**
   section in the navigation menu.
3. **Click Add User** (or equivalent option) to create a new user account.
4. **Enter user details:**
   - **Email:** The user's email address. This becomes their login username.
   - **Full Name:** The user's first and last name as it appears in the system.
   - **Password:** Set an initial password (the user can change this later) or configure
     SSO.
5. **Assign initial role(s).** Select the appropriate role(s) from the available roles
   list. See *Assign Roles to Users* below for detailed guidance.
6. **Save the user.** Click **Save** or **Create** to complete the user's
   creation.

## Expected Results

The new user appears in the Users list. The user can now log in with their email address
and password. Their access level is determined by the assigned role(s).

## Managing Existing Users

You can modify user accounts at any time through Enhanced Access Administration:

- **Edit user properties:** Update name, email, or other profile information.
- **Change role assignments:** Add or remove roles as responsibilities change.
- **Reset passwords:** Reset a user password if they are locked out.
- **Deactivate accounts:** Disable user accounts when employees leave or no longer need
  access.

Warning: Deactivating a user does not delete their historical data or audit trail.
If you need to completely remove a user for compliance reasons, contact Apptio
Support.

## Common Pitfalls

- **Email format:** Ensure email addresses are correctly formatted. Users cannot log in
  if their email is entered incorrectly.
- **Domain mismatch:** Users must be created in the correct domain to access the intended
  projects.
- **Missing role assignment:** Users without any role assignment cannot access TBM
  Studio. Always assign at least one role.

**Parent topic:** [User Management](../../../../studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html)
