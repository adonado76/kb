---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Filter data by date partition"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Transform & Enrich Data"
source_path: "studio/new-uc/howtoguides/work-with-data/filter-data-date.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filter data by date partition

## Objective

Distribute time-stamped data across periods and automatically filter to the active time
period selected in TBM Studio, enabling month-centric cost analysis.

## When to use this

Use Date Partition when:

- Your data contains transaction dates and you need monthly slices
- Working with general ledger data with date stamps per transaction
- Data has months in separate columns (Jan, Feb, Mar, etc.)
- You need values to update automatically when users switch time periods

Note: TBM Studio is month-centric. Date partitions filter data to show only the selected
month&#x2019;s values. Multi-period aggregation occurs in the reporting layer.

***Note:***

## Prerequisites

- Data with date information (in rows or columns)
- Understanding of your data date format
- Date columns properly typed (for row-based data)

## Time estimate

10-15 minutes

**Steps**

## For row-based data (dates in rows)

*Use this approach when your data has date columns with one date per row (e.g.,
transaction date in GL).*

1. Check out the table and add a **Date Partition** step to the transform pipeline.
2. Select **Dates are represented in rows**.
3. Select the **Start Date** column (required).
4. (Optional) Select the **End Date** column if your data spans date ranges.
5. Click **Save**.

## For column-based data (dates in column headers)

*Use this approach when your data has a column for each month (e.g., Budget with Jan,
Feb, Mar columns).*

1. Check out the table and add a **Date Partition** step to the transform pipeline.
2. Select **Dates are represented in columns**.
3. In **Interpret Year As**, select **Fiscal Year** or **Calendar Year**.
4. In **New Column Prefix**, enter a label to prefix the date columns (e.g.,
   "Amount&" creates "Amount Jan&", "Amount Feb&").
5. Select which column sets to partition:
   - If you have multiple sets (e.g., Cost and Budget), select which to include
   - You can partition by one or all column sets
6. Click **Save**.

## Expected results

The table now responds to the active time period selected in TBM Studio. When you change
months using the date picker, the preview updates to show only that month&#x2019;s data.
For column-based partitions, new columns are created with the specified prefix and month
labels.

## Common pitfalls

- **Date format not recognized:** For column-based data, month names must be
  recognizable (Jan, January, P1, etc.). Years can be in any position except the middle
  ("2016 Jan&" or "Jan 2016&" work, but "Jan 2016 Cost&" does not).
- **No data visible after partitioning:** Verify the selected time period matches dates
  in your data. If working with historical data, ensure your TBM Studio date picker covers
  the relevant period.
- **Cannot select multiple months:** This is expected behavior. Date partitions filter
  to a single active period. For multi-month aggregation, use reporting-layer functions like
  YTD (Year to Date) or create date-based columns.

**Related tasks**

- [Version Tables for Monthly Data](version-tables-monthly-data.html)
- Understanding time periods (Concepts: Data Architecture)
- Time-based formulas in reporting (Reference: Formulas & Functions)

**Parent topic:** [Transform & Enrich Data](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
