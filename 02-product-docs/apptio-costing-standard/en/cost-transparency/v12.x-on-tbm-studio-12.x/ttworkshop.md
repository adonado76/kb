---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Time Tracking Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/ttworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Time Tracking Workshop

## Preparing your Time Tracking data

1. If you haven’t already done so, load your Time Tracking data including:
   - List of Tasks
   - Hours worked by Employee
2. Following Apptio standard
   practices, categorize each raw data set into the category of Time Tracking:
3. If appropriate, apply a date filter to your time tracking data:

## About the Time Tracking Identifier

The Identifier for the Time Tracking object is pre-defined and should not be altered. It
includes:

- Labor ID
- Task ID
- Project ID

## About the Time Tracking Keys

The keys for the Time Tracking Master Data set are all system generated and should not be
altered.

| Key | Field key is based on | Logic |
| --- | --- | --- |
| **Labor\_Time Tracking Key** | Labor ID | Append the text Labor\_Time Tracking with Labor ID |
| **Time Tracking\_Project Key** | Project ID | Append the text Time Tracking\_Project with Project ID |
| **Time Tracking\_IT Tower Key** | IT Resource Tower  IT Resource Sub Tower | Append the text Time Tracking\_IT Tower Key with IT Resource Tower and IT Resource Sub Tower |

When mapping in the Employee ID to the Labor ID the system will automatically make a connection
between the Labor and Time Tracking objects. When this connection is established the cost for that
employee will flow to the Time Tracking object but will be more granular because they employee will
now be split out based on the activities the employee is tracking hours against.

## Common Computed Columns Needed for Time Tracking

Often there is no single list of tasks and all the metadata about those tasks. You may need to
pull data from one or more systems. As long as the task ID is the same among the various systems,
you can use the LOOKUP function to translate task related information such as actual hours or
planned hours back to a single data set (such as the original list of tasks for a project).

## Map data to Time Tracking Master Data

Map your time tracking data to the Time Tracking Master Data set. Most of the mapping should be
self-explanatory at this point. There are no unusual mapping requirements. In 12.7 you can now
leverage the Column Map function in your raw dataset to map to the Time Tracking Master Data ([Map
Columns](https://community.apptio.com/docs/DOC-10561 "(Opens in a new tab or window)"))

## Review the Time Tracking object on the models

| Model | Actions |
| --- | --- |
| Cost | Ensure values are flowing into the Time Tracking object.  From Labor to Time Tracking, allocate using the Data-based Reference. You can also allocate from Time Tracking to IT Towers as needed.  From Time Tracking, you can allocate to Projects based on the project ID. Ideally, allocate using the Data-based Reference. If you cannot use a Data-based Reference, discuss your options with your consultant. |
| Budget | Ensure values are flowing into the Time Tracking object.  From Labor to Time Tracking, allocate using the Data-based Reference. You can also allocate from Time Tracking to IT Towers as needed[VM1] .  From Time Tracking, you can allocate to Projects based on the project ID. Ideally, allocate using the Data-based Reference. If you cannot use a Data-based Reference, discuss your options with your consultant. |
| CapEx | Ensure values are flowing into the Time Tracking object.  From the Labor object to Time Tracking object, allocate using the Data-based Reference. From Time Tracking to Projects, allocate using the Data-based Reference.  If you cannot use a Data-based Reference, discuss your options with your consultant. |
| CapEx Budget | Ensure values are flowing into the Time Tracking object[VM2] .  From the Labor object to Time Tracking object, allocate using the Data-based Reference. From Time Tracking to Projects, allocate using the Data-based Reference.  If you cannot use a Data-based Reference, discuss your options with your consultant |

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
