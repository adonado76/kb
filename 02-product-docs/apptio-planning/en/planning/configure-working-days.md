---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Working calendar"
breadcrumb: []
source_path: "planning/configure-working-days.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Working calendar

Working calendar is critical to build an effective financial model that accurately reflects the
monthly working hours for the full-time and part -time labor, provides flexibility to amortize the
labor compensation as per working calendar and allows to accurately expense the monthly labor
allocation to projects and investments.

Apptio Planning offers flexibility to configure either a fix month working calendar or a variable
month working calendar. It also supports configuring multiple working calendar as per the working
profiles full-time, part-time, global holiday schedule etc.

- Fixed Calendar – If your organization defines a standardized working month with fixed
  monthly hours throughout the year for the labor expense budgeting and forecasting, this calendar
  will be most suitable for you.
- Variable Calendar – If the budgeting and forecasting practice at your organization
  considers the actual calendar month and define a working week (5 day working week, 6 day working
  week etc.) as well as holidays and non-working days and then arrive at the actual working month,
  this calendar will be most suitable for you.

## Variable Working Calendar Configuration

1. Navigate to Configuration > Calendar Setup. For a first time user, a default
   Variable Calendar is selected.

   ![](../../resources/images/it%20planning_images/wc-main_1283x858.png)
2. Select the Add button and choose the Variable Calendar option.

   ![](../../resources/images/it%20planning_images/add-cal.png)
3. Enter a name for the calendar. The Add and Add Another buttons are
   enabled.

   ![](../../resources/images/it%20planning_images/add-cal-2.png)
4. Select the Add button. The variable calendar is added as shown.

   ![](../../resources/images/it%20planning_images/add-cal-1_914x753.png)

   Note: To see and mark a
   calendar as default, hover your cursor over it to see the Mark as default link.
5. Select the Edit icon next to the newly added calendar. The working days section on the
   right side is enabled.
6. ![](../../resources/images/it%20planning_images/add-cal-3_931x570.png)

   - To set Working Days, select the checkbox under the day you want to set as a working
     day.
   - To set the Working hours per day, enter the number of hours in the textbox. For example,
     for an eight-hour working day, enter 8.
   - Set specific dates as non-working days
   - To set Non-working days, select Edit.
     - Select Year.
     - Specify a Name and a Date for the non-working day.
     - Continue to add all non-working days you want to configure and then select the Save
       button.
     - A warning message "Updating the Working Calendar will impact the Hours to FTE conversion, labor
       financials utilizing the working calendar, and all calculated labor activity financials"
       appears.
   - Note: If you configure a non-working day which is already set as a non-working day by default (such
     as a weekend day), this has no affect on the amortization schedule.

## Fixed Working Calendar Configuration

1. Navigate to Configuration > Calendar Setup and select Add button.
2. Select the Fixed Calendar option.

   ![](../../resources/images/it%20planning_images/fc-1_795x314.png)
3. Enter a name for the calendar and select the Add button. The fixed calendar is added as
   shown.

   ![](../../resources/images/it%20planning_images/fix-cal-2_798x586.png)
4. Select the Edit icon to enable the working days section on the right side.

   ![](../../resources/images/it%20planning_images/fix-cal-3_803x589.png)
5. Enter the number of hours in the Working hours per month textbox. For example, for an
   eight-hour per day of 21 working days, enter 168.
6. Select the Save button.

## Assigning Working Calendar for Labor Expense Amortization

To use working calendar days to amortize the monthly labor expenses update the Labor Amortization
Method in the Labor Allocation Rules and publish the change. To learn more, see [Labor Allocation
Rules.](manage-labor-allocation-rules.htm "(Opens in a new tab or window)")

![](../../resources/images/it%20planning_images/wc-1_1456x341.png)

## Assigning Working Calendar On the Labor Expense Lines

- Default working calendar gets automatically assigned to the Labor lines.
- If there are multiple-working calendar, the user needs to select appropriate working calendar
  for the entered labor data.

  ![](../../resources/images/it%20planning_images/wc-2_1094x412.png)

  ![](../../resources/images/it%20planning_images/wc-3_1104x294.png)

Note:

- Default working day calendar configuration consists of five working days (Monday to Friday) and
  eight hours per day without any additional holidays or non-working days which can be further
  customized as well as more calendar configuration can also be added.
- Default working day calendar configuration consists of five working days (Monday to Friday) and
  eight hours per day without any additional holidays or non-working days which can be further
  customized as well as more calendar configuration can also be added.
- There must be at least one default working calendar.
- FTE to Hours conversion on the Expenses > Labor Activity is done as per the
  working calendar assigned for the selected labor resource.
- Working calendar is a global configuration, so it is applicable to all the plans in the
  environment.
- Any change to working days, hours per day, or non-working days will affect the Hours to FTEs
  conversion, Labor financials linked to working calendar, and all the Labor Activity financials.
