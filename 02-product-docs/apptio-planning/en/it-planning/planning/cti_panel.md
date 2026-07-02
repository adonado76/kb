---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Working with Cost Transparency Integration Panel"
breadcrumb: []
source_path: "it-planning/planning/cti_panel.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Working with Cost Transparency Integration Panel

The updated Cost Transparency Integration (CTI) panel, introduced
in Planning release 2.78, is a self-contained space where admin users can
perform all Cost Transparency Integration tasks within a single control
panel. The new panel provides centralized management and one-click import and export with Cost
Transparency.

## Access CTI panel

The Cost Transparency Integration panel allows you to perform all CTI tasks, which are divided
into separate pages. The following sections of this topic describe the contents of each page and the
corresponding tasks that can be performed.

1. Log in to Planning.
2. Open the Settings menu.
3. Click Cost Transparency Integration.

## Configure CTI panel

This option contains the configuration settings for the CTI. This setup process is usually
completed by Apptio delivery team members on initial set-up, and is rarely modified afterwards.

No changes have been made to the configuration page from prior product versions. For more
information on that configuration process, see [Integrate with Costing Standard](integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.").

## Import Actuals

The Import Actuals task is performed by a TBMA (usually once per month) to import Actual spend
data from Costing Standard into Planning. Use the
imported Actuals to form forecasts, perform variance analysis, and create other comparison
views.

1. On the Import Actuals CTI page, select the months for which you want to import Actuals.

   If
   multiple months are chosen, a bulk import will be performed.
2. Once all months have been selected, click the blue Import button.

A message is displayed that recommends going to the Status page and checking on your job’s
status. For the Import Actuals process, go to the Status page.

You may also return to the CTI home page to continue with other CTI tasks. You are not blocked
from performing other Planning and CTI tasks, even if a large or lengthy
import job is in progress.

## Import Reference Data

PlannPlanninging uses Reference data as baseline information for planning
purposes, and includes such information as Chart of Accounts, department hierarchy, or lists of cost
centers and vendors. The Import Reference Data page allows you to pull reference data from Costing Standard into Planning.

1. Select the reference data you want to import from the list.
2. Scroll to the bottom of the page, and click the Import button.

All reference data sets are selected by default, supporting bulk import.

A pop-up is displayed that recommends going to the Status page and checking on your job’s status.
To finish the Import Reference Data process, you must go to the Status page and publish the imported
data when the job is complete.

Note: It is recommended you review the data you uploaded if any major changes were made. Once you
publish the reference data there is no way to revert it.

You may also return to CTI Homepage to continue with other CTI tasks. You are not blocked from
performing other Planning and CTI tasks, even if a large or lengthy import
job is in progress.

## Publish to Costing Standard

The Costing Standard data model can accommodate only one budget and one
forecast for analysis. Consequently, only one of each plan type can be pushed from Planning to Costing Standard. Use the Publish to CT page
to determine and manually publish the appropriate plans to Cost Transparency.

1. Select a plan from the drop-down menu and select all line item types you wish to publish.
2. Click the blue Publish button when ready, and it will begin a publish job.

All line item types are selected by default.

A pop-up is displayed that recommends going to the Status page and checking on your job’s status.
However, the Publish to CT process does not require any follow-up tasks: you may find your imported
data in CT once the job is complete.

You may also return to CTI Homepage to continue with other CTI tasks. You are not blocked from
performing other ITP and CTI tasks even if a large or lengthy import job is in progress.

## Status

You can access this page at any time to display the status of every CTI job that has been
attempted, scheduled, or completed.

| Status | Description |
| --- | --- |
| Start & End | The start and end times for the corresponding job. |
| Initiated By | The email of the user that initiated the job. |
| Status | The progress of the job: QUEUE, SUCCESS, SUCCESS WITH WARNINGS, or FAIL. |
| Actions | Follow-up actions that must be performed:  • Publish data once Import jobs are successful (for example, Publish reference data after import).  • View to find and download error logs for failed jobs. |
