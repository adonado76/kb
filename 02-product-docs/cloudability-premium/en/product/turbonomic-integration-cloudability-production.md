---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Cloudability Onboarding New Turbonomic Instance"
breadcrumb:
  - "Cloudability Premium"
  - "Turbonomic Integration"
source_path: "product/turbonomic-integration-cloudability-production.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability Onboarding New Turbonomic Instance

## Overview

For a production environment, any configuration is done automatically with the help of PPO. The
only manual action required is to setup permissions for users in Frontdoor. This should be done by
the customer's Admin user.

This section will focus on the difference in configuration of user roles and scopes between non
Frontdoor Turbonomic instances and Frontdoor-enabled Turbonomic instances, as well as the
description of permissions themselves which are available in the production environment.

In a Cloudability Premium Turbonomic instance, users are created automatically during their
first login to Turbonomic , based on their configuration in Frontdoor. Frontdoor configuration is
used to set up user roles in Turbonomic (which are based on Frontdoor permissions), but there is no
way to configure Turbonomic scopes from Frontdoor . The initial user scope assignment only occurs
when the user has logged in for the first time (and the user account is automatically created in
Turbonomic). Of note, once the user account exists in Turbonomic , changing permissions in Frontdoor
will not affect this user’s scope. For more granular scoping to be configured, further steps from
the customer's administrator (within Turbonomic) will be required.

## Scopes in Turbonomic

Scopes in Turbonomic work similarly to Views in Cloudability, but its worthwhile noting that
they are not synchronized between Cloudability and Turbonomic, and need to be setup separately in
each application. This is the case only in the initial phase of integration between the two, where
the customer has direct access to the Turbonomic application. In later releases of our integration,
the customer will not be able to login into Turbonomic directly and will not be required to setup
those scopes - Cloudability will handle all the actions required to grant access to specified
resources for the user.

## Frontdoor Permissions

Here you can find a list of all permissions available in the production instance of Frontdoor,
that can be used for Turbonomic authorization.

| Permission Name | Description |
| --- | --- |
| ScopedAutomatorFullAccess | Users with this permission can use all Turbonomic features (including Plan, Park, and Place), but cannot configure the Turbonomic installation or create policies. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management view. |
| ScopedDeployerFullAccess | Users with this permission can view all Turbonomic charts and data, use Place to reserve workloads, and create placement policies and templates. However, users cannot run plans or execute any recommended actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management view. |
| ScopedAdvisorFullAccess | Users with this permission can view all Turbonomic charts and data, and run plans. However, users cannot use Place to reserve workloads, create policies, or execute any recommended actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management view. |
| ScopedObserverFullAccess | Users with this permission can view the environment, including the Home Page and Dashboards. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management view. |
| ScopedOperationalObserverFullAccess | Users with this permission can view the environment, including the Home Page, Dashboards, Groups, and Policies. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management view. |
| ScopedSharedAdvisorFullAccess | Users with this permission can view the Home Page and Dashboards, but only see VMs and Applications. Users cannot execute Turbonomic actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management view. |
| ScopedSharedObserverFullAccess | Users with this permission can view the Home Page and custom Dashboards, but only see VMs and Applications. Users cannot see Executive Dashboards or execute Turbonomic actions. A Turbonomic Site Administrator must set a scope for this user in the Turbonomic User Management view. |
| SiteAdminFullAccess | Users with this permission can use all Turbonomic features and modify site-specific settings to configure the Turbonomic installation. Users can also administer Groups, Policies, Workflows, Templates, Billing/ Costs, and Target Configuration, but not Email, Licenses, Updates, and Maintenance. Users with this role can set the scope on other accounts. |
| AutomatorFullAccess | Users with this permission can use all Turbonomic features (including Plan, Park, and Place), but cannot configure the Turbonomic installation or create policies. |
| DeployerFullAccess | Users with this permission can view all Turbonomic charts and data, use Place to reserve workloads, and create placement policies and templates. However, users cannot run plans or execute any recommended actions. |
| AdvisorFullAccess | Users with this permission can view all Turbonomic charts and data, and run plans. However, users cannot use Place to reserve workloads, create policies, or execute any recommended actions. |
| ObserverFullAccess | Users with this permission can view the environment, including the Home Page and Dashboards. |
| OperationalObserverFullAccess | Users with this permission can view the environment, including the Home Page, Dashboards, Groups, and Policies. |

The above Frontdoor role permissions directly correspond to Turbonomic's built in roles. For
example, a Frontdoor role permission of **ObserverFullAccess** will grant the **Observer**
role to users in Turbonomic. Note, most of the above listed permissions have two variants, and the
difference between them is based on whether the user will be assigned an empty scope (no access to
any resource), or with a full scope (access to all resources). Other than scopes, these two
permissions will grant the same role in Turbonomic (i.e. **ScopedObserverFullAccess** and
**ObserverFullAccess** will grant the **Observer** role to a user in Turbonomic). Note that
some permissions **do not** support scoping, as they grant access to all resources regardless
(i.e. **SiteAdminFullAccess**).

In the case where multiple permissions are applied to the same user in Frontdoor, Turbonomic
will chose a permission with the least amount of privileges.

## Applying scopes to users in Turbonomic

A user in Turbonomic is granted an appropriate role and scope during their first login (based on
the intial Frontdoor role permissions). It is worthwhile noting a user will not exist in Turbonomic
(before first logging in), and as such, cannot be pre-configured with a granular scope.

To apply full scopes to the user, follow the steps below.

1. An Administrator applies **ObserverFullAccess** role permission to the user in Frontdoor.
2. The user logs in to the Turbonomic instance for the first time – at this point a new user is
   created within Turbonomic automatically based on the role permission in Frontdoor.
3. The user can now access Turbonomic with **Observer** role and will be granted access to all
   resources.

To apply a limited scope to the user, follow the steps below.

1. An Administrator applies the **ScopedObserverFullAccess** role permission to the user in
   Frontdoor
2. The user logs into the Turbonomic instance for the first time – at this point a new user is
   created within Turbonomic automatically based on the role permission in Frontdoor
3. The user can now access Turbonomic with **Scoped Observer** role but has no access to any
   resources.
4. An Administrator logs into Turbonomic and sets up a scope for this user with respective access
   to resources.
5. When the user logs in again, the user will now be able to access Turbonomic with the **Scoped
   Observer** role and have an appropriate scope assigned to them.

## Updating User Roles in Turbonomic

In order to change a user role in Turbonomic , the Administrator needs to update assigned
permissions to that user in Frontdoor. On every login, Turbonomic will check the currently assigned
roles to the user in Frontdoor, and will update its configuration where needed. This process will
not affect scopes as scoping is only checked during first login into Turbonomic.

In the event roles are updated in Turbonomic directly, the Frontdoor configuration will override
the users role during their next login.

**NOTE**: When users are added to Turbonomic in Cloudability Premium, they are not automatically
removed when they are deprovisioned from Frontdoor. In the event this occurs (eg: during offboarding
a user), the user will need to be manually removed from Turbonomic. Its worthwhile noting from a
security perspective when a user is removed from Frontdoor, that user will no longer be able to
access Turbonomic (as access is controlled by Frontdoor).
