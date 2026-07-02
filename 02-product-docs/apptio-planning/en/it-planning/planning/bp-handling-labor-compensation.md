---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Best practices: Labor compensation rates"
breadcrumb: []
source_path: "it-planning/planning/bp-handling-labor-compensation.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Best practices: Labor compensation rates

The information below addresses common considerations for handling labor compensation
rates in Apptio Planning applications. This information is especially relevant to executive sponsors
and related stakeholders before labor compensation rate details are recorded in Apptio Planning
applications.

## Strategies for labor compensation rate values

Labor compensation rates are recorded in the Labor reference data table. For implementation
details, see [Manage Labor
reference data](manage-labor-configuration.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles."). Before recording labor compensation rates, Apptio recommends your
organization to adopt a standard approach. The following are common labor compensation rate
strategies to consider.

## Midpoint values

This strategy uses the middle of the established salary range when tying salaries to labor. For
example, if the salary range was $56,000 to $94,000, the midpoint would be $75,000.

- Advantage - Hides salary information from view while providing a level of
  data for clarity.
- Disadvantage - The level of information in reporting cannot be 100%
  accurate. There would be in an increase in variances as there would be no tie back to actuals.

## Average

Plans use the average of all salaries when rolling up into a larger budget or forecast plan. For
example, if you have 10 analysts, you would take the average salary of those 10 analysts.

- Advantage - Allows you to hide salary information, as well as provide a
  strategic view of salary data.
- Disadvantage - Does not allow for a more granular approach to viewing
  salary data. There would be in an increase in variances, as there would be no tie back to
  actuals.

## One Rate

One rate for all employees and real salaries are entered in the Expenses tab by managers.
Managers are the only ones who can see these if you hide the Labor tab from Admins with a custom
role. See [Restrict access to
labor salary details](restrict-access-labor.html "The tasks below can only be performed by users assigned to the Admin role. See Frontdoor permissions and roles."). This is the recommended approach, as this provides the most accuracy
into salary data while still offering some level of protection.

- Advantage - Allows for accurate planning when budgeting or forecasting
  with regards to salary information. Also allows for the ability to drill down into reporting for a
  more granular view of salary data.
- Disadvantage - Managers can see all salary information within their
  departments. Also, this data is visible to the TBMA or Apptio Admin. There would be in an increase
  in variances, as there would be no tie back to actuals.

## Best practice: Entering salary information by role, region/location, and employee type (external vs. internal)

- Advantage - Most accurate approach, least variance, and ties back to
  actuals.
- Disadvantage - All Admins can see salary information. In addition, anyone
  with access to a specific Cost Center can see all the salaries in that Cost Center.

## Labor security options

This section describes strategies to protect labor information within your Apptio
environments.

## Manage Cost Object Permissions

Many companies set up detailed Cost Object permissions. These companies take considerable effort
to ensure that the permissions for every end user are set up properly per the level of their
respective roles. To learn more, see [Restrict access to labor salary details](restrict-access-labor.html "The tasks below can only be performed by users assigned to the Admin role. See Frontdoor permissions and roles.").

## Hide labor Information

Within their respective Apptio environments, under the Roles tab, the
option exists to remove the Labor option altogether from individual
users.

## Track labor outside of Apptio

Some companies choose not to track labor information within their respective Apptio environments.
These companies utilize other systems to track specific labor information and use those systems in
conjunction with Apptio.

## Restrict labor access to Admins

Labor information can be hidden from everyone except Admins, who would have to budget all the
labor. See [Restrict access to
labor salary details](restrict-access-labor.html "The tasks below can only be performed by users assigned to the Admin role. See Frontdoor permissions and roles.").

## User Permissions

|  |  |  |
| --- | --- | --- |
| **Permission Name** | **Description** | **Default Roles** |
| ITPPlanSettingsEdit | Allows users to edit Plan Settings. | Added to **Admin** and **Budget Process Owner** roles by default. |
| ITPPlanSettingsView | Allows users to view Plan Settings. | None |
| ITPCompensationAdjustmentEdit | Allows users to override default compensation adjustments on labor lines for defined Compensation Cycles. | Added to **Admin**, **Budget Process Owner**, and **Cost Center Owner** roles by default. |
| ITPCompensationAdjustmentAllPeriodsEdit | Allows users to edit compensation adjustments on labor lines for all plan periods, including periods outside the defined Compensation Cycles. | Added to Admin and Budget Process Owner role by default. |

To know more, see [Setting up labor compensation adjustments](plan-labor-compensation.html "Budget Process Owners or users with owner permissions for a Cost Object can account for planned adjustments to labor compensation rates. This can be done for current or planned labor. You can specify a percentage change to base compensation per labor resource, and the date at which the change will become effective.").
