---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Monitor builds with the Calculation Queue"
breadcrumb: []
source_path: "studio/admin/monitor-builds-calculation.html"
images:
  - "resources/images/studio_images/build-tab.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Monitor builds with the Calculation Queue

◆ Applies to: TBM Studio 12.2 and later. Use the Calculation Queue table to monitor the
state of the builds for the environments (Development, Staging, and Production) in your
domain.

You can access the Calculation Queue from the **Build** tab.![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/build-tab.png)

A build automatically starts in the Development and Staging environments any time a user checks
in a document. The build incorporates all checked-in documents since the last build and updates all
of the calculated numbers in the project.

Builds in the Development and Staging environments can take place concurrently, but running them
at the same time can result in a delay between the two builds and the build numbers that do not
match. In addition, the build number for the Production environment might be significantly different
depending on how often the Staging environment is promoted to the Production environment.

## Understand the columns in the table

The **Status** column displays one of following statuses:

- **Pending** - A build is queued and waiting to be processed.
- **Calculating** - A build is in progress. Displayed next to this status is the number of
  calculations completed versus the total number of calculations. In the example above, 140
  calculations out of 6,337 are completed.
- **Finished** - The build is complete. Displayed next to this status is the length of time
  since the build finished, and in parentheses, the duration of the build.

The **Changes** column lists all of the check-ins processed during the build.

To sort the table by the values in a column, select the column header then select a sort
option.

To only display rows with a certain value in a column, enter the text in the search field below
each column header.

Note: If you are in the Welcome project, the Calculation Queue does not list the
environments (Development, Staging, and Production) at the top of the Calculation Queue because the
Welcome project does not have environments.

## Frequently Asked Questions

**What is Precision
Calc?**

Precision Calculation is a new performance improvement that reduces the calculation time
for changes that have been checked-in. Precision Calculation uses lineage information to better
understand the specific calculation impacts based on the types of changes made: e.g., table uploads,
data scheme changes, transforms, calculated metrics, perspectives, reports, project settings, etc..
In the Calculation Queue feature, Administrators will see:

- Faster calculation times then before Precision Calculations
- Greater variation in calculation times for different builds.

**How do you enable this feature?**

This feature is automatically enabled for all
customers beginning with the Server 12.10.10.1 release.

**How quickly does it calculate the
time?**

Builds with "report only" changes or changes that do not affect the calculation
model will complete in seconds. Builds with other types of changes will calculate and complete
faster than before. Precision Calculation will not reduce the time for a full calculation that is
required after an instance reset with cache clear.

**Will making UI config changes affect the
optimizations?**

Making the following UI changes will not impact the data being calculated

- Change Color Spec
- Change Default Page size
- Toggle Enable Application Tabs
- Toggle auto-calculation workspace
- Toggle Enable Mandatory Checkin-descriptions
- Closing / Reduce number of calculated Periods
- Making a Project Setting change to Enable Apex UI

**How does it optimize calculations?**

Server will optimize calculations to
only process those areas impacted by the checked-in changes

**How can I optimize this
feature?**

Replace the use of [Eval()](../formulas-and-functions/functions/eval.htm "(Opens in a new tab or window)") function with [DynamicColumn()](../formulas-and-functions/functions/dynamic-column.htm "(Opens in a new tab or window)") function to benefit from the Precision Calc performance
improvements.

To maximize the calc performance improvements of the new "precision
calculations" feature, the functionality of the Eval() function is replaced with DynamicColumn() or
other code changes. The customers that still have Eval() in their project configuration, can make
the necessary changes using the [OOTB Eval() replacement code](../formulas-and-functions/updated-eval-formulas.htm "(Opens in a new tab or window)") document that has information of
all the reports and metric changes.

Note: NOTICE: If you have modified the OOTB reports, the Eval()
will not be removed from reports in earlier templates (e.g. ,v104, v105, v106.
v107).
