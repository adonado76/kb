---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Labor Activity Over/Under Allocation Analysis"
breadcrumb: []
source_path: "planning/iip/manage-over-under-allocation.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Activity Over/Under Allocation Analysis

Allocated labor represents a major portion of Project/Investment expense. Understanding
utilization of labor on project is very important to understand available capacity vs demand, making
hiring decisions to support increased demand, stopping non-critical projects when the increased
demand can’t be met through available budget. It also helps identify underutilized workforce and
make allocation decisions where their available capacity can be optimally utilized.

In many cases, resource cost center and project cost centers are different, and one labor
resource might be working on multiple projects, making the capacity vs demand analysis even more
complicated. This results in a mismatch between capacity and demand leading to loss of available
resource hours when under allocated and delays in project schedules when the labor resources are
over allocated than actual capacity during the planning cycle due to false representation of actual
capacity. It is hard to get visibility into total demand for various roles across the company vs
available capacity and how much funds to allocate for the planned labor during the budget
planning.

Integrated Investment Planning solves this challenge by introducing capabilities to completely
prevent overallocation of resources or set up over allocation and under allocation thresholds and
identify the resource allocations that don’t meet the set threshold.

## Labor Capacity

Every labor resource is assigned a working calendar that defines the working schedule for the
labor. Please visit [Calendar Setup](../configure-working-days.htm "(Opens in a new tab or window)") to learn more about working calendar.

Labor data in Expenses > Labor defines the start date, end date and monthly FTE
capacity for the labor. Following formula is used to calculate hourly labor capacity.

Monthly Capacity = Monthly working days x Daily working hours X Monthly labor quantity

Please see the example below to better understand capacity calculation:

Fiscal calendar type - Gregorian

Working Calendar

![](../../../resources/images/it%20planning_images/working-calendar.png)

Expenses Labor

![](../../../resources/images/it%20planning_images/exp-labor_956x97.png)

Working Capacity for John in January 2024

January working days = Working Days - Holiday

= 23-1

Working Hours in January = January working days x Daily working hours

= 22 x 8 = 176

Expenses > Labor in January = 0.5

Monthly capacity = 176 x 0.5 = 88 hours
