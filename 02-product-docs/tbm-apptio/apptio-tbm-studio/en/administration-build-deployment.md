---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Build & Deployment"
breadcrumb:
  - "Administration"
  - "Build & Deployment"
source_path: "SSWRJM/studio/new-uc/admin/build-deploy.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Build & Deployment

Content Type: Conceptual / How-To

Target Audience: Administrators, Power Users

Prerequisites: Understanding of Development, Staging, Production environments

The build and deployment lifecycle in TBM Studio manages how changes flow from development through staging to production. Understanding this lifecycle is essential for maintaining a stable production environment while enabling iterative development.

## Understanding Environments

TBM Studio uses three environments to manage the progression of changes from development to end users.

| Environment | Description |
| --- | --- |
| Environment | Description |
| Development | Where configuration changes are made. Check-ins trigger development calculations that process transforms and metrics. Changes are validated here before moving to staging. |
| Staging | Pre-production validation environment. Calculates drills and reports after development calculation completes. Used to verify changes before promoting to production. |
| Production | Live environment that business users access. Changes reach production only through an explicit promotion from staging. Promotion is nearly instantaneous. |

## Check-Out and Check-In Workflow

In TBM Studio, all elements (tables, metrics, perspectives, models) are documents that must be checked out for editing. When you check out a document, it is locked so others cannot edit it simultaneously.

To check out a document:

- Select the document in Project Explorer
- On the Home tab, in the Document group, click Check Out
- A check-out icon appears next to the document name, and the name displays in orange

## Check-in best practices:

- Review data before uploading to verify content and formatting
- Click Save after modifying any document
- Resolve all errors before checking in
- Validate reports that use the modified data
- Coordinate check-ins with team members to avoid queued calculations

Tip: Establish a team check-in policy to coordinate check-ins once or twice per day (e.g., at lunch and end of day). This reduces calculation queue conflicts and ensures everyone sees the same data.

## Monitoring the Calculation Queue

The Calculation Queue shows the status of builds across all environments. Use it to monitor calculation progress, identify queued builds, and view calculation history.

To access the Calculation Queue:

- Navigate to Build > Calculation Queue

Build status indicators:

- Pending - Build is queued and waiting to be processed
- Calculating - Build is in progress (shows completed vs total calculations)
- Finished - Build is complete (shows time since completion and duration)

## Lock and Promote to Production

To deploy changes to production, you must first lock staging to prevent further changes, then promote the staging build to production.

To promote to production:

- Ensure all pending staging calculations are complete
- Navigate to Build > Lock to lock the staging environment
- Click Promote Now to deploy to production
- Verify reports in production after promotion

Note: Promotion to production in TBM Studio R12 is nearly instantaneous. Users will see updated data immediately after promotion completesis complete.

## Working with Branches

Branching creates a complete copy of your project, allowing parallel development without affecting the main project (trunk). Branches are useful for long-running configuration changes, hotfixes, and archiving past states.

When to use branches:

- Long-running configuration - Major changes that take weeks to complete while operational data loads continue on trunk
- Hotfix production - Fix production issues without promoting in-progress development work
- Archive prior states - Preserve and access historical project states (e.g., prior fiscal years)

Branch limitations:

- Maximum of 5 branches per environment
- Each branch uses the same resources as the main project
- Branch calculations are queued with trunk calculations (except hotfix branches)
- A branch cannot be closed if its build is used in production

Tip: To improve branch performance, right-size the time period by adjusting the Project Start and End dates to only include necessary periods. This reduces calculation time significantly.

## Rolling Back Changes

The rollback feature allows you to restore a project to an earlier configuration state. Use the rollback feature when a checked-in change causes problems that need to be quickly reversed.

Warning: Rollback is a significant operation. All check-ins after the selected point will be discarded. Ensure you understand the impact before proceeding, andproceeding and consider using a branch to preserve work if needed.

To rollback a configuration:

- Navigate to Build > Check In History
- Right-click the check-in you want to restore and select Rollback To
- Enter a descriptive reason for the rollback
- Click Rollback Check In
- After rollback completes, refresh workspaces by clicking Home > Update Workspace

## Scheduled and Recurring Promotions

TBM Studio supports scheduled promotions for automated deployment workflows. You can configure recurring updates and promotions to automate the deployment of editable table data and other changes.

To configure scheduled promotions:

- Navigate to Build > Promotion Options
- Configure Recurring Updates to set the schedule for staging builds
- Configure Recurring Promotions to automate deployment to production
