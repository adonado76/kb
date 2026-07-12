---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Saved Views"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Report Viewer"
  - "Saved Views"
source_path: "SSWRJM/studio/report-studio/saved-views.html"
images:
  - "03-media/apptio-tbm-studio/sv-qs.png"
  - "03-media/apptio-tbm-studio/sv-create.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Saved Views

## Overview

Saved Views allow users to create personalized snapshots of a report in the Report Viewer. A saved view captures the current state of the report, including filters and interactions applied to the report.

## Quick Start

Use Saved Views to personalize how you view reports.

You can:

- Create a saved view after applying filters or interactions.
- Maintain multiple views of the same report for different analysis needs.
- Set a landing view so the report opens with your preferred configuration.
- Bookmark the view URL to quickly access a saved view later.

Each user can create up to 5 saved views per report.

## Creating a Saved View

1. Open a report in the Report Viewer.
1. Apply the desired filters or interactions.
1. Click the Eye icon on the action bar at the top of the report.
1. Select Save View . A dialog appears where you can enter: View Name Optional description Option to Set as Landing View
1. The view is created and you are automatically navigated to the newly created view.

## Updating or Creating Additional Views

Save View

When you are currently on a saved view:

- Clicking Save View updates the current view with the latest report interactions and filters.
- Use this option to create a saved view for the first time for a given report.

Save View As

Use Save View As to create a new view based on the current report state.

Steps:

1. Modify filters or interactions on the report
1. Click the Eye icon
1. Select Save View As
1. Enter a new name for the view

This creates a separate saved view while keeping the original view unchanged.

Switching Between Views

To switch between views:

1. Click the Eye icon in the report toolbar.
1. Select a view from the list. The list includes:
1. The Default Report
1. All Saved Views created by you

Selecting a view loads that version of the report.

Managing Saved Views

Each saved view includes an overflow menu (three dots) that allows you to perform the following actions:

- View Details - See the name and description of the view.
- Edit - Modify the name or description of the view.
- Delete - Permanently remove the view.

Deleting a View

- If you delete the view, you are currently viewing, you will be redirected to the Landing View.
- If no landing view exists, you will be redirected to the Default Report.

Bookmarking Views

Each saved view has a unique URL that includes the view ID.

This allows you to:

- Bookmark the URL in your browser
- Share the link for your own future reference
- Return directly to the same report configuration

## Key Concepts

1. Default Report - The Default Report is the original version of the report as created by the report author/ admin. Appears in the Saved Views list with a home icon. Does not include any saved filters or interactions. Allows you to return to the base version of the report at any time.
1. Saved View - A Saved View is a personalized version of the report created by a user. It captures the current state of the report including: Applied filters Interactions with report visualizations The overall report state at the time the view is saved When you are viewing a saved view: The Eye icon in the toolbar appears bold. The report breadcrumb title includes the view name in parentheses. Example: Cost Analysis Report (Finance Department View) - Here the default report is the Cost Analysis Report, and the view is the Finance Department View
1. Landing View - A Landing View is the saved view that automatically opens when you access the report. Identified with a Star icon. Only one view per report can be set as the landing view for a user. Setting a landing view helps you start with your most frequently used report configuration.
1. Diverged View – A Diverged View occurs when the base report has been modified after the view was created. Because the report structure has changed, the saved view may no longer fully match the latest version of the report. A warning icon appears next to the view. A message indicates that the view has diverged from the base report.

Updating a Diverged View

To update a diverged view:

1. Open the diverged view
1. Click the overflow menu (three dots) for the view
1. Select Update from Base Report

Updating the view will:

- Synchronize it with the latest version of the report
- Remove all existing filters and interactions
- Reset the view to match the base report

Limits and Rules

- Saved views are available only in Production environments.
- Saved views are user-specific and cannot be seen by other users.
- Each user can create up to 5 saved views per report.
- Users cannot create additional views from a diverged view.
- Updating a diverged view removes existing filters and interactions.

## Icon Guide

| Icon | Meaning |
| --- | --- |
| Icon | Meaning |
| Eye icon | Access the Saved Views menu |
| Bold Eye icon | Indicates you are currently viewing a saved view |
| Home icon | Default report |
| Star icon | Landing view |
| Warning icon | View has diverged from the base report |
