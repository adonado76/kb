---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Project Permissions"
breadcrumb:
  - "Planning"
  - "Project Planning"
source_path: "it-planning/planning/iip/project-level-access-control.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Project Permissions

Important: *Available with the* ***Apptio Planning Standard****subscription*.

Remember: *Integrated Investment Planning (IIP) feature is enabled*

Integrated Investment Planning (IIP) supports different budget ownership models across
organizations. Because project and operational budgeting structures vary, Apptio Planning
provides flexible **project-level access controls** that align with your organizational
hierarchy, cost accountability model, and planning workflow.

This guide describes common project planning use cases and explains how to configure
project-level permissions using **Projects → Permission** and **Cost Object
Permissions**.

## Use Case 1: Project Managers Own All Project Costs (Dedicated Project Departments)

**Overview**

Used when each project has its own dedicated cost center, and theProjectManageris the sole
owner of all costs for that project.

**Goal**

Project managers plan and manage all expenses for the projects they own.

**Organization Structure**

- Projects have dedicated cost centers that roll up to a distinct “Project Department.”
- Project budget owners are separate from departmental operational budget owners.

**Access Requirements**

- Project Managers can view/edit only their project departments.
- Project Managers can enter spend directly into their project cost centers.
- Project Managers can submit budgets for approval.

**Implementation**

- Assign Project Managers the Cost Center Owner (or equivalent) role in Frontdoor.
- Grant edit access to the project cost centers using Cost Object Permissions.
- Use “project rollup departments” to separate project-only financials.

**Result**

- Project Managers can enter project costs within their assigned department.
- Access remains restricted to project-specific departments.

## Use Case 2: Cost Center Owners Manage Both Operational + Project Costs

**Overview**

Used when a single budget owner manages both operational and project expenses for their
department.

**Goal**

Cost Center Owners manage all spend—project and operational—across their department.

**Organization Structure**

- No separate personas; Cost Center Owners own all costs.
- Projects may assign costs to any cost center.

**Access Requirements**

- Owners can view/edit only their own departments.
- Owners can submit budgets through the standard workflow.

**Implementation**

- Assign Cost Center Owners the **Cost Center Owner** role.
- Grant edit permissions to relevant departments through **Cost Object Permissions**.
- Enable "Allow Any Cost Center" on Projects if cross-department allocation is needed.

**Result**

- One persona handles all budgeting activities.
- Full access to department-level operational and project expenses.

**Limitation**

- You cannot restrict a Cost Center Owner to only project expenses. They will see all
  expenses in their department.

## Use Case 3: Hybrid Model — Department Owners + Project Managers (Shared Project Costs)

**Overview**

Used when Project Managers contribute project expenses to departments, while Department
Owners remain responsible for operational spend and approving project allocations.

**Goal**

- Department Owners plan operational spend and approve project allocations.
- Project Managers enter only project expenses across departments.

**Organization Structure**

- Both Departments and Projects have cost centers.
- Project Managers allocate spend to any allowed cost center.
- Department Owners approve project allocations within their departments.

**Access Requirements**

- **Department Owners:** full access to all expenses in their departments.
- **Project Managers:** restricted to view/edit only expenses for their assigned
  projects.
- Both personas must see only the relevant project/department data.

**Implementation**

- Assign Cost Center Owners the **Cost Center Owner** role.
- Grant edit permissions to relevant departments through **Cost Object Permissions**.
- Assign Project Managers either the **IIP Project Manager** role or **IIP Portfolio
  Manager** role. IIP Portfolio Managers can manage the Projects List and project
  permissions.
- Enable "Allow Any Cost Center" on Projects if cross-department allocation is needed.

**Result**

- Department Owners see all expenses (project + operational).
- Project Managers see only lines where **Project = assigned project**.
- Project Managers can add/edit/delete project expenses.
- Department Owners continue to submit budgets.

**Limitations**

- Project Manager access is always filtered to project-only expenses.

## Project Roles & Permissions

**Standard Roles:** 

- **IIP Portfolio Manager**
  - Edit/view access for entire project portfolio.
  - Can manage project-level permissions.
- **IIP Project Manager**
  - Edit/view only expenses for assigned projects.

    |  |  |
    | --- | --- |
    | **Permission** | **Description** |
    | **IIPProjectExpenseEdit** | View/edit expenses only for assigned projects. |
    | **IIPProjectPermissionManage** | Manage permissions in Projects → Permission. |
    | **IIPProjectManage** | Create and delete projects. |

Users need permissions in both Projects Permissions and Cost Object Permissions:

|  |  |
| --- | --- |
| **Permission Area** | **Why It’s Needed** |
| **Projects** → **Permission** | Determines which projects the user manages. |
| **Cost Object Permission** | Controls access to departments where those project costs roll up. |
