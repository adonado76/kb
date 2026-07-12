---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Labor Activity Over/Under Allocation Analysis"
breadcrumb:
  - "Planning"
  - "Project Labor Activity Planning"
source_path: "it-planning/planning/iip/manage-over-under-allocation.html"
images:
  - "resources/images/it_planning_images/la-2.png"
  - "resources/images/it_planning_images/la-color1.png"
  - "resources/images/it_planning_images/la-colors.png"
  - "resources/images/it_planning_images/la-first.png"
  - "resources/images/it_planning_images/lc-example1.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Activity Over/Under Allocation Analysis

Important: *Available with the* ***Apptio Planning Standard****subscription*

Remember: *Integrated Investment Planning (IIP) feature is enabled*

Allocated labor often represents a significant portion of a project or investment’s total
expense. Understanding how labor is utilized is essential for assessing available capacity
vs. demand, making hiring decisions, determining when to pause or stop non-critical
projects, and identifying underutilized resources whose capacity can be better allocated
elsewhere.

In many organizations, the **resource cost center** differs from the **project cost
center**, and a single labor resource may support multiple projects. This makes capacity
planning more complex and can lead to:

- **Under-allocation**, where valuable capacity is lost
- **Over-allocation**, which causes project delays and misrepresents actual resource
  availability
- Difficulty assessing total demand for key roles vs. available capacity
- Challenges estimating labor funding needs during budgeting

**Integrated Investment Planning (IIP)** addresses these challenges by providing
controls to either **prevent resource over-allocation entirely** or to **define custom
over- and under-allocation thresholds**. These thresholds make it easy to identify labor
assignments that exceed or fall short of acceptable limits, ensuring accurate capacity
forecasting and more effective labor planning across the organization.

## Enable Labor Activity Planning and Allocation Settings

1. Navigate to Administration **Settings (Gear icon)** → **Company Profile**.
2. Ensure **Integrated Investment Planning (IIP)** is enabled first—Labor Activity
   cannot be activated without it.
3. Enable **Labor Activity**.
4. Choose whether to **prevent over-allocation** or **allow over-allocation** of labor
   resources.
   1. **Prevent Over Allocation:** The system will block allocations that exceed
      available resource capacity.
   2. **Allow Over Allocation:** The system will allow allocations above capacity.
5. If over-allocation is allowed, specify the **percentage of over/under allocation**
   permitted.

   ![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-first.png)

   Once enabled, the **Labor Activity** tab becomes available for planning project
   labor.

## Enable Labor Allocation Analysis

**Requires:***New Expenses Experience Page enabled*

1. Navigate to **Expenses** → **Labor Activity** tab.
2. Toggle on **New View**
3. Click the **Ellipsis** menu.
4. Select **Analyze labor allocation**.

   ![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-2.png)

Cells will now be color-coded to reflect labor utilization:

- **Blue** – Under allocation (below the configured threshold)
- **Red** – Over allocation (above the configured threshold)
- **No color** – Within the allowed thresholds

Labor Activity line items are grouped by Resource, and any allocations that fall outside
the defined thresholds are highlighted in the corresponding color. Cells without color
indicate that the allocation is within the acceptable range.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-colors.png)

You can hover over any cell to see the resource’s total capacity and the amount allocated.
Allocations can be viewed in either **Hours** or **FTE**.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-color1.png)

## Labor Capacity

Each labor resource is assigned a working calendar that defines their working days and
hours. To learn more about configuring calendars, see [Working Calendars](../configure-working-days.html "Working Calendar defines how many working days and hours are used for labor planning, which influences full-time-equivalent (FTE) conversion, amortization of labor costs, and monthly expense calculations.").

In **Expenses** → **Labor**, a resource’s **Start Date**, **End Date**, and
**Monthly FTE Capacity** determine how much capacity is available for planning. Labor
capacity in hours is calculated using the following formula:

**Monthly Capacity = (Monthly Working Days × Daily Working Hours × Monthly Labor
Quantity)**

This calculated capacity is used in the Labor Activity tab to determine over- and
under-allocation.

**Example:**

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/lc-example1.png)

Assuming a Gregorian calendar with the working calendar configuration above (5 days per
week, 8 hours per day) and one non-working day for New Year’s Day:

**Working capacity for January = (23 working days − 1 holiday) × 8 hours = 176 hours**
