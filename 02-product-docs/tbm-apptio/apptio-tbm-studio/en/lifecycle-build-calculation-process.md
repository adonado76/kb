---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Build and Calculation Process"
breadcrumb:
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
  - "Build and Calculation Process"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/build-calc.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Build and Calculation Process

A "build" in TBM Studio refers to the process of calculating all transforms, metrics, drills, and reports for a given environment. Understanding what triggers builds and how they queue helps you plan your work effectively.

What Triggers a Build

Builds are triggered by different actions depending on the environment:

| Environment | Trigger | What Calculates |
| --- | --- | --- |
| Environment | Trigger | What Calculates |
| Development | Save (with Auto Calculate enabled) | Transforms and Metrics |
| Staging | Check-in of any document | Transforms, Metrics, Drills, Reports |
| Production | Promotion from Staging | Receives calculated build (no recalculation) |

Calculation Data Flow

Understanding the calculation data flow helps diagnose issues when builds fail or produce unexpected results. The general flow is:

1. Data Tables: Raw data is uploaded or imported.
1. Transform Steps: Data is cleaned, mapped, joined, and enriched.
1. Master Datasets: Unified tables (e.g., Cost Source Master) combine GL, Budget, and Forecast data.
1. Model Objects: Model references these unified transform tables.
1. Allocations: Metrics propagate downstream through the allocation chain.
1. Reports: Calculated values are rendered in reports.

Key Behavior: The model cannot calculate unless transform tables pass validation. Errors in upstream transforms will block model-layer logic. Always resolve transform errors before expecting model calculations to complete.

Monitoring the Calculation Queue

The Calculation Queue shows what has been calculated (with duration), what is currently calculating, and what is waiting. To view it:

1. In TBM Studio, select the Build tab.
1. Click Calculation Queue.

When multiple check-ins occur over a short period, they may batch into a single calculation. If a calculation is already running, subsequent check-ins are queued for the next calculation. For long-running Stage calculations, consider using the Cancel Build feature (v.12.3.1+) to cancel the running build, so pending changes can be included in the next build.

Coordinate check-ins with your team. If everyone checks in at the same time (e.g., end of day), changes batch into one calculation rather than queuing multiple sequential calculations.
