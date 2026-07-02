---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Enable custom calendars"
breadcrumb: []
source_path: "planning/custom-calendars.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Enable custom calendars

Note: If Fiscal Calendar Service (FCS) is enabled in your environment, please configure fiscal
calendar using FCS and skip the steps described on this page. To learn more about Planning
integration with FCS, refer to the release notes for [Planning 3.76](../whats-new.htm "(Opens in a new tab or window)"). To learn more about FCS, refer [Fiscal Calendar
Services](../../fiscal-calendar-services/home.htm "(Opens in a new tab or window)").

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

We support three ways an organization can structure their fiscal calendars:

- Gregorian calendars - standard 12-period calendars where each period corresponds directly with a
  month. IT Planning was built with this calendar as the default calendar setup.
- Custom 12-period calendars - calendars that allow you to begin fiscal years at a different time
  than that of the regular year or to divide up the weeks/days in a year in a specific way such that
  each period starts/ends at the beginning/end of a week.
- Custom 13-period calendars - calendars with 13 periods instead of 12. The primary reason for
  this is to make each period the same number of days.

You can set up Planning to use a custom fiscal calendar by contacting your Apptio customer
success manager. They can create a tenant with the custom fiscal calendar feature available. Note
that you can't convert an existing tenant from a standard calendar to a custom fiscal calendar.

## Custom calendar capabilities in IT Planning

Because tenants cannot switch between custom calendars and the standard calendar, it's a good
idea to review the following capabilities before opting in to this feature:

- KPIs - KPIs for a period or a year will correctly render and calculate
  values specific to your custom calendar.
- Calendar Pickers - Calendar pickers, such as the one on the
  Expenses tab, will select the proper period based on your custom calendar.
  For example, if you choose the 2/3rd section of Q2 in a 2020 plan using the 4-5-4 calendar, you will
  see Oct FY20 through Feb FY20 as the selection.
- Expense tables - In Expense tables,
  Qtr and FY column data is summarized correctly
  regardless of calendar customizations. For example, a $52k contract set up using the 4-5-4 calendar
  will have $13k in each quarter, assuming no proration at all.
- Supported calendars - Currently, we support 12-period and 13-period
  custom fiscal calendars.
- Leap weeks - for 12-period custom fiscal calendars, there must be 13
  weeks) in each quarter. Common calendars that fit into this category include the 4-5-4, 4-4-5, and
  5-4-4 fiscal calendars. For 13-period custom fiscal calendars, each period consists of exactly 4
  weeks. In both cases, custom fiscal calendars result in 52-week years made up of 7-day weeks, for a
  total of 364 days in a typical fiscal year. Because a calendar year typically has 365 days in it,
  companies using these fiscal calendars must occasionally add a leap week, or 53rd week, to their
  fiscal year every five to six years. These leap weeks are often added to the last period in a
  specific quarter but could conceivably be added by a company at any time, including as a 6th week to
  an existing 5-week period (which would constitute a 4-4-6 pattern if you are using a 4-4-5 custom
  fiscal calendar).
- Updating custom calendars - Occasionally, you will need to upload a new
  custom calendar to add more planning years to the application or to fix an error with the existing
  calendar. The new custom calendar will replace the existing custom calendar. If your new calendar
  differs from the old one for an existing time period (i.e., if you're fixing an error), existing
  plans aren't updated based on the new calendar. Only new plans will take the new calendar into
  account.
- Calendar length - Custom calendars need to be planned out far in advance. You
  must upload a minimum of seven years of calendar periods at a time.
- Plan restrictions - To create a new plan in a custom calendar environment, a
  minimum of seven years of calendar periods must be in the system *from the start date of the
  plan*. This means that even if you have seven years of calendar periods, you will only be able to
  create plans starting on the very first period. You must upload additional periods to create plans
  which start later. After you have set up a Custom Fiscal Calendar, Apptio recommends that you define
  over 30 years of calendar periods.

## Enable and define a custom 12-period calendar

After your customer success manager has provided you with a viable tenant, you must enable custom
calendars on the Company Profile page.

1. On the Apptio planning menu, click the Settings button (![](../../resources/images/it%20planning_images/icon_gear.png)), then click Company
   Profile.

   The Company Profile page opens.
2. In the Settings section, select Enable Custom Fiscal
   Calendar.

   ![](../../resources/planning_images/itp_company-profile_custom-calendars.png)

   The feature
   is now enabled.
3. Select Export Template to download a .csv file with the proper column
   names.

   You will use this file to define your custom calendar.
4. Enter your custom calendar data in the .csv file.

   The file contains two columns:
   StartsOnInclusive and FiscalYear. Each fiscal year
   should contain twelve entries (one for each fiscal period in the year), and the first period defined
   must be the first period of the fiscal year. Additionally, you must define a minimum of six years at
   a time. This means your table must contain a minimum of 73 rows. See the example below for
   information on the correct data formatting.
5. Save the template in .csv format.
6. On the Company Profile page, select Import and
   select your .csv file.

Example reference data

The following table demonstrates the correct format for a 12-period custom calendar .csv file.
Each StartOnInclusive value represents the start date for a period. This
means that the first period in the example begins on 09/29/19 and ends on 10/26/19, the second
period begins on 10/27/19 and ends on 11/30/19, and so on.

NOTES:

- The following example contains 13 rows which define 12 calendar periods. The 13th row defines
  the end date for the 12th period. The amount of rows in the upload will always be n+1, where n is
  the number of periods defined.
- This table only contains data for one fiscal year. A minimum of six years must be uploaded at a
  time.

| StartsOnInclusive | FiscalYear |
| --- | --- |
| 2019-09-29 | 2020 |
| 2019-10-27 | 2020 |
| 2019-12-01 | 2020 |
| 2019-12-29 | 2020 |
| 2020-01-26 | 2020 |
| 2020-03-01 | 2020 |
| 2020-03-29 | 2020 |
| 2020-04-26 | 2020 |
| 2020-05-31 | 2020 |
| 2020-06-28 | 2020 |
| 2020-07-26 | 2020 |
| 2020-08-30 | 2020 |
| 2020-09-27 | 2021 |

## Enable and define a 13-period calendar

After your customer success manager has provided you with a viable tenant, you must enable
13-period calendars on the Company Profile page - On the Apptio planning
menu, click the Settings button (![](../../resources/images/it%20planning_images/icon_gear.png)), then click Company
Profile.

1. On the Apptio planning menu, click the Settings button (![](../../resources/images/it%20planning_images/icon_gear.png)), then click Company
   Profile.

   The Company Profile page opens.
2. From the Fiscal Calendar drop down, select the 13-period calendar.
3. Select Enable Custom Fiscal Calendar.
4. Select Export Template to download a .csv file with the proper column
   names.
5. Enter your custom calendar data in the exported .csv file.

   The .csv file contains two columns:
   StartsOnInclusive and FiscalYear. Each fiscal year
   should contain thirteen entries (one for each fiscal period in the year), and the first period
   defined must be the first period of the fiscal year. Additionally, you must define a minimum of six
   years at a time. This means your table must contain a minimum of 79 rows. See the example below for
   information on the correct data formatting.
6. Select Import to import a .csv file.

The .csv file must contain 13 entries for each fiscal year. Each entry represents a period and it
must define the first day of the period.

Example reference data

The following table demonstrates the correct format for a 13-period custom calendar .csv file.
Each StartOnInclusive value represents the start date for a period. This
means that the first period in the example begins on 01/01/21 and ends on 1/28/21, the second period
begins on 1/29/21 and ends on 2/25/21, and so on.

NOTES:

- The following example contains 14 rows which define 13 calendar periods. The 14th row defines
  the end date for the 13th period. The amount of rows in the upload will always be n+1, where n is
  the number of periods defined.
- This table only contains data for one fiscal year. A minimum of six years must be uploaded at a
  time.

| StartsOnInclusive | FiscalYear |
| --- | --- |
| 1/1/2021 | 2021 |
| 1/29/2021 | 2021 |
| 2/26/2021 | 2021 |
| 3/26/2021 | 2021 |
| 4/23/2021 | 2021 |
| 5/21/2021 | 2021 |
| 6/18/2021 | 2021 |
| 7/16/2021 | 2021 |
| 8/13/2021 | 2021 |
| 9/10/2021 | 2021 |
| 10/8/2021 | 2021 |
| 11/5/2021 | 2021 |
| 12/3/2021 | 2021 |
| 12/31/2021 | 2021 |

## Configure reference data for custom calendars

After you enable custom calendars and upload your organization's calendar on the Company
Profile Page, you must update several reference data dimensions to make use of the new feature.
For more information, see [Manage reference data](manage-reference-data.html "(Opens in a new tab or window)").

1. For the Contract Type data dimension, select one of the following
   Contract Amortization Methods:
   - Manual Amortization
   - Straight Line Even Periods
   - Straight Line Using Calendar Days
   - Straight Line By Duration Custom Fiscal Calendar

   For more information, see [Manage Contract Configuration reference data](manage-contract-configuration.htm "(Opens in a new tab or window)").
2. For the Labor Allocation Rules data dimension, for each Account, set the
   Labor Amortization Method value to Straight Line Using Calendar
   Days to utilize your custom calendar. Select a different amortization method if you
   don't want to use the custom calendar for a given account. For more information, see [Manage Labor Configuration
   reference data](manage-labor-configuration.htm "(Opens in a new tab or window)").
3. For the Asset Class data dimension, set the Depreciation
   Method value to Straight Line Using Calendar Days to utilize your
   custom calendar. Select a different amortization method if you don't want to use the custom calendar
   for a given asset class. For more information, see [Manage Asset Configuration reference data](manage-asset-configuration.htm "(Opens in a new tab or window)").
