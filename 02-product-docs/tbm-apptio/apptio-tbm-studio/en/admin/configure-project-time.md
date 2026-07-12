---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Configure project time settings"
breadcrumb: []
source_path: "admin/configure-project-time.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure project time settings

Applies to: TBM Studio 12.0 and later. The options displayed in
the Configure Project Time Settings dialog depend on the calendar type you
select.

As you configure the project time settings, consider the following guidelines:

- When you save the settings, you cannot go back and change the fiscal year definition.
- If you want to include historical data in your project, pick a start-of-project date that spans
  the dates of the data.

## Calendar types supported

The application supports the following calendar types:

- Gregorian
- 445, 454, and 544
- 13 period (444)

The calendar type you select determines the fields displayed in the Fiscal Year
Definition section of the Configure Project Time Settings dialog
shown in the following image. You cannot change the calendar type after it has been set.

![](../../resources/images/studio_images/studioimages/studio/stu040.png)

Note: The same
type of calendar must be used across all projects.

The fields for each type of calendar are described in the information below. The fields in the
Fiscal Year Definition section are described first, followed by descriptions
of the Project Time Span Definition, Viewable Periods of
Time, and Editable Periods sections. The latter sections are
similar for all types of calendars.

## Fiscal Year Definition - Gregorian calendar

The fields for the Gregorian calendar are described below.

- Calendar Type - Select the Gregorian calendar type.
- The Fiscal Year is Defined By - Select Starting
  Period or Ending Period. If you select Starting
  Period, the fiscal year is based on the first period of the calendar. If you select
  Ending Period, the fiscal year is based on the last period in the calendar.
  - For example, suppose you have a fiscal year that runs from June 2016 to May 2017. If you select
    Starting Period, the fiscal year will be 2016. If you select
    Ending Period, the fiscal year will be 2017.
- Starting Month of Fiscal Year - Select a month/period that will be the
  start of the fiscal year.

  Note: Once you save this setting, you cannot change it.
- Display Month or Period Names - Choose if dates will display the month
  name (e.g.: Jan 2016, Feb 2016), or period (e.g.: P1 2016, P3 2016). This setting applies to many
  areas of the product, including the date picker.
  - If your fiscal year starts in a month other than January, you may wish to display periods
    instead of months to eliminate confusion over which fiscal year a month belongs to.For example,
    assume your fiscal year starts on April 1 and the fiscal year is defined by the starting date. The
    date April 15, 2016 would belong to the 2016 fiscal year and would be displayed as Period 1. The
    date March 15, 2016 would belong to the 2015 fiscal year and be displayed as Period 12.

## Fiscal Year Definition - 445, 454, and 544

The fields for the 445, 454, and 544 calendars are described below.

- Calendar Type - Select a 445, 454, or 544 calendar type. The numbers
  represent the number of weeks in each of the four quarters in the fiscal year. For example, 445
  represents 4 weeks, 4 weeks, 5 weeks.
- The Fiscal Year is Defined By - Select Starting
  Period or Ending Period. If you select Starting
  Period, the fiscal year is based on the first period of the calendar. If you select
  Ending Period, the fiscal year is based on the last period in the
  calendar.
- For example, suppose you have a fiscal year that runs from June 2016 to May 2017. If you select
  Starting Period, the fiscal year will be 2016. If you select
  Ending Period, the fiscal year will be 2017.
- The Fiscal Calendar - Use the four fields in this section to define the
  starting or ending day of the fiscal calendar. Select values from each of the drop-down lists.
- Display Month or Period Names - Choose if dates will display the month
  name (e.g.: Jan 2016, Feb 2016), or period (e.g.: P1 2016, P2 2016). This setting applies to many
  areas of the product including the date picker.

## Custom Calendar 454

How to configure the customer calendar? (First Time configuration)

1. You can select Calendar Type as 445 or variant and toggle the Fiscal
   Calendar from Standard to Custom. An Upload widget appears with text 'Click to
   upload'.

   ![](../../resources/images/studio_images/custom_calendar/fiscal-calendar-1.png)
2. Click to upload widget looks similar to transform pipeline:

   ![](../../resources/images/studio_images/custom_calendar/click-to-upload.png)
3. You can browse the Custom calendar file by clicking on Append option in the menu dropdown. Once
   you upload the file name, it’ll show up the file name in the time setting dialogue.

   ![](../../resources/images/studio_images/custom_calendar/append-1.png)
4. Once done with other field selection, you can select Configure Time
   button. After you upload your calendar file, the time for Start of Project and End of Project will
   be updated to reflect the calendar file.

   ![](../../resources/images/studio_images/custom_calendar/time-setting-dates.png)
5. From the time settings dialogue, you can either Download the configured
   custom calendar or Append further calendar configurations.
6. Reconfiguration of the calendar can be done via the project setting. As part of a
   reconfiguration, you can Append the existing calendar file which will, in
   turn, extend the calendar dates. Once you re-upload the calendar file, the project end time will be
   updated as per the new end time of the calendar file.

Note: Start of the Project date will not be changed during the
reconfiguration. It will change only once when you’re configuring the project for the first time.
Only the End of Project will change with every re-upload of the file.

## How do you migrate?

Historic calendar information is migrated via an action in /data. The migration will be only for
projects which have the 445 calendar type. To migrate:

- To migrate to the custom calendar settings, you must have a standard project with 445 calendar
  type configured.
- Contact the Customer Support team to migrate your standard calendar information and custom
  configuration.

Note: Since the project start and end are dictated by the uploaded calendar table, they are no
longer configurable via the time settings dialog. This means that once you on board into this Custom
Calendar 454, you can not go back and change the dates. Start of the Project date is configured only
once when you configure the project for the first time. Only the End of Project is updated with
every re-upload of the file.

## Calendar Table

1. Required columns: FiscalYear, StartsOnInclusive
2. Table is not time versioned, and uploaded to the initial time period.
3. Validation for column and format is done on successful upload of the calendar file.
4. The table should have the first period of year n + 1, to calculate the end of year n.
5. If you want to fix errors to an checked-in calendar table, revert you time setting
   check-in.

   Eg Calendar table.

   | Fiscal Year | Starts On Inclusive |
   | --- | --- |
   | 2021 | 2021-02-04 |
   | 2021 | 2021-03-04 |
   | 2021 | 2021-04-08 |
   | 2021 | 2021-05-06 |
   | 2021 | 2021-06-03 |
   | 2021 | 2021-07-08 |
   | 2021 | 2021-08-05 |
   | 2021 | 2021-09-02 |
   | 2021 | 2021-10-07 |
   | 2021 | 2021-11-04 |
   | 2021 | 2021-12-02 |
   | 2021 | 2022-01-06 |
   | 2022 | 2022-02-03 |

Notes:

- Can only migrate to Custom Calendar at the End of Year boundary and before any data is uploaded
  or config changes are made in the next year.
- If data has been uploaded or config changes made, they will need to be reverted.
- Customers who are using a non-Gregorian calendar (e.g., 445, 454, 544 or 13 period), should
  begin planning for the transition prior to year end.

## Fiscal Year Definition - 13 Period (444)

The fields for 13-Period (444) calendars are described below.

- Calendar Type - Select the 13-Period (444) calendar type. The numbers
  represent the number of weeks in each of the periods in the fiscal year: 4 weeks, 4 weeks, 4
  weeks.
- The Fiscal Year is Defined By - Select Starting
  Period or Ending Period. If you select Starting
  Period, the fiscal year is based on the first peri of the calendar. If you select
  Ending Period, the fiscal year is based on the last period in the calendar.
  - For example, suppose you have a fiscal year that runs from June 2016 to May 2017. If you select
    Starting Period, the fiscal year will be 2016. If you select
    Ending Period, the fiscal year will be 2017.
- The Fiscal Calendar - Use the four fields in this section to define the
  starting or ending day of the fiscal calendar. Select values from each of the drop-down lists.
- The Quarter with 4 Periods is the Fourth - In a 13-period calendar, three
  quarters have three periods each. The fourth quarter has four periods. Select the quarter that will
  have four periods.In the example below, the first quarter has four periods:![](../../resources/images/studio_images/studioimages/studio/stu179.png)

Note: The upcoming, centralized Fiscal Calendar Service (FCS), will use a similar uploaded
table as the Custom Calendar configuration. TBM Studio > Time
Settings will no longer be used to manage updates to the fiscal calendar. Instead, the
table will be uploaded and managed in FCS and will work with other Apptio Products as they integrate
with FCS.

## Project Time Span Definition

The Project Time Span Definition fields are described below.

- Start of Project - Click on the field and select a month and year for the
  start date of the project. Use the arrows on the left and right margins of the date picker to move
  between years.

  Note: Once you save the start date of a project, you cannot change it. The
  Start of Project field is also used to select viewable periods of time, see
  [Viewable Periods of Time](#Configureprojecttimesettings__ViewablePeriodsofTime)
- End of Project - Click on the field and select a month and year for the
  end date of the project. Use the arrows on the left and right margins of the date picker to move
  between years. You can change this date at any time.
- When setting the end date, keep in mind that the application runs calculations out to the end
  date. The more months that need to be calculated, the longer the calculations take. For this reason,
  it is best to set the project end date out far enough to cover planning and forecasting needs but
  not so far that it causes unnecessary calculations.
- Enable Default Time Period - When checked, the option activates the
  Default Time Period field.
- Default Time Period - The period you select will be the default time
  period displayed for all users when they open a project. You can select a period, quarter, half, or
  full year. The users can change the time period using the date picker. Setting the default time
  period is useful for time-dependent projects like budgeting and forecasting.
- If you do not set a default time period, when a user opens a project, the last active time
  period is displayed.

## Viewable Periods of Time

Select the periods that will be displayed in the date picker. This will be months for Gregorian
calendars and periods for all other calendar types. You must select at least one option from the
group, but you also can select any combination of options. For example, you can select just months,
months and quarters, or quarters and half years. You can change this setting at any time.

To select a month or period, use the following Project Time Span
Definition fields:

- Start of Project - Click on the field and select a month and year for the
  period of time you want to view. Use the arrows on the left and right margins of the date picker to
  move between years.
- End of Project - Click on the field and select a month and year for the
  period of time you want to view. Use the arrows on the left and right margins of the date picker to
  move between years.

The periods you select control the periods included in pre-processing. Years will take less time
to process than halves or quarters. You can select any combination of the three. Monthly/period
calculations are performed by default. If users will be viewing reports for months or periods only,
do not select these options.

## Editable Periods

There may be projects where you will want to close data entry for certain periods. For example,
if you are doing budgeting, you may want to close the current budgeting period after the budget has
been finalized. In the date picker, the names of the closed periods are displayed in italics and the
bar across the top of the period is gray. In the example below, January, February, and March are
closed:

![](../../resources/images/studio_images/studioimages/studio/stu180.png)

Using the Closed Periods field, you can select the periods to close. Click
on the field to display a date picker where you can select months or periods, quarters, half years,
or full years. This setting closes the period for data sets, data entry through editable tables on
reports, and allocation mapping grids in models. You can change this setting at any time.
