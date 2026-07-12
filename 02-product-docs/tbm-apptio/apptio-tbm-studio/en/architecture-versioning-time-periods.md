---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Versioning and Time Periods"
breadcrumb:
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Versioning and Time Periods"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/data-architecture/versioning-time-periods.html"
images:
  - "03-media/apptio-tbm-studio/project-time-settings.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Versioning and Time Periods

TBM Studio is fundamentally a month-centric platform. Nearly everything—data, models, and reports—operates within the context of a specific monthly time period. Understanding how time periods and versioning work is essential to working effectively with the platform.

## Time Period Concepts

A time period in TBM Studio represents a single month of data. When you view a transform table, you see data for one month at a time. When you run a model calculation, it calculates for a specific period. When you view a report, it presents data for the currently selected period (though reports can aggregate across periods for trend analysis).

This month-centric design reflects the reality of IT financial management: costs are typically tracked, allocated, and reported on a monthly cycle.

Key Concept

Data Studio enforces a single active period for transform previews. You cannot preview multiple months simultaneously in the transform workspace. Multi-period aggregation is performed in the reporting layer, not in Data Studio.

## Data Refresh Cycles and Versioning

| Refresh Cycle | Versioning Behavior | Best For |
| --- | --- | --- |
| Refresh Cycle | Versioning Behavior | Best For |
| Ad-Hoc updates | Data can be appended or replaced as needed. No expiration checks. | One-time reference data that rarely changes |
| 1 version; No scheduled updates | Uploaded data replaces existing data. No expiration checks. | Static configuration tables |
| 1 version; Update every month | Single version refreshed monthly. Data flagged as expired if not updated within one month. | Lookup tables that change periodically |
| 1 version; Update every year | Single version refreshed annually. Data flagged as expired if not updated within one year. | Annual rate cards or price lists |
| Monthly versions; Update every month | Each month gets its own version. New data does not overwrite previous months. | GL data, budgets, and forecasts (most common for financial data) |
| Yearly versions; Update every month | Twelve months of data uploaded monthly, each to its own period. | Trailing-twelve-month analyses |
| Yearly versions with carryover | Annual data uploaded at fiscal year start. Previous year values carry forward if new data is not uploaded. | Tables where values are largely the same year over year |

The most common pattern for financial data is monthly versions. With this approach, each month’s GL export, budget file, or forecast becomes its own version. The model references the correct version based on the active time period, ensuring that January allocations use January data and February allocations use February data.

## Fiscal Calendar

TBM Studio supports both standard calendar years (January–December) and custom fiscal calendars. The fiscal calendar determines how time periods are labeled, how fiscal year boundaries are drawn, and how functions like Year-to-Date calculations work.

- Calendar type: Standard (12 months) or custom patterns like 4-4-5 week groupings.
- Fiscal year definition: Whether the fiscal year is identified by its starting period or ending period. For example, a June 2024–May 2025 fiscal year could be labeled FY2024 (starting period) or FY2025 (ending period).
- Display format: Whether dates display as month names (Jan 2024, Feb 2024) or period numbers (P1 2024, P2 2024).

Fiscal calendar settings are configured at the project level and affect every component of the platform—transforms, models, and reports all inherit the same calendar.

## Time Period Inheritance

![Project Time Settings](../../../../resources/images/studio_images/project-time-settings.png)

Important

Closed periods block data uploads and prevent model recalculations for those months. This protects finalized financial data from accidental modification. Editable table publishes may also be blocked when targeting closed periods.
