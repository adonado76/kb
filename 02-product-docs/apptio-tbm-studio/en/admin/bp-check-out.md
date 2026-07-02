---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Best practices: Check out and check in"
breadcrumb: []
source_path: "admin/bp-check-out.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Best practices: Check out and check in

◆ Applies to: Apptio TBM Studio 12.x and later. In Apptio TBM Studio R12, all elements
are documents, including data tables, metrics, perspectives, and models. To edit a document, you
must first check it out. When you check out a document, it is locked so that others cannot edit it.
You can save your changes to the document without triggering a recalculation. When you finish
editing a document, you can check it in. Checking in a document triggers a recalculation. Others
will now see the changes you made to the document when the dev mode calculation is complete and
their workspace is updated. Also, others will now be able to check out this document.

The information below details document check out, check in, and recommended best practices to
follow for an optimal experience.

## Check out

To check out a document, follow these steps:

1. Select the document in Project Explorer.
2. On the Home tab, in the Document group, select Check Out![](../../resources/images/studio_images/checkout1.png).
3. When you check out a document, a check out icon appears next to the document name, and the
   document name is displayed in orange text in the tab at the bottom of the workspace.![](../../resources/images/studio_images/checkout.png)

## Undo, redo, and revert

Sometimes, when you are editing documents in your workspace, you might want to return to a
previous version, or redo it. When documents are checked out, you can use three options to achieve this:

- Undo
- Redo
- Revert Change

Undo and redo are useful for rolling back small, discrete changes to configuration, such as the following:

- Positioning of reporting elements within a report
- Discrete edits to the configuration of reporting elements (for example: button text, HTML
  contents, and so forth)
- Edits to formulas for columns in a table's formula step

## Revert

You can find undo and redo on the Home tab, Changes group. Revert abandons all
changes you made to checked-out documents you select and then discards the check out. To revert,
follow these steps:

1. On the Home tab, in the Document group, click Revert Changes.
2. Select the checkbox next to documents you want to revert and click Revert Check Out.

## Checkin

Examine performance reports

When evaluating the health of the
system after making changes to data or configuration, it is useful to examine reports that are
designed to assess potential performance issues.

Note: Upcoming versions of TBM Studio will have reports specifically designed to assess the
performance impacts of changes. When those reports become available, this document will be updated
to provide specific guidance. However, until those reports are available, you simply choose a report
known to exercise the system well. If you aren't sure which report to use, consult with your CSM or
Apptio Support.

## Confirm data load is good

The guiding principle of Project Workspaces is that this area is your development environment.
You should be very confident of the data and configuration within that area before checking in data.
Use the following checklist before you check in documents and after you have carried out a data
upload.

## Document check in checklist

- Review data before uploading it to your workspace (for example, confirm the file has content, is
  correctly delimited, and so forth).
- Ensure that data tables have data and that cardinality validation is enabled.
- Click Save on the changed data table.
- Validate columns (for example, the addition of columns or renaming of columns) and types (see
  [Additional resources](#BestpracticesCheckoutandcheckin__addresources)).
- If columns are missing, determine what effect that this will have on configuration.
- Check the overall quality of the data (for example, is there data missing, do the numeric column
  totals look sensible) and build your own validation routine around this point.
- Look at a report that is directly associated with the data and ensure that nothing odd has
  occurred.
- Browse to the [Performance reports](#BestpracticesCheckoutandcheckin__perfreports) and verify that they
  respond well.
- **If the reports do not respond well or issues are indicated, resolve the issues prior to check
  in.**
- Coordinate and agree with colleagues when to check in data and ensure that no one is waiting to
  promote from Stage to Production.

## Datalink (Classic) considerations

When using Datalink (Classic), the following applies in addition to the points above:

- When Datalink (Classic) uploads a document, that document is uploaded into a Datalink (Classic)
  workspace and is then *immediately* checked in.
  - Consider using Datalink (Classic) connector groups to manage large sets of uploads. Using a
    connector group will result in a single check in for the group vs. individual check ins for each
    load. For more information, see [Group multiple connectors](../../datalink-classic/datalink/group-connectors.html "(Opens in a new tab or window)").
- If there are validation issues, the document will be held in the Datalink (Classic) workspace
  until the validation errors are resolved and the document is manually checked in.

## Confirm configuration changes

As with data loads, take care before checking in configuration changes. Use the following
checklist before checking in configuration changes. For guidance on ways to accelerate your
validation, see [Validation technique tips](#BestpracticesCheckoutandcheckin__validation).

## Checklist

- Click Save when you finish modifying any document.
- Resolve any errors by selecting the numbers displayed next to data tables, for example:![](../../resources/images/studio_images/checkin-errors.png)
- Validate how data and configuration changes have affected allocations.
- Validate how data and configuration changes have affected reports.
- Check the Allocation Ratios size of Modeled Tables within each Modeled Metric associated with
  that table.
- Verify that any reports you have worked on respond when viewed. If a report does not load as
  expected, then it might indicate a configuration issue (for example, if the report never loads, or
  if it loads after a VERY long time). If you think it is a browser issue, you can refresh your
  browser and then go back to the report and ensure that it loads correctly. If it does not load
  correctly, address the issue prior to a check in.
- Browse to the [Performance reports](#BestpracticesCheckoutandcheckin__perfreports) and verify that they
  respond well. If the reports do not respond well or issues are indicated, resolve the issues prior
  to a check in.
- Coordinate and agree with colleagues about when to check in documents and ensure that no one is
  waiting to promote from Stage to Production.

## Check in a project

When numerous people are working on a single project with the potential for multiple document
check ins the same day, follow these guidelines to control what is calculated and when. This step
should be a part of any customer's Software Development Lifecycle (SDLC) process. It is worth
recapping what happens after a check in. The activities in each environment within a single Apptio
project when a check-in occurs:

- Development — A check in triggers the dev calc node(s) to process:
  - Transforms
  - Metrics
- Stage — A check in triggers stage calc node provisioning, which can take up to 15
  minutes, and once provisioned, the stage calc nodes calculate the following after the calc in dev
  has completed:
- - Drills
  - Reports

    Note: When multiple check in events occur over a sufficiently long period of time (for
    example, a few minutes), this might result in more than one calculation event. When a calculation is
    in motion, any subsequent check ins will be included in the next calculation event. Solutions to
    this are provided later in this document.
- Production — A publish to production can only be executed after all pending stage
  calculations have been completed. Publication to prod in v.12 is almost instantaneous.

## Control calculations

When you check in data, config, or report changes, it triggers calculations in development and
stage. This will cause workload on the environment. Until the stage calculation is complete, users'
browsing stage will receive a warning that the environment is out of date. A promotion to production
will not be possible until all stage calculations are complete.

## Establish a check in policy

It is recommended that the wider TBMA team determines a check in policy at the start of the
project and revises it as needed. The following guidelines have proven to be successful in other
Apptio v.12 implementations:

- Coordinate the check in to occur once or twice per day (for example, at lunch and at the end of
  the day).
- If a project has a longer stage calculation time, then coordinate the check in across the team
  to take place at the same time. This will help limit the possibility of two stage calculations
  taking place. *If you get queued calculations anyway,* see [Limit
  calculation time](#BestpracticesCheckoutandcheckin__limitcalc) to limit the calculation time.
- If there is a requirement to publish to production, lock stage when all agreed check ins have
  completed to avoid another check in occurring before the publish to production has taken place.

## View the calculation status

So far, we have discussed 1) what happens when you click check in, 2) what you should do before
you click check in, and 3) when should you click check in. This section explains what is happening
after a check in. The calculation queue shows what has been calculated (and how long it
took), what is being calculated, and what is waiting to be calculated. To view the Calculation Queue:

1. In the TBM Studio menu, select the Build tab.
2. Click Calculation Queue.

This shows the latest build for each environment, and displays the builds that have finished
calculating, are actively calculating, and have finished calculating. [Learn more about the
Calculation Queue](monitor-builds-calculation.html "(Opens in a new tab or window)")

## Limit calculation time

If a calculation is in motion and subsequent check ins occur, then those changes will become
queued until the running calculation finishes. If your stage calc time is long, you may want to
consider using the Cancel Build feature (v.12.3.1+) to cancel the running build so that the pending
changes are included in the next build. For more information, see [Cancel an
in-progress calculation](https://community.apptio.com/docs/DOC-8376 "(Opens in a new tab or window)").

## View check in history

To see a history of who has checked in a specific document, follow these steps:

1. Select the document in Project Explorer.
2. Right-click the tab at the bottom of the workspace and select Check In History:![](../../resources/images/studio_images/check-in-tab.png)
3. A table appears showing the date, user, status, description and any message included with the
   check-in.![](../../resources/images/studio_images/changehist.png)
4. To return to the document view, right-click the tab again and select Show Document.

## Rollback

Beginning with v.12.2.2, you can rollback changes made in a project from a specific change. All
changes made after the specific change will be reverted. However, there are some important
considerations prior to using this feature. For more information, see [Roll back a
configuration](roll-back-configuration.html "(Opens in a new tab or window)").

## Lock and promote a project

Locking and promoting is covered in [Lock and promote a project](lock-promote-project.htm "(Opens in a new tab or window)").

## Validation techniques

One way to speed up validation is to have *two* browser tabs open: one tab with what you see
in your workspace, and one tab with what is visible in the current stage build. This is most useful
when there are configuration changes but no data changes, and when there are no pending stage
calculations. However, it can be useful under other circumstances too. To use two browser tabs:

1. Navigate to the document you are validating (table, report, model, and so forth).
2. Open another tab, and navigate to the same document in stage, prod, and so forth.
3. Some browsers such as Chrome have a Duplicate Tab option when you right click on an open browser
   tab. This can speed up creating a new tab by not having to repeat the navigation to Enhanced Access
   Administration, and so forth.
4. Hold down Ctrl and click the tab button. This should toggle between the two open
   tabs. This allows you to rapidly assess differences between the views.

Additional resources

- Locate and Fix Data Validity Issues: [Locate and fix data validity issues](https://community.apptio.com/docs/DOC-6790 "(Opens in a new tab or window)")
- Data Validation Videos: [Data Validation (v.12)](https://community.apptio.com/videos/1305 "(Opens in a new tab or window)")
