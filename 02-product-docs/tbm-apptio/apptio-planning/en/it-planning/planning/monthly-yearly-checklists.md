---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Monthly and yearly checklists for administering Planning"
breadcrumb: []
source_path: "it-planning/planning/monthly-yearly-checklists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Monthly and yearly checklists for administering Planning

◆ Applies to: Planning administration. The tasks below can only
be performed by users assigned to the Admin or Budget Process Owner roles. For additional
information on roles, see Frontdoor permissions and roles.

Use this checklist as a guide for maintaining your Planning solution.

Note: This checklist does not cover all operational elements for every possible scenario. It is
intended to facilitate the operational procedures for a typically configured solution. All checklist
items link to detailed instructions.

## Monthly checklist

- [Import and publish
  actuals](import-publish-actuals.html)
- [Create a plan or
  forecast](create-budget-plan.html) and notify Department Owners of entry period
- [Integrate with Cost
  Transparency](integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.")

## Yearly checklist

- [Configure project time settings](../../studio/admin/configure-project-time.html "Applies to: TBM Studio 12.0 and later. The options displayed in the Configure Project Time Settings dialog depend on the calendar type you select.") in Costing Standard.
- Update reference data with the new organization information. Built-in dimensions are managed by
  Admins or Budget Process Owners. Many built-in dimensions have dependencies on other dimensions (see
  [Reference data attribute and
  dimensions dependencies](manage-reference-data.html) for information).
  - Update Accounts, Cost Centers, Departments, Location, and Vendors (see [Manage Financial reference
    data](manage-financial-dimensions.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")).
  - Update External and Internal Labor Pools, Labor Allocation Rules, Labor Rates, and Roles (see
    [Manage Labor reference
    data](manage-labor-configuration.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")).
  - Update Contract types and VAT rates (see [Manage Contract reference data](manage-contract-configuration.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")).
  - Update Asset class (see [Manage Asset Class reference data](manage-asset-configuration.html)).
  - Update Cost Object Permissions (see [Manage Cost Object Permissions reference data](manage-cost-object.html "Cost Object Permissions determine which users can view, edit, submit, or approve Department-level plans (Cost Objects). Each Department can have one or more users assigned with edit-level permissions and, for Multi-Level Approvals, approval-level permissions."))
  - If you are supporting multiple currencies, update Actual and Plan Currency rates (see [Manage currency conversion rate
    tables reference data](manage-multi-currency.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")).
  - If [Project Financial Planning is enabled](pfp/gs-project-financial.html "◆ Applies to: Planning with Project Financial Planning."), update Project and Project Group (see [Manage Project reference
    data](pfp/manage-project-configuration.html)).
- [Create a plan or
  forecast](create-budget-plan.html).
- [Enter financial details
  and adjust baseline values](enter-financial-details.html).
- [Open a plan or a
  forecast](open-plan-forecast.html "After you create a budget plan or forecast, optionally adjust the baseline values, set the targets, and open the plan so that the budget owners can edit line items. Budget owners cannot see a plan when it is in the New state. When you open a plan, an email notification is sent to budget owners and all users who have the Edit & Submit permission associated with the Cost Objects in that plan.").
- Notify Department Owners of a budget entry period (start and end date).
- [Create a labor
  plan](create-labor-plan.html).
- [Review, approve, or return
  plans or Cost Objects](review-approve-return.html).
- [Integrate with Cost
  Transparency](integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.").

SEE ALSO: As you update reference data, the following articles may be useful:

- [Manage reference data for
  Planning](manage-itfmf-reference.html "◆ Applies to: Planning")
- [Force a plan to use updated
  reference data](force-plan-use.html)
