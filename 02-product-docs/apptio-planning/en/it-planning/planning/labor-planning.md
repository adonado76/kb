---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Labor Planning Overview"
breadcrumb:
  - "Planning"
  - "Labor Planning"
source_path: "it-planning/planning/labor-planning.html"
images:
  - "resources/images/it_planning_images/glf.png"
  - "resources/images/it_planning_images/lca-1.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Planning Overview

The Labor Planning module enables organizations to plan and budget for workforce-related
expenses — including salaries, benefits, taxes, and associated cost allocations. It helps you
model staffing needs, assign costs to departments, and align workforce strategy with business
priorities.

**Why Use Labor Planning**

- Provides visibility intoheadcount, employee costs, and role-level expenses across
  departments and projects.
- Enable Finance and HR to collaborate more effectively on capacity planning, hiring, and
  workforce cost optimization.
- Configure labor allocation rules to automatically calculate the fully burdened cost of
  each headcount, including salary, benefits, and overhead.

## Configure Labor Planning

Note: Admin or Budget Process Owner roles are required to perform these tasks.

Before you start entering labor line items, you’ll need to enable Labor and set up
reference data so labor allocations behave consistently in your model.

Enabling labor planning activates the related Reference Data tables and adds the **Labor**tab to the Expenses table.

**Enable Labor Planning** 

1. Go to **Settings** (Gear icon) **→ Company Profile**.
2. Enable **Labor Headcount**
3. **Configure Headcount Summarization Method** – Determines how headcount totals are
   calculated and displayed in KPIs:
4. **Average** – Calculates the average headcount across the selected period.
5. **Start of Period** – Uses the headcount at the beginning of the period.
6. **End of Period** – Uses the headcount at the end of the period.
7. **Select Labor Summarization Settings** – Choose which dimensions to summarize
   generated labor financials by in the **Summary** tab.
8. Available dimensions include any shared between the **Labor** and
   **Financials** schemas. See *[Summarize
   Labor Financials](labor-summarization.html "The Summarize Labor Financials feature enables you to determine how your labor cost data is aggregated and presented in the Summary tab. It controls which dimensions (e.g., Cost Center, Account, Location) are used to group and roll up labor cost lines, ensuring you get the right level of visibility and confidentiality for labor financials.")* for more details.
9. **Enable Variable Compensation Adjustments***(requires New View)* – Allows
   modeling of monthly base compensation changes.
10. See *[Labor Compensation
    Adjustments](plan-labor-compensation.html "Labor Compensation Adjustments allow organizations to model compensation increases (or decreases) over time within Apptio Planning. This feature provides a structured way to account for planned salary adjustments such as merit increases, market adjustments, promotions, or cost-of-living changes.")* for more details.
11. Click **Save and Exit**.

**Set up Labor Roles** 

1. Navigate to **Configuration → Reference Data → Role.**
2. **Export** the template and populate the required fields:
3. **Code** – Unique identifier for the role.
4. **Name** – Name or title of the position.
5. **Import** the updated CSV file and **Publish** the changes to make roles
   available for plans.

*Tip:* You can customize the **Role** schema in **Schema → Standard
Dimensions** to include additional attributes.

**Set up Labor Rates** 

Define default base compensation rates for each labor
role to standardize cost modeling. Rules can use combinations of **Employee Type**,
**Role**, **Location**, and **Vendor**. When a labor line item matches these
attributes, the corresponding default rate is automatically applied.

1. Go to **Configuration → Reference Data → Labor Rates.**
2. **Export** the template and fill out key fields:
3. **Employee Type** – *Internal* or *External*
4. **Role** – The Role Code from the Labor Roles table
5. **Location** – The Location Code from the Location reference data
6. **Vendor** – The Vendor Code from the Vendor reference data
7. **Currency** – Currency code for the rate
8. **Base Rate** – Annual compensation for the role
9. **Import** the updated CSV file and **Publish** the changes to make rates
   available for plans.

**Set up Labor Allocation Rules** 

Labor Allocation Rules define how labor
costs are distributed across departments and GL accounts. Each labor line item in Apptio
Planning starts with a base rate, and allocation rules automatically apply distribution
logic—either as a percentage of the base rate or a fixed value. This ensures accurate
“fully burdened” labor costs and correct allocation to the appropriate departments and GL
accounts.

1. Go to **Configuration → Labor Allocation Rules.**
2. Export a template or enter the following fields directly in the UI:
   1. **Account** – The Account Code from the Account reference data. This
      generates an expense entry for each labor line that meets the rule conditions.
   2. **Output Value Type** – Defines how the cost is calculated:
      1. **Flat Value** – Applies a fixed annual amount.
      2. **Percent of Base Rate** – Calculates a percentage of the Base labor
         rate.
      3. **Percent of Other Rate** – Calculates a percentage of the Other labor
         rate.
   3. **Exclude from Labor Calculation** – Determines whether this cost is included
      in the Fiscal Year total shown in the Labor tab:
      1. **True (checked)** – Excludes the cost from the total (e.g., for
         cross-charges or non-burdened costs).
      2. **False (unchecked)** – Includes the cost in the Fiscal Year total.
   4. **Value** – The percentage or flat amount to apply based on the Output Value
      Type.
   5. **Labor Amortization Method** – Defines how the cost is spread across time
      periods (See *[Labor Allocation
      Rules](manage-labor-allocation-rules.html)* for more details):
      1. **Straight Line Even Periods** – Spreads the cost evenly across all
         periods.
      2. **Straight Line Using Calendar Days** – Distributes cost proportionally
         to the number of days in each period.
      3. **Straight Line Using Working Days** – Uses the defined working calendar
         to weight cost distribution.
3. **Import** the completed CSV file and **Publish** the changes to make the
   allocation rules available for use in plans.

**Plan-Level Time-Effective Labor Allocation Rules**

Labor Allocation Rules can be configured at the plan level with **time-effective values**,
allowing labor costs to vary over the planning horizon without modifying the global Labor Allocation
Rule reference data.

This capability is useful for modeling changes in labor-related costs
such as benefits, bonuses, training, and other components that may increase or decrease over time
within a specific plan.

Each plan maintains its own Labor Allocation Rule timeline
independent of the global reference data. During labor financial generation, the system applies the
appropriate plan-level rate based on the labor Starte Date and the Fiscal Period being calculated.
If no plan-level value exists for a period, the corresponding global Labor Allocation Rule value is
used.

***Key considerations***

- Select the **Plan**, then navigate to **Plan Settings → Labor Allocation Rules** to
  configure plan-specific rule values.
- Use **Effective From** dates to define when each rate becomes active within the plan.
- Changes to plan-level Labor Allocation Rules are reflected immediately in the current plan;
  publishing is not required.
- Plan-level Labor Allocation Rules display the rule attributes from the corresponding global
  Labor Allocation Rule version as read-only, while allowing you to add and update the time-effective
  rates for each rule.
- Plan-level Labor Allocation Rule timelines are preserved when creating a plan from a baseline.
- Compensation adjustments and fully burdened labor cost calculations automatically use the
  applicable plan-level rate for the relevant period.
- If no plan-level rate is defined for a period, the system falls back to the corresponding global
  Labor Allocation Rule value.
- Plan level labor allocation rules also support impot via a .CSV file.

## Entering & Managing Labor Line Items

1. Open your plan and navigate to the **Labor** tab within the **Expenses** page.
2. Add a new labor row by either:
   1. Using the **empty row** at the bottom of the table, or
   2. **Right-clicking** and selecting **Insert Row**
3. **Provide the required information** for each labor row:
   1. **Cost Center** – The organizational unit responsible for the labor cost.
   2. **Role** – The position or job title associated with the labor resource (e.g.,
      Developer, Project Manager).
   3. **Employee Type** – Indicates whether the labor is **Internal** (employee) or
      **External** (contractor).
   4. **Location** – The work location or region of the labor resource; used for
      applying location-based rates.
   5. **Vendor** – The vendor or staffing firm providing the resource (if applicable).
   6. **Employee Name –** The name of the individual; useful for tracking but
      notrequired.
   7. **Base Compensation** – The annual base pay or cost per head before applying
      allocations or adjustments.
   8. **Other Compensation** – Additional annual pay components (e.g., bonuses,
      incentives, allowances) used in allocation rules that apply a Percent of Other Rate
      calculation.
   9. **Quantity** – The number of resources (headcount) represented by this line item.
   10. **Start Date / End Date** – The period during which the resource is active or
       budgeted for.
   11. **Description** – A brief explanation or notes about the labor item (e.g.,
       project assignment, role type).
   12. **Working Calendar** – Defines the working days used to calculate cost
       distributions across time periods.
4. The system automatically generates a headcount plan based on the Quantity, Start Date, and
   End Date. Review the generated plan to confirm that the headcount distribution across
   periods aligns with your expectations.
5. Modify the distribution if needed by editing monthly or periodic fields directly in the
   table.
6. Labor lines that match the configured Role, Vendor, Location, and Employee Type
   automatically apply the correct labor rate and allocation rules.
7. You can override labor rates on specific line items when necessary—for example, to
   reflect an individual’s actual compensation instead of a default rate.
8. The **Fiscal Year Total** column displays the **fully burdened annual cost** for
   each labor line.
   1. If **Variable Labor Adjustments** are enabled, you can model monthly base
      compensation changes and view detailed cost allocations by GL account.
   2. For more details, see *[Labor
      Compensation Adjustments](plan-labor-compensation.html "Labor Compensation Adjustments allow organizations to model compensation increases (or decreases) over time within Apptio Planning. This feature provides a structured way to account for planned salary adjustments such as merit increases, market adjustments, promotions, or cost-of-living changes.")*.

![labor compensation adjustment image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/lca-1.png)

## Important Behavior: Headcount Quantity

- **Headcount quantity is not prorated** based on an employee’s **Start Date** or
  **End Date**.

  For example, if a labor resource begins on **January 15**, they
  will still count as **1 FTE** for the month of January by default.
- **Straight Line by Calendar Days** and **Straight Line by Working Days**
  amortization methods **do** account for Start and End Date proration when calculating
  **cost**, but not headcount.
  - For instance, if you manually adjust a partial-month headcount to **0.5**, the
    system will apply cost proration accordingly (e.g., 0.5 × 15 days in January = 7.5
    days of cost, or roughly one-quarter of the month’s expense).
- **Straight Line by Even Periods** does **not** perform date-based proration—costs
  are spread evenly across all months where the labor resource is active.
  - Therefore, only adjust **headcount to partial FTE (e.g., 0.5)** when using
    **Straight Line by Even Periods** to represent a mid-month hire or part-time
    resource.
- **Amortization methods**determine how **costs** are spread across time (e.g., by
  period, calendar days, or working days), but **do not alter headcount counts** in
  reporting or KPIs.

Tip: If your organization needs to represent partial-month headcount, you can
model the partial headcount directly in the periodic columns or adjust the quantity field
when using **Straight Line by Even Periods**.

## View Generated Labor Financials

- The Summary tab aggregates total burdened labor costs by Department, providing clear
  visibility into how workforce expenses are distributed across the organization.
- Each labor line item generates a financial entry for every Labor Allocation Rule that
  applies. The number of summarized rows displayed in the Summary tab depends on your Labor
  Summarization Settings, which define the grouping dimensions used for rollup. This
  structure ensures detailed allocation while safeguarding individual salary confidentiality
  by summarizing costs at an aggregate level rather than exposing individual compensation
  data. See *[Hide Sensitive Labor
  Data](hide-sensitive-labor-data.html "Administrators can restrict visibility of specific columns in the Labor tab—such as employee name, salary, or other compensation details—so that users without the required permission can view labor entries without seeing sensitive fields.")* for more details.

![image of generated labor financials](../../../../../03-media/apptio-planning/resources/images/it_planning_images/glf.png)
