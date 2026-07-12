---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Promotion Workflow"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
source_path: "studio/new-uc/concepts-architecture/promotion-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Promotion Workflow

Promotion is the process of moving validated content from the Staging environment to Production.
TBM Studio supports two promotion modes: on-demand and recurring.

**On-Demand Promotions**

On-demand promotion is the standard mode where administrators promote builds as needed. The
workflow is:

1. **Validate:** Administrator reviews and validates the current build in Staging.
2. **Lock:** Administrator locks the project to prevent new check-ins during promotion.
3. **Promote:** Administrator promotes using either Promote Now or Promote Later.
4. **Unlock:** Administrator unlocks the project to resume normal operations.

**Locking a Project:** When Stage is locked:

- Users can check out documents but cannot check them in
- The Environment dropdown displays "Locked" status
- Only administrators can promote to Production

To lock or unlock a project: Select the Staging environment, then on the Build tab, select Lock
(or Unlock if already locked).

**Promotion Options:**

|  |  |
| --- | --- |
| **Option** | **Behavior** |
| **Promote Now** | Immediately promotes the project. Disabled when unlocked or when another build is still running. |
| **Promote Later** | Schedules promotion for a specific time. Options include: promote as soon as build completes (not after specified time) or promote at specified time if build is complete. |
| **Force Promotion** | (v.12.11.0+) Promotes the last calculated build without locking Stage. Use for urgent updates when locking isn't practical. |

**Recurring Promotions**

Recurring promotion is an advanced mode for teams with established rhythms. It automatically
promotes at scheduled times. Prerequisites for using recurring promotions:

- Team has a well-established rhythm of check-ins and validation on a schedule
- Team wants Production updated on a known cadence for consumption
- Team members coordinate with each other about check-in timing

Important:

Locking cannot be used with recurring promotions. If the project is locked during a scheduled
promotion time, the promotion will fail. Do not mix on-demand locking with recurring schedules.
