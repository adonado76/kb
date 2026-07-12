---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Labor Activity Planning Overview"
breadcrumb:
  - "Planning"
  - "Project Labor Activity Planning"
source_path: "it-planning/planning/iip/labor-resource-planning.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Activity Planning Overview

Important: *Available with the* ***Apptio Planning Standard****subscription*

Remember: *Integrated Investment Planning (IIP) feature is enabled*

**Labor Activity Planning** enables organizations to plan the labor effort required for
projects by hours or FTE, while also supporting cross-charging, labor cost allocation, and
visibility into over/under allocations across project resources.

When the Integrated Investment Planning (IIP) feature is enabled, two optional labor
attributes become available in **Expenses** → **Labor**:

- **Project Labor Role**
- **Labor Activity Type**

## Enable Labor Activity Planning

Note:

- *Admin or Budget Process Owner roles are required to perform these tasks.*
- The **Integrated Investment Planning (IIP)** feature must be enabled *before*
  Labor Activity can be turned on.

Before users can allocate labor effort in the **Expenses** → **Labor Activity** tab,
Labor Activity Planning must be enabled in the Company Profile.

**Steps to Enable Labor Activity Planning**

1. Navigate to **Settings (Gear)**icon→ **Company Profile**.
2. Ensure **Integrated Investment Planning (IIP)** is enabled first—Labor Activity
   cannot be activated without it.
3. Enable **Labor Activity**.
4. Choose whether to **prevent over-allocation** or **allow over-allocation** of
   labor resources.
5. **Prevent Over Allocation:** The system will block allocations that exceed
   available resource capacity.
6. **Allow Over Allocation:** The system will allow allocations above capacity.
7. If over-allocation is allowed, specify the **percentage of over/under
   allocation**permitted.

Once enabled, the **Labor Activity** tab becomes available for planning project
labor.

## Project Labor Role & Rate

The **Project Labor Role** reference data defines the project-specific roles used for
internal or external labor resources, along with the hourly labor rates applied when those
resources charge time to a project.

This dimension enables project-level labor planning by allowing organizations to map HR
roles into project-specific roles and set appropriate chargeback or cross-charge rates. For
example, an employee with an HR role of Software Developer 2 may be assigned the Project
Labor Role of Developer when working on a project.

For configuration details, refer to [Project Labor Roles](manage-project-labor-role-data-ref.html).

## Labor Activity Type

The **Labor Activity Type** reference data defines the mapping between the Department
Cost Center Account (the provider) and the Project Cost Center Account (the consumer) for a
given activity type. This mapping determines how labor charges and cross-charges flow
between cost centers.

Labor Activity Types are used during Labor Activity Planning to:

- Identify which cost center provides the labor
- Identify which project or cost center consumes the labor
- Allocate the corresponding charge and cross-charge amounts to the correct provider and
  consumer accounts

For configuration details, refer to [Labor Activity Type](manage-labor-activity-type-data-ref.html).

## Assigning Labor Roles and Planning Project Effort

Labor Activity Planning is a two-step process. First, you assign a labor resource to a
**Project Labor Role** in the **Labor** tab. Then, you plan the resource’s project
effort (hours or FTE) in the **Labor Activity** tab.

Only labor resources with a Project Labor Role assigned will appear as **Resources** in
the **Labor Activity** tab.

**Step 1: Assign a Project Labor Role and Rate (Labor Tab)**

To set a resource’s project role and billable rate:

1. Go to **Expenses** → **Labor** and create or edit a labor resource line.
2. Select the **Project Labor Role** from the dropdown.
3. The **Project Labor Rate** automatically populates based on reference data.

***Important Behaviors:***

- Selecting a **Project Labor Role** automatically sets the **Project Labor
  Rate**.
- You may override the default rate.
- If a labor resource is **not billed** to a project, you can leave Project Labor
  Role and Rate blank.
- Labor cross-charges are generated in the **Summary** tab using Price x Quantity
  (Hours).

**Step 2: Allocate Hours or FTE to Projects (Labor Activity Tab)**

The Labor Activity tab allows you to plan labor effort for projects by **Project Labor
Role** or by **Named Resource**. Resources displayed in this tab are filtered based
on the Project Labor Role assignments made in **Expenses** → **Labor**.

Follow the steps below to allocate labor to a project:

1. **Select the Project** - In the **Labor Activity** tab, choose the
   **Project** you want to plan labor for.
2. **Choose How to Allocate Resources** - You may allocate labor in one of two ways:
   1. **By Project Labor Role**
   2. **By Named Resource**
3. **Select a Project Labor Role**
   1. Choose the **Project Labor Role** from the dropdown.
   2. The **Project Labor Rate** will automatically populate based on the Project
      Labor Role reference data.
   3. You may override the rate if needed.
4. **Select a Named Resource (Optional)**
   1. In the **Resource** dimension, choose a named resource to allocate.
   2. The resource list is automatically filtered to show only those mapped to the
      selected **Project Labor Role** in the Labor tab.
      1. Use the **Resource Cost Center** dimension to limit the list to
         resources belonging to a specific cost center.
      2. Note: Resource allocation cannot be performed when a **Resource Cost Center** is in a
         **submitted** or **locked** state. Any attempt to change or assign a Resource Cost Center that
         is already submitted/locked will result in a validation error, and the change will not be saved.
5. **Select the Activity Type** - If the labor is billable or cross-charged:
   1. Choose the appropriate **Activity Type**.
   2. This determines how charges and cross-charges are allocated between provider and
      consumer accounts based on Labor Activity Type mappings.
6. **Enter Effort in Hours or FTE**
   1. Enter the required labor effort in **monthly hours** or **FTE**.
   2. Effort entered will drive labor cost calculations.
7. **Review Labor Charges** - Labor charges are calculated using **Price ×
   Quantity** based on the selected Project Labor Role, Labor Rate, Activity Type,
   and allocation rules. The resulting amounts appear in the **Summary** tab, where
   the provider cost center receives a credit and the consumer cost center receives a
   debit.
