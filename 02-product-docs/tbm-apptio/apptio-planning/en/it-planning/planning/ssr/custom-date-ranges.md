---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Custom Date Ranges"
breadcrumb: []
source_path: "it-planning/planning/ssr/custom-date-ranges.html"
images:
  - "resources/images/ssr_images/release_notes/bi-ct-customdaterange_722x582.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Custom Date Ranges

The Costing & Planning customers can now create multi-year
reports using custom date ranges.

## Support for custom date ranges with Planning data sources

You can now select the following custom periods for your visualizations:

- Month
- Quarter
- Half
- Year

These custom periods are provided in addition to the existing date ranges. You can also use the
Rolling and Compare option with these custom periods.

To use custom date periods in your visualizations:

1. Open the visualization editor in Apptio BI and select any Planning data
   source.
2. Add the applicable dimensions and metrics.
3. From the Date Range picker, select one of the following custom periods: Month, Quarter, Half, or Year.
4. Set the Rolling option, if required.
5. Rolling: The Rolling option makes a date range relative; the date range changes as you move forward in time. To set a rolling date range, select the Rolling check box. This checkbox is not selected by default.
6. Compare: The Compare option allows you to compare two time periods to see how a given metric has changed over the specified periods. To use the Compare option, select the first date range, and after selecting the Compare checkbox, select the second date rage. The compare checkbox is not selected by default.
7. Save the visualization.

The following figure shows a sample comparison period selection for a visualization.![Select a Date Range compares January through September of 2021 to January through September 2022.](../../../../../../03-media/apptio-planning/resources/images/ssr_images/release_notes/bi-ct-customdaterange_722x582.png)
