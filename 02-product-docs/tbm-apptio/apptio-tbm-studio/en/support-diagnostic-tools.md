---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Diagnostic Tools"
breadcrumb:
  - "Troubleshooting and Support"
  - "Diagnostic Tools"
source_path: "SSWRJM/studio/new-uc/ts-support/diagnostic-tools.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Diagnostic Tools

*TBM Studio provides several tools for diagnosing performance issues, monitoring builds, and analyzing system behavior.*

## Calc Explorer

Calc Explorer enables administrators to analyze build performance and identify calculation-intensive components. Access via Build tab > Calc Explorer.

Key Definitions:

| Term | Description |
| --- | --- |
| Term | Description |
| Build | A specific point in check-in progression that can be calculated |
| Calc Type | All (full calc), Partial (dependent entities only), or None (no calc needed) |
| Calculation Effort | A measure of resources needed, shown in millions (e.g., 3.2M) |
| Query | The smallest unit of calculation, typically an entity for a specific time period |

Using the Sankey Diagram:

For "All" builds, Calc Explorer displays a Sankey diagram showing entities sized and sorted by Calculation Effort. Click on Reports entity to drill into top 10 reports. Hover over report names to see Calculation Effort percentages. Right-click to open documents or see full data paths. Continue drilling to identify specific problematic components.

## Calculation Queue

The Calculation Queue shows the status of builds across all environments. Access via Build tab > Calculation Queue.

| Status | Description |
| --- | --- |
| Status | Description |
| Pending | Build is queued and waiting to be processed |
| Calculating | Build in progress (shows completed vs. total calculations) |
| Finished | Build complete (shows time since completion and duration) |

## Errors Panel

The Errors Panel provides a consolidated view of all project errors. Access via Project tab > Errors. Review the list of errors, click on each to see details and navigate to the affected document. Errors block model calculation until resolved.

## Check-In History

Track changes made to documents over time. Select a document in Project Explorer, right-click the tab at the bottom, and select Check In History. View date, user, status, and messages for each check-in. From here, you can also rollback to a previous configuration if needed.
