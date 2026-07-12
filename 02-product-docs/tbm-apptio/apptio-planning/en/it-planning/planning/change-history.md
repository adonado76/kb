---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Change History"
breadcrumb:
  - "Planning"
  - "Workflows and Collaboration"
source_path: "it-planning/planning/change-history.html"
images:
  - "resources/images/it_planning_images/chnghist.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Change History

Change History provides an audit trail of key actions performed within your planning
environment. It allows organizations to maintain transparency, support compliance requirements,
and troubleshoot planning issues by tracking who changed what, when, and how.

Note: Admin or Budget Process Owner roles are required to access Change History.

## Where to Access Change History

Go to **Change History → Event Log** using the left navigation.

- Use filters to drill into the types of events, date ranges, users, or scopes (plans,
  departments, accounts).
- Use the **Export** function to download a CSV of the audit log for external
  analysis or archiving.

## Event Types

Change History captures a variety of event types. Common categories include:

- **Plan Events**: Plan creation, state changes (New → Final), archiving, versioning.
- **Data Entry Events**: Line-item edits, record insert/delete, import operations.
- **Approval Events**: Submission, approval, return, comment.
- **Reference Data Events**: Dimension changes (e.g., accounts, departments),
  configuration updates.
- **Role and Permission Events**: User role assignment, access changes.

Refer to the full [Event Types](event-types.html "Change History captures a wide range of system events within Apptio Planning, allowing you to review who did what, when, and how. Each event is categorized by type, area, container, item type, and attribute changes.") list for complete
details and descriptions.

## Exporting Change History

- On the Change History page, click the **Ellipses menu →****Export to CSV.**
- The file includes all selected filters and the event data: timestamp, user, plan,
  department, event type, description, and before/after values when available.
- Use the export for compliance audits, process reviews, or integration with BI/reporting
  systems.

## View Event Details

You can view additional information about any event in the Change History by opening the
**Properties** pane.

**To open an event’s properties:**

- Click the **Properties icon** next to the event in the Event Log.

The Properties pane includes two tabs:

- **Info** — Shows general information about the event (such as event type, user, and
  timestamp).
- **Details** — Displays specific changes, including before and after values for all
  affected attributes.

![image of event log](../../../../../03-media/apptio-planning/resources/images/it_planning_images/chnghist.png)

- **[Event Types](../../it-planning/planning/event-types.html)**  
  Change History captures a wide range of system events within Apptio Planning, allowing you to review who did what, when, and how. Each event is categorized by type, area, container, item type, and attribute changes.
