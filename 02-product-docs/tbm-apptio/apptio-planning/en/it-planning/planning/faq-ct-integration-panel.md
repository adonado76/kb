---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "FAQ: Cost Transparency Integration Panel"
breadcrumb:
  - "Planning"
  - "Troubleshooting and FAQs"
source_path: "it-planning/planning/faq-ct-integration-panel.html"
images:
  - "resources/planning_images/faq-ct-integration-panel-1_700x182.png"
  - "resources/planning_images/faq-ct-integration-panel-2_700x471.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# FAQ: Cost Transparency Integration Panel

This list of frequently asked questions about how the Cost Transparency Integration (CTI)
panel, introduced in Planning release 2.78. The CTI panel is a self-contained space where Admin
users can perform all Cost Transparency Integration tasks within a single control panel. The new
panel provides centralized management and one-click import and export with Costing Standard.

In this FAQ:

[Q. How do I turn on the new functionality?](#FAQCostTransparencyIntegrationPanel__Q.)

[Q. What tasks can I perform through CTI Panel?](#FAQCostTransparencyIntegrationPanel__Q.2)

[Q. What role/permissions are needed to access the new panel?](#FAQCostTransparencyIntegrationPanel__Q.3)

[Q. Can I import Actuals for more than one month at a time?](#FAQCostTransparencyIntegrationPanel__Q.4)

[Q. Can I perform other ITP tasks when my CTI jobs are queued or
running?](#FAQCostTransparencyIntegrationPanel__Q.5)

[Q. Can I see a detailed status of my job?](#FAQCostTransparencyIntegrationPanel__Q.6)

[Q. Is there an order of operations when importing reference data in
bulk?](#FAQCostTransparencyIntegrationPanel__Q.7)

[Q. If one of the reference datasets fails to load, will the whole job
fail?](#FAQCostTransparencyIntegrationPanel__Q.8)

[Q. Where do I publish my reference data?](#FAQCostTransparencyIntegrationPanel__Q.9)

[Q. Where do I verify what I loaded is correct and what I
expected?](#FAQCostTransparencyIntegrationPanel__Q.10)

[Q. Does the new CTI panel replace any of the existing CTI functionality and
process?](#FAQCostTransparencyIntegrationPanel__Q.11)

[Q. Does the CTI Status page list only the jobs that are scheduled using the
Cost Transparency Integration Panel?](#FAQCostTransparencyIntegrationPanel__Q.12)

## Q. How do I turn on the new functionality?

A. New functionality is ON by default. To access the enhanced CTI
functionality, from the Settings menu, click Cost
Transparency Integration.

## Q. What tasks can I perform through CTI Panel?

A. The following tasks can be performed through CTI Panel:

- Configure CT integration settings.
- Import Actuals from CT.
- Import Reference Data from CT and publish it to the plan.
- Publish plan data from ITP to CT.
- View Status of all CTI jobs.

## Q. What role/permissions are needed to access the new panel?

A. Admins. No changes are made with respect to permissions from the
existing CTI roles.

## Q. Can I import Actuals for more than one month at a time?

A. Yes. Use the calendar picker to specify a period. Select the start and
end months. To select just one month, select the start and end months to be the same.

![image](../../../../../03-media/apptio-planning/resources/planning_images/faq-ct-integration-panel-1_700x182.png)

## Q. Can I perform other ITP tasks when my CTI jobs are queued or running?

A. Yes. You are not prevented from performing any CTI or ITP related tasks
when a job is queued or running. You can access the Status page at any time
to view the status of every CTI job that has been attempted, scheduled, or completed.

## Q. Can I see a detailed status of my job?

A. Yes. From the Status page, click the arrow icon
to expand. You can view list of sub-tasks.

You can access this page at any time to display the status of CTI jobs and their sub-tasks that
have been attempted, scheduled, or completed.

We only display the 100 most recent jobs less than 31 days old.

![image](../../../../../03-media/apptio-planning/resources/planning_images/faq-ct-integration-panel-2_700x471.png)

## Q. Is there an order of operations when importing reference data in bulk?

A. For information on the recommended order for importing reference data,
see: [Reference Table Dependencies Diagram](https://community.ibm.com/community/user/viewdocument/reference-table-dependencies-diagra?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Opens in a new tab or window)").

## Q. If one of the reference datasets fails to load, will the whole job fail?

A. No. Even if one of the subtasks fails to load, the
CTI\_IMPORT\_REF\_DATA\_IMPORT job will still pass with warnings. A Warning status message is displayed.
To access the error logs for the sub-tasks that failed, expand the job, and under
Actions, click View Log.

## Q. Where do I publish my reference data?

A. To publish reference data, from the Status page, under
Actions, click Publish. The
Publish button is not displayed if the import job status is
Failed. It will be displayed only for Success and
Warning states. After the reference data is published, the button text
changes to Published and the button is disabled.

NOTICE

When a job with Warning status is published, only the job tasks that were
successful are published. Failed jobs are ignored and are not published.

## Q. Where do I verify what I loaded is correct and what I expected?

A. You can verify the upload before publishing. Navigate to the reference
data page, and click into the relevant dataset.

## Q. Does the new CTI panel replace any of the existing CTI functionality and process?

A. No. This enhanced CTI panel is used alongside the existing
functionality.

## Q. Does the CTI Status page list only the jobs that are scheduled using the Cost Transparency Integration Panel?

A. Yes. CTI activities performed outside the new CTI panel are not tracked
and will not be listed on the CTI Status page.

For more information see: [Cost Transparency Integration Panel](cti_panel.html "The updated Cost Transparency Integration (CTI) panel, introduced in Planning release 2.78, is a self-contained space where admin users can perform all Cost Transparency Integration tasks within a single control panel. The new panel provides centralized management and one-click import and export with Cost Transparency.").
