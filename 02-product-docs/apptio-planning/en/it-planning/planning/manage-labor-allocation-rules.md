---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Labor Allocation Rules"
breadcrumb:
  - "Planning"
  - "Labor Planning"
source_path: "it-planning/planning/manage-labor-allocation-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Allocation Rules

Note: Admin or Budget Process Owner roles are required to configure labor allocation
rules.

Labor Allocation Rules enable you to define how base labor costs (salary, benefits, burden)
are distributed across departments, cost centers and GL accounts. When a labor line qualifies
for a rule, the system creates a corresponding financial entry (or entries) applying the
rule’s logic.

These rules help model **fully burdened labor cost** and ensure expenditure is allocated
to the correct Department, Cost Center, and Account rather based on the planned headcount.

## Amortization Methods

|  |  |  |
| --- | --- | --- |
| **Method** | **What it Does** | **Example** |
| **Straight Line Even Periods** | Spreads cost evenly across all periods in which the resource is active or budgeted for. | A rule generates $12,000 annually; for 12 months each period = $1,000. |
| **Straight Line Using Calendar Days** | Spreads cost proportionally based on the calendar days per period. | $12,000 over 12 months, Feb has 28 days → cost for Feb = (28/365)\*12,000 ≈ $920. |
| **Straight Line Using Working Days** | Spreads cost using the defined working-calendar (e.g., excluding weekends/holidays). | $12,000 annually if 260 working days → daily cost = $46.15; March has 22 working days → $1,015. |
| **Straight Line Using Calendar Days Fixed Period** | Distributes costs based on the number of calendar days in each fiscal period relative to the full fiscal year, without prorating employment start or end dates. | A **$12,000** annual amount distributed across a 365-day year: February has 28 days, so the cost for February = **(28 / 365) × 12,000 ≈ $920**, regardless of employment start or end dates within the year. |
| **Straight Line Using Working Days Fixed Period** | Distributes costs based on the number of working days in each fiscal period using the configured working calendar, without prorating employment start or end dates. Falls back to even period distribution when working calendars are fixed. | A **$12,000** annual amount distributed across **260 working days** results in a daily cost of approximately **$46.15**. If March has **22 working days**, the allocated cost for March = **22 × 46.15 ≈ $1,015**, regardless of employment start or end dates within the year. |

## Important Behavior: Headcount Quantity and Labor Cost Proration

**Headcount Quantity** 

Headcount quantity is **not prorated** based on a
labor resource’s **Start Date** or **End Date**.

- If a resource starts or ends partway through a month, they are still counted as **1.0
  FTE for that entire period by default**.
- For example, a labor resource that begins on **January 15** will count as **1 FTE
  for the full month of January** unless you manually adjust the headcount.

**Cost Calculation vs. Headcount** 

Amortization methods affect how labor costs
are spread over time, but they do not affect headcount quantities in the Labor tab.

- **Labor cost** is always calculated as: **Monthly Headcount × Monthly Rate**
- Labor cost proration is only applied when using Straight Line by Calendar Days or
  Straight Line by Working Days amortization methods.

**Amortization Method Behavior** 

- **Straight Line by Even Periods**
  - Does **not** perform date-based proration when calculating labor cost
  - Headcount defaults to **1 FTE for the period**, regardless of start or end
    date.
  - Labor costs are calculated as **Monthly Headcount × Monthly Rate.**
  - Costs are spread evenly across all periods in which the labor resource is active.
  - Example: A labor resource starts on January 15 with a monthly rate of $10,000.
    Using Straight Line by Even Periods, the resource is counted as 1.0 FTE for
    January, and the full $10,000 is allocated to January.

    If you want January to reflect a partial-month cost, you must manually adjust
    headcount (for example, to 0.5 FTE), which would result in $5,000 of labor cost
    for January.
- **Straight Line by Calendar Days** and **Straight Line by Working Days**
  - These methods **do** account for Start and End Date proration when calculating
    labor cost.
  - Headcount still defaults to **1.0 FTE for the period**, regardless of start or
    end date.
  - Labor cost is prorated based on the resource’s active days within the period.
  - Example: Using the same resource that starts on January 15 with a monthly rate of
    $10,000, Straight Line by Calendar Days or Straight Line by Working Days calculates
    labor cost based on the resource’s active days in January.

    With 16 active days,
    the January labor cost is roughly $5,161, even though headcount remains 1.0 FTE
    for the period.

Note: If your organization needs to represent partial-month headcount when using
Straight Line by Even Periods amortization method, you can model the partial headcount
directly in the periodic columns.

## Set up Labor Allocation Rules

Labor Allocation Rules define how labor costs are distributed across departments and GL
accounts. Each labor line item in Apptio Planning starts with a base rate, and allocation
rules automatically apply distribution logic—either as a percentage of the base rate or a
fixed value. This ensures accurate “fully burdened” labor costs and correct allocation to
the appropriate departments and GL accounts.

1. Go to **Configuration → Labor Allocation Rules.**
2. Export a template or enter the following fields directly in the UI:
   1. **Account** – The Account Code from the Account reference data. This generates
      an expense entry for each labor line that meets the rule conditions.
   2. **Output Value Type** – Defines how the cost is calculated:
      1. **Flat Value** – Applies a fixed annual amount.
      2. **Percent of Base Rate** – Calculates a percentage of the Base labor rate.
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
      periods (See *Labor Amortization Methods* for more detail):
   6. **Straight Line Even Periods** – Spreads the cost evenly across all periods.
   7. **Straight Line Using Calendar Days** – Distributes cost proportionally to the
      number of days in each period.
   8. **Straight Line Using Working Days** – Uses the defined working calendar to
      weight cost distribution.
3. **Import** the completed CSV file and **Publish** the changes to make the
   allocation rules available for use in plans.

## Examples

**Example A – Flat Value (annual), No Plan Level Rules** 

This example
demonstrates how the same annual value ($2,000) is distributed using different Amortization Methods.

Flat Value (annual) = $2,000 , **Start Date:** Jan 15

1. **Amortization Method = Straight Line Even Periods**

   Monthly Rate: $2,000 ÷ 12 months = $166.67 per month

   Monthly Allocation:

   |  |  |  |  |
   | --- | --- | --- | --- |
   | **Month** | **Qty** | **Calculation** | **Amount** |
   | January | 1 | ( $2,000 ÷ 12 months) × 1 FTE | $166.67 |
   | February | 1 | ( $2,000 ÷ 12 months) × 1 FTE | $166.67 |
   | March | 1 | ( $2,000 ÷ 12 months) × 1 FTE | $166.67 |
2. **Amortization Method = Straight Line Using Calendar Days** 

   Daily Rate: $2,000 ÷ 365 days = $5.48 per day

   Monthly Allocation:

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Month** | **Qty** | **Days** | **Calculation** | **Amount** |
   | January | 1 | 31 | ((31 – 14 days) × $5.48) × 1 FTE | $93.16 |
   | February | 1 | 28 | (28 days × $5.48) × 1 FTE | $153.44 |
   | March | 1 | 31 | (31 days × $5.48) × 1 FTE | $169.88 |
3. **Amortization Method = Straight Line Using Working Days**

   Working Calendar Definition: 260
   working days

   Daily Rate: $2,000 ÷ 260 days = $7.69 per day

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Month** | **Qty** | **Working Days** | **Calculation** | **Amount** |
   | January | 1 | 21 | ((21 – 8 days) × $7.69) × 1 FTE | $161.49 |
   | February | 1 | 19 | (19 days × $7.69) × 1 FTE | $146.11 |
   | March | 1 | 21 | (21 days × $7.69) × 1 FTE | $161.49 |

**Example B – Percent of Base Rate, No Plan Level Rules** 

An employee has a **Base Rate**
of **$120,000 per year**, and an allocation rule applies **10% of Base Rate** as an additional
cost (e.g., benefits or overhead).

Annual Allocation: $120,000 × 10% = $12,000 per year,
**Start Date:** Jan 15

1. **Amortization Method = Straight Line Even Periods**

   Formula: $12,000 ÷ 12 months = $1,000 per month

   |  |  |  |  |
   | --- | --- | --- | --- |
   | **Month** | **Qty** | **Calculation** | **Amount** |
   | January | 1 | ($12,000 ÷ 12 months) × 1 FTE | $1,000 |
   | February | 1 | ($12,000 ÷ 12 months) × 1 FTE | $1,000 |
   | March | 1 | ($12,000 ÷ 12 months) × 1 FTE | $1,000 |
2. **Amortization Method = Straight Line Using Calendar Days** 

   Formula: $12,000 ÷ 365 days =
   $32.88 per day

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Month** | **Qty** | **Days** | **Calculation** | **Amount** |
   | January | 1 | 31 | ((31 – 14 days) × $32.88) × 1 FTE | $558.96 |
   | February | 1 | 28 | (28 days × $32.88) × 1 FTE | $920.64 |
   | March | 1 | 31 | (31 days × $32.88) × 1 FTE | $1,019.28 |
3. **Amortization Method = Straight Line Using Working Days**

   Working Calendar Definition: 260 working days

   Formula: $12,000 ÷ 260 days = $46.15 per day

   |  |  |  |  |  |
   | --- | --- | --- | --- | --- |
   | **Month** | **Qty** | **Working Days** | **Calculation** | **Amount** |
   | January | 1 | 21 | ((21 – 8 days) × $46.15) × 1 FTE | $599.95 |
   | February | 1 | 19 | (19 days × $46.15) × 1 FTE | $876.85 |
   | March | 1 | 21 | (21 days × $46.15) × 1 FTE | $969.15 |

## Plan-Level Time-Effective Labor Allocation Rules

Note: Admin or Budget Process Owner role is required to configure plan-level allocation
rules.

By default, Labor Allocation Rules are maintained as global reference data, and all plans use the
same rule values when generating labor expense line items. Plan-level time-effective Labor
Allocation Rules allow individual plans to maintain their own rate timelines, enabling scenario
planning and the modeling of changing labor cost assumptions over the planning horizon while
preserving the underlying global rule definitions.

***Key Capabilities***

- **Extend global rules with plan-specific timelines** – Inherit global Labor Allocation Rules
  and define additional time-effective entries at the plan level without altering shared reference
  data.
- **Define Effective From values** – Control exactly when a rule value change takes effect
  within the plan period. Multiple rate entries can be defined within the same month.
- **Automatic rate application** – During labor cost generation, the system selects the
  plan-level effective value whose Effective From date is the latest date on or before the relevant
  date being evaluated. If no plan-level rate covers the period, the system falls back to the global
  rule value.
- **Multi-year scenario modeling** – Apply different benefit rates, bonus percentages, or
  training costs in different years of a multi-year plan without creating separate global rules.

**Setup Plan-Level Allocation Rules**

- Open your **Plan** and from the left navigation select **Plan Settings**.
- Select **Labor Allocation Rule** from the plan settings menu. The **Labor Allocation Rules –
  Time Periods** table lists all global rules available for override.
- Locate the rule you want to extend and click **View Rules** in the **Advanced Rules**
  column to expand the advanced rule rows.
- In the **Advanced Rates** panel, click **+ Add Rate** to add a time-effective entry.
- Specify the **Value** (percentage or flat amount) and the **Effective From** date for when
  that value should apply.
- Add additional rate entries to model value changes across different periods. Each entry must
  have a unique Effective From date.
- Use the **Sort by date** toggle to arrange rate entries chronologically for easier
  review.
- Click **Save** to save the changes.

**Labor Financial Generation for Plan Level Rules**

The system always selects the
rate whose **Effective From** date is the latest date on or before the date being evaluated. The
key behavior per amortization method is:

- **Straight Line Even Periods:** For the **start month**, the rate effective on the
  **labor Start Date** is used for the entire month. For all **subsequent full months**, the
  rate effective on the **1st of that month** is used. Mid-month rate changes within a full month
  are not applied.
- **Straight Line Using Calendar Days:** The daily cost is recalculated for each **rate
  segment** within the month. For the **start month**, only days from the labor Start Date onward
  are active, and the rate effective on the Start Date applies to those days (and onwards until the
  next rate change). For **subsequent months**, each rate segment
  contributes to a proportional share of that month’s cost based on calendar days.
- **Straight Line Using Working Days:** Identical in logic to Calendar Days but only **working
  days** (as defined by the configured working calendar) are counted within each rate segment.
- If no plan-level rate exists for a given period, the system **falls back to the global rule value**.

Note: Plan-level allocation rules and their rate timelines are copied automatically when
creating a plan from a baseline. Reference data sync (Update Ref Data) will add new global rules to
the plan and remove deleted ones, while preserving any plan-level rate entries you have
configured.

**Examples with Plan-Level Time-Effective Rules**

The following examples **(C, D,
and E)** extend **Example B** (Percent of Base Rate, $120,000/year, Qty = 1 FTE, **Start Date
= Jan 15**) by adding plan-level time-effective rates. All three examples use the same plan-level
rate timeline, which has rates changing monthly and also **mid-month** in January and
February.

*Plan-Level Rate Timeline (shared across Examples C, D, E)*

|  |  |  |
| --- | --- | --- |
| **Effective From** | **Rate (% of Base)** | **Notes** |
| 01/01/2026 | 10% | Start of plan |
| 01/15/2026 | 11% | Mid-January change — coincides with labor Start Date |
| 02/01/2026 | 12% | February change |
| 02/10/2026 | 13% | Mid-February change |
| 03/01/2026 | 14% | March change |

**Base Rate:** $120,000/year │ Qty**:** 1 FTE │ Start **Date:** Jan
15

**Example C – Straight Line Even Periods with Plan-Level Rules**

With **Straight
Line Even Periods**, the rate effective on the labor **Start Date (Jan 15)** is used for the
entire start month. For subsequent full months, the rate effective on the **1st of each month**
is used. Mid-month rate changes within a full month (e.g., 02/10 → 13%) are **not applied** —
only the rate active on the 1st of those months matters.

**Applicable rates:** Jan → 11%
(rate on Start Date 01/15), Feb → 12% (rate on 02/01), Mar → 14% (rate on 03/01)

|  |  |  |  |
| --- | --- | --- | --- |
| **Month** | **Qty** | **Calculation** | **Amount** |
| January | 1 | (($120,000 × 11%) ÷ 12) × 1 FTE | $1,100 |
| February | 1 | (($120,000 × 12%) ÷ 12) × 1 FTE | $1,200 |
| March | 1 | (($120,000 × 14%) ÷ 12) × 1 FTE | $1,400 |

Note: For the **start month (January)**, the system uses the rate effective on the labor
**Start Date** (01/15 → 11%), not the rate on the 1st of the month (01/01 → 10%). For subsequent
full months, only the rate in effect on the 1st of the month is used — mid-month changes like 02/10
→ 13% are not applied for Even Periods.

**Example D – Straight Line Using Calendar Days with Plan-Level Rules**

With
**Straight Line Using Calendar Days**, costs are calculated **per rate segment** within each
month. In the **start month (January)**, only days from the labor Start Date (Jan 15) onward are
active.

**January (17 active calendar days: Jan 15–31)**

The rate effective on the
labor Start Date (Jan 15) is **11%**. No additional rate changes occur before February 1, so all
active days in January use this rate.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segment** | **From** | **To** | **Rate** | **Daily Rate** | **Days** | **Segment Cost** |
| Segment 1 | 15-Jan | 31-Jan | 11% | ($120,000 × 11%) ÷ 365 = $36.16 | 17 | $614.79 |

**February (28 calendar days)**

February contains two rate segments due to the
rate change effective February 10.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segment** | **From** | **To** | **Rate** | **Daily Rate** | **Days** | **Segment Cost** |
| Segment 1 | Feb 1 | Feb 9 | 12% | ($120,000 × 12%) ÷ 365 = $39.45 | 9 | $355.07 |
| Segment 2 | Feb 10 | Feb 28 | 13% | ($120,000 × 13%) ÷ 365 = $42.74 | 19 | $812.05 |
| **February Total** |  |  |  |  | **28** | **$1,167.12** |

**March (31 calendar days)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segment** | **From** | **To** | **Rate** | **Daily Rate** | **Days** | **Segment Cost** |
| Segment 1 | Mar 1 | Mar 31 | 14% | ($120,000 × 14%) ÷ 365 = $46.03 | 31 | $1,426.85 |
| **March Total** |  |  |  |  | **31** | **$1,426.85** |

**Summary – Example D (Calendar Days)**

|  |  |  |  |
| --- | --- | --- | --- |
| **Month** | **Qty** | **Segments** | **Monthly Total** |
| January | 1 | 1 (11%, days 15–31) | $614.79 |
| February | 1 | 2 (12% + 13%) | $1,167.12 |
| March | 1 | 1 (14%) | $1,426.85 |

**Example E – Straight Line Using Working Days with Plan-Level Rules**

With
**Straight Line Using Working Days**, the logic is identical to Calendar Days but only **working
days** (weekends and holidays excluded) are counted within each rate segment.

As with
Calendar Days, in the **start month (January)**, only working days from Jan 15 onward are active,
and the rate effective on the Start Date (**11% from 01/15**) applies to all of
them.

Working calendar: **261 working days/year in year 2026**

**Daily rate formula:**Daily Rate = (Base Rate × Plan-Level Rate) ÷ 261

**Assumed working day distribution for
each rate segment:**

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Segment** | **From** | **To** | **Rate** | **Working Days** |
| Jan – Seg 1 | Jan 15 | Jan 30 | 11% | 12 |
| Feb – Seg 1 | Feb 2 | Feb 9 | 12% | 6 |
| Feb – Seg 2 | Feb 10 | Feb 27 | 13% | 14 |
| Mar – Seg 1 | Mar 1 | Mar 31 | 14% | 22 |

**January (12 working days: Jan 15–31)**

The rate effective on the labor Start
Date (01/15) is 11%. All 12 working days in January fall under this single rate segment.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segment** | **From** | **To** | **Rate** | **Daily Rate** | **Wkg Days** | **Segment Cost** |
| Segment 1 | Jan 15 | Jan 31 | 11% | ($120,000 × 11%) ÷ 261 = $50.77 | 12 | $606.90 |
| **January Total** |  |  |  |  | **12** | **$606.90** |

**February (20 working days)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segment** | **From** | **To** | **Rate** | **Daily Rate** | **Wkg Days** | **Segment Cost** |
| Segment 1 | Feb 2 | Feb 9 | 12% | ($120,000 × 12%) ÷ 261 = $55.17 | 6 | $331.03 |
| Segment 2 | Feb 10 | Feb 27 | 13% | ($120,000 × 13%) ÷ 261 = $59.77 | 14 | $836.78 |
| **February Total** |  |  |  |  | **20** | **$1,167.82** |

**March (22 working days)**

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Segment** | **From** | **To** | **Rate** | **Daily Rate** | **Wkg Days** | **Segment Cost** |
| Segment 1 | Mar 1 | Mar 31 | 14% | ($120,000 × 14%) ÷ 261 = $64.37 | 22 | $1,416.09 |
| **March Total** |  |  |  |  | **21** | **$1,416.09** |

**Summary – Example E (Working Days)**

|  |  |  |  |
| --- | --- | --- | --- |
| **Month** | **Qty** | **Segments** | **Monthly Total** |
| January | 1 | 1 (11%, wkg days 15–30) | $606.90 |
| February | 1 | 2 (12% + 13%) | $1,167.82 |
| March | 1 | 1 (14%) | $1,416.09 |
