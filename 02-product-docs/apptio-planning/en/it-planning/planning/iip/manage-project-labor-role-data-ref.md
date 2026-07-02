---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Project Labor Roles"
breadcrumb:
  - "Planning"
  - "Project Labor Activity Planning"
source_path: "it-planning/planning/iip/manage-project-labor-role-data-ref.html"
images:
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Project Labor Roles

Important: Available with the ***Apptio Planning Standard****subscription*

Remember: *Integrated Investment Planning (IIP) feature is enabled*

The **Project Labor Role** reference data defines the project-specific roles used for
internal or external labor resources, along with the hourly labor rates applied when those
resources charge time to a project.

This dimension enables project-level labor planning by allowing organizations to map HR
roles into project-specific roles and set appropriate chargeback or cross-charge rates. For
example, an employee with an HR role of Software Developer 2 may be assigned the Project
Labor Role of Developer when working on a project.

## Configure Project Labor Roles

***Note:*** *Admin or Budget Process Owner roles are required to perform these
tasks.*

1. In the navigation menu, go to **Configuration** → **Reference Data** →**Standard Dimensions** → **Project Labor Role**.
2. Export the template and populate key fields:

   |  |  |
   | --- | --- |
   | **Field** | **Description** |
   | **Name** | The display name of the Project Labor Role. This is required. |
   | **Currency** | The currency code for the labor rate. Required when multi-currency support is enabled in *Company Profile*. If left blank, the system uses the default common currency. |
   | **Project Labor Rate** | The hourly rate associated with the Project Labor Role. Supports decimal values. Used for labor cross-charges. |
   | **Source** | The source of the labor role (e.g., *Internal*, *External*, *Vendor Name*). Helps distinguish labor attribution across multiple sourcing models. |
3. Import the updated CSV
4. Click the ![ellipses menu](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) and **Publish** the changes so they are
   available for plans.

## How Project Labor Roles Are Used

Project Labor Roles are used in **Labor Activity Planning**, where organizations assign
labor resources to specific project roles for estimating effort and cost.

- **Project-specific role mapping:**

  HR roles may not reflect how labor is allocated on projects. Project Labor Roles
  allow you to define project-facing role categories (e.g., Developer, Analyst,
  Architect).
- **Labor effort planning:**

  During project planning, hours or FTEs can be allocated to Project Labor Roles to
  estimate labor effort.
- **Cross-charge or internal rate application:**

  Hourly rates assigned to Project Labor Roles determine the cost charged to projects
  for using resources of that role.
