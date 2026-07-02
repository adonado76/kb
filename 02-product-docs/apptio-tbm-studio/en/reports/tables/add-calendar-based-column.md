---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a calendar-based column to a table"
breadcrumb: []
source_path: "reports/tables/add-calendar-based-column.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a calendar-based column to a table

**Applies to**: TBM Studio 12.0 and later

Tables often include numerical data such as units and cost. These are displayed for the currently
selected month/period. If you want to see values for a span of time greater than a month or period,
you can add a variety of calendar-based columns. Add calendar items using the menu items under the
**Dates** icon on the **Formulas** tab. Several examples of calendar based columns are shown
in the following image. When you add a calendar-based column, the default column name is the
abbreviation plus the name of the selected column.

![](../../../resources/images/studio_images/studioimages/reports/rep203.png)

## Add a calendar-based column

1. Select a value column in the table that will serve as the basis for the calendar column.
2. Click the **Formulas** tab.
3. Open the **Dates** menu and select the **Calendar** column.

## Types of columns

The types of columns are described below.

- **Annualized Value (ANN)** - Calculates the average monthly value to date for a metric, and
  then multiplies that value by 12 to project the total annual value for the fiscal year. This
  function is useful for projecting actual values such as cost and units.
- **Fiscal Year (FY)** - Sums the value of a specified metric in the same table for the entire
  fiscal year. If no year is specified, the function is evaluated for the current year. This function
  returns the total for the entire year regardless of the selected period.
- **Fiscal Quarter (FQ)** - Sums the value of a specified metric in the same table for the
  entire fiscal quarter. If no quarter is specified, the function is evaluated for the current
  quarter. This function returns the total for the entire quarter regardless of the currently selected
  period.
- **Year to Date (YTD)** - Sums the values up to and including the selected month in the
  current year.
- **Quarter to Date (QTD)** - Sums the values up to and including the selected month in the
  current quarter.
- **Last Fiscal Year (LFY)** - Shows the value from the previous year. It is useful for
  comparing year-to-year changes in values.
- **Last Fiscal Quarter (LFQ)** - Sums the values within the previous fiscal quarter.
- **Last 12 Months (LTM)** - Shows the value from the last 12 months (not including the
  currently selected month) without regard to fiscal calendars.
- **Last Month (LM)** - Shows the value from the previous month.
- **This Period Last Year (LY)** - Shows the value from the same period last year. Useful for
  comparing year-to-year changes in value.
- **Sparkline Trend** - Shows the values from the past six months in a small trend line.
