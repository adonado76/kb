---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Working Calendars"
breadcrumb:
  - "Planning"
  - "Labor Planning"
source_path: "it-planning/planning/configure-working-days.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Working Calendars

Working Calendar defines how many working days and hours are used for labor planning,
which influences full-time-equivalent (FTE) conversion, amortization of labor costs, and monthly
expense calculations.

You can configure multiple calendars in the system (for example: full-time, part-time, global
holiday schedule) and designate a default working calendar. Changes to the calendar affect
labor expense modelling and must be managed carefully.

Note: Admin or Budget Process Owner
roles are required to configure working calendars.

## Types of Working Calendars

**Fixed Calendar**

- Define a set number of working hours per month (for example: 168 hours per month).
- Use this when your organization uses a standard monthly working-hour model regardless
  of actual working days.

**Variable Calendar**

- Define working days by day-of-week, set hours per day, and specify non-working days
  (holidays, shutdowns).
- Use this when your labor planning reflects actual working days, holidays, or
  non-standard schedules.

## Configure Working Calendars

1. Navigate to **Configuration → Calendar Setup**.
2. Click **Add**, then choose either **Fixed Calendar** or **Variable Calendar**.
3. Enter a **name** for the calendar and click **Add**.
4. Click the **Edit (pencil)** icon next to the calendar name to configure details.

**For Fixed Calendars:**

- Enter the **working hours per month** value.

**For Variable Calendars:**

1. Select the **working days of the week**.
2. Enter the **hours per working day** (e.g., 8 for a standard workday).
3. To add non-working days:
   1. Click **Edit**under *Non-Working Days*.
   2. Choose the **year**, then enter a **name** and **date** (MM/DD) for each
      holiday or non-working day.
   3. Click **Save**.

When hovering over a calendar, select **Mark as Default** to set it as the default
working calendar. The default calendar will automatically apply to new labor line items.

## Assigning and Using Working Calendars

- The default working calendar is automatically assigned to labor lines unless a different
  calendar is selected.
- If you have multiple calendars (e.g., for different regions or job types), users can
  override the calendar for specific labor line items.
- To use the working calendar in amortization of labor expenses: Update the **Labor
  Amortization Method** in **Labor Allocation Rules** and publish the changes. Refer
  to [Labor Allocation Rules](manage-labor-allocation-rules.html) for more information.

## Troubleshooting & Considerations

|  |  |  |
| --- | --- | --- |
| **Issue** | **Description** | **Recommendation** |
| Hours to FTE conversion looks incorrect | The calendar may not reflect the correct hours/day or working days/week. | Review the assigned calendar, check hours per day and working days settings. |
| Non-working days missing (e.g., holidays) | The non-working days list may not be populated for that year or region. | Add the holiday dates under Non-Working Days and Save. |
| Multiple calendars confusing to users | Users may not know which calendar to select for line items. | Set a clear naming convention (e.g., “US-FullTime”, “EU-PartTime”) and set a default. |
| Labor expense amortization not reflecting calendar | Amortization rule may not reference the working calendar. | Update the Labor Allocation Rules to use the working calendar and republish the changes. |
