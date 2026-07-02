---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Allocate department labor"
breadcrumb: []
source_path: "planning/allocate-department-labor.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Allocate department labor

## Before you begin

Before you begin, ensure you enable the labor planning features. See [Edit the Company Profile](edit-company-profile.dita).

## About this task

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For more information on roles, see Frontdoor permissions and roles.

After your Labor reference data is configured, you can make labor available for work through
labor resource pools and allocations. For more information, see [Manage Labor Configuration
reference data](manage-labor-configuration.dita). Department Owners can allocate to a project, service, or labor pool. These
departmental allocations also appear in the labor allocation tables of your projects and services.
Labor allocations also appear as charges on the Ledger page for the
department for licensed users of Project Financial Planning or Service Demand Planning.

## Procedure

- **Enter labor allocation data**

  Work with planned labor details on the Labor tab,
  Planned page.

  1. In the Plan menus at the top right, select a Plan,
     a Cost Object category, and a cost object or
     cost object group.

     [Learn more about navigating in Planning](navigate-apptio-planning.html#Toolbar).

     Note: Cost
     Center Owners can only edit their assigned Cost Centers. For more
     information, see [Manage Cost Object
     Permissions reference data](manage-cost-object.html).
  2. Navigate to
     Planning > Expenses.
  3. Select the Labor tab.
  4. Select Existing to plan labor compensation adjustments for current
     labor.
  5. Select Planned to plan labor compensation adjustments for planned
     labor.
  6. Select Edit Allocations in the Allocations column.
     The Resource Allocation table displays and includes the following columns:
     - Cost Object Type - The Cost Object group to assign to the resource.
     - To Cost Object - The specific Cost Object to assign to the resource.
     - To Account - The account receiving the money for the service.
     - From Account - The account withdrawing the money to pay for the
       service.
     - Quantity - The periods (months, quarters, and years) of time a percentage
       of the resource is allocated to the Cost Object.
- **View labor allocation data**

  When allocations have been entered, an Allocations option appears next to
  the Planned and Existing links under the
  Labor tab. Click Allocations to view the details in a
  read-only table.

  You can view allocations in the following ways:

  - A percentage value.
  - A full-time-equivalent (FTE) value.
  - A prefigured unit of labor measure as defined in the Company Profile. For more information, see
    [Edit the Company
    Profile](edit-company-profile.html).
