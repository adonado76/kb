---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Fiscal Calendar Settings"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/custom-calendars.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Fiscal Calendar Settings

Fiscal Calendar settings define how time is structured and displayed across Apptio
Planning. A fiscal year represents a recurring time structure used for financial planning,
budgeting, and reporting. Unlike a traditional Gregorian calendar, a fiscal year does not need
to start on January 1 or end on December 31. Instead, organizations define fiscal dates that
best align with their business cycles and industry practices.

Note: Admin role is required to manage Fiscal Calendar settings.

Depending on the calendar type, a fiscal year may be organized as:

- 12 consecutive months (Gregorian calendar),
- Week-based periods such as 4-4-5 variants, or
- 13 equal periods, typically designed so each period contains the same number of days.

In all cases, fiscal calendars are designed to align with the underlying Gregorian calendar
over time, accounting for standard year lengths and leap years where applicable. These
settings apply across the entire environment and determine how expenses, forecasts, and
summaries are organized and displayed in all plans.

## Supported Calendar Types

Apptio Planning supports the following fiscal calendar types:

**Gregorian Calendar** 

The Gregorian calendar is the most common fiscal
structure and consists of 12 consecutive months.

**Capabilities:**

- Supports both traditional and non-traditional fiscal years
  - **Traditional:** Fiscal year starts in January and ends in December
  - **Non-traditional:** Fiscal year starts in any month selected by the user
- For non-January starts, choose whether the fiscal year is:
  - **Defined by start period** (e.g., FY2025 is July 2025-June 2026), or
  - **Defined by end period** (e.g., FY2025 is July 2024-June2025)
- Period labels can be displayed as:
  - **Months** (Jan, Feb, Mar), or
  - **Periods** (P1, P2, P3)

To **learn more**, see [*Configure Gregorian Fiscal Calendar*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-gregorian "(Opens in a new tab or window)")

**4-4-5 (4-5-4 / 5-4-4) Calendar Variant** 

4-4-5 variant calendars are
typically used by retail and manufacturing organizations that require consistent
week-based reporting.

**Key characteristics:**

- Fiscal year is divided into weeks rather than months
- Periods always start and end on the same weekday
- Organized into quarters with:
  - Two 4-week periods and one 5-week period
- Supported structures:
  - **4-4-5**
  - **4-5-4**
  - **5-4-4**

To **Learn more**, see [*Configure 4-4-5 Variant Fiscal
Calendar*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-445-variant "(Opens in a new tab or window)")

**13-Period Calendar** 

The 13-period calendar divides the fiscal year into
**13 equal periods**, typically four weeks each.

**Why customers use this
calendar:**

- Ensures each period has the same number of days
- Simplifies operational comparisons and trend analysis
- Common in manufacturing, logistics, and operations-heavy organizations

To **learn more**, see [*Configure 13-Period Fiscal
Calendar*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-13-period "(Opens in a new tab or window)")

## Configure Fiscal Calendar

You can select a fiscal calendar when your Apptio Planning environment is created. The
selected calendar type applies to all plans created in the environment and cannot be changed
by users directly in the UI.

To access your Fiscal Calendar Configuration, go to **Settings (Gear icon) →****Fiscal
Calendar Configuration.**

**Changing the Fiscal Calendar**

Changing the fiscal calendar requires assistance from Apptio Support.

**Important
considerations:**

- Historical plans continue to use the original fiscal calendar
- **New plans** created after the change use the **new calendar**
- Plan comparisons across different calendar structures are **not supported**

If you need to compare new plans to historical plans, you must **recreate the
historical plans** using the new fiscal calendar configuration

To request a
change - Submit a **Support request** through IBM Support or contact your Customer
Success Manager
