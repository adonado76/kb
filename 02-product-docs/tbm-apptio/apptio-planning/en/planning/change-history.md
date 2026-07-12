---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "View and export the change history"
breadcrumb: []
source_path: "planning/change-history.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# View and export the change history

You can use the change history Event Log to view changes in your system over a specific time
period and export the results as a CSV file.

## About the Event Log

- To open the Event Log, open the left-hand navigation and select Change History > Event
  Log.

  ![](../../resources/images/it%20planning_images/event-log2.png)

## What the Event Log displays

Note: One action may consist of multiple events. For example, a user can submit a list of cost
objects in a single action, but the Event Log shows an event for each cost object included in the
action.

[Learn more about Event
types](event-types.htm "(Opens in a new tab or window)")

## Fields

The Event Log records the following information about each event:

| Field | Description |
| --- | --- |
| Event ID | Unique event identifier (randomly generated 32 character string) |
| Timestamp | Date and time, in the following format:  5/24/21, 11:32 AM  In the CSV file, the format is: 2021-05-24T18:32:07.842027Z |
| Event type | [Learn more about Event types](event-types.htm "(Opens in a new tab or window)") |
| Container ID | Unique container ID (randomly generated 32 character string) |
| Area | The highest level of the data's hierarchy that the element is linked to  For most events, this is either Plan or Configuration |
| Container | The second level of the data's hierarchy (name of the plan or a table in the configuration) |
| Item ID | Unique item identifier (randomly generated 32 character string)  May be blank for some events |
| Item type | Type of item that was changed. For example, if an expense line item was changed, this value refers to the line item table that was changed. May be blank for some events. |
| Item | Together with Item Type and Attribute, this value puts into context what specifically was changed as a result of the event (for example CC-200, Role, Employee Name). This value varies widely across events and may be blank for some events. |
| User ID | Unique user identifer (randomly generated 32 character string) |
| User | User name of the user initiating the event |
| Attribute | Found in the Properties pane under the Details tab. Can vary across event types. When a period's metric value changes, the attribute will be the period name, for instance. May be blank for some events.  [Learn more about viewing event properties](#Viewandexportthechangehistory__Viewthepropertiesofanevent). |
| Before | Found in the Properties pane under the Details tab. The value before the event. May be blank for some events. |
| After | Found in the Properties pane under the Details tab. The value as a result of the event. May be blank for some events. |
| Context ID | Unique context identifier (randomly generated 32-characters string). |
| Context Type | Type of context (Department, Project, or Service). |
| Context | Cost Object Code for the logged event. |

## Show or hide columns

Add or remove columns using the Show/Hide Columns pane.

![](../../resources/images/it%20planning_images/event-log.png)

To open the pane, select ![](../../resources/images/it%20planning_images/options1_23x20.png) > Open Show/Hide Columns.

If you can only see an option to Close Show/Hide Columns, the Show/Hide Columns pane is already
open and collapsed at the right side of the Event Log. Select Show/Hide Columns to display the
pane.

## Rearrange columns

To move a column in the Event Log, click and drag the column to where you want to display it.

## Filter events

You can filter the events displayed in the Event Log to only include events with certain values
in a column. You can apply more than one filter at the same time.

You cannot filter events by columns with unique values per event (Event ID and Timestamp).

1. Hover over the column header and select ![](../../resources/images/it%20planning_images/burger-button_13x9.png) > ![](../../resources/images/icons/icon-filteron_18x20.png).
2. Use the check boxes to select the values you want to include. You can use the search field to
   find the values you want to select.

   ![](../../resources/planning_images/col_filter.png)
3. Select Apply.

   Columns with filters applied display a filter icon (![](../../resources/images/icons/icon-filteron_18x20.png)) in the header, as shown
   below:

   ![](../../resources/planning_images/filter_applied.png)

## Clear filters

To clear filters, select ![](../../resources/images/it%20planning_images/clear-filters_20x20.png) above the Event Log.

## Sort events by column

To sort events by a column, hover over the column header and select ![](../../resources/images/it%20planning_images/itfmf-ct_images/sort-icon_21x20.png).

You can sort by any of the these columns:

- Timestamp
- Event Type
- Area
- Item Type

Currently, you cannot sort by these columns:

- Container
- Item
- User
- any of the ID columns, for example Event ID

## Export your change history

Select ![](../../resources/images/it%20planning_images/options1_23x20.png) > Export to
CSV.

Planning downloads your CSV file to your device.

## View the properties of an event

To get more information about any event in the change history, you can view the Properties
pane.

- To open an event in the Properties pane, select the Properties icon (![](../../resources/images/it%20planning_images/view-properties.png)) in the Event Log row.

  The
  Properties pane displays the following tabs:

  dd
- In Info you can view basic information about the event.
- In Details you can view specific information with before and after values. The Details tab
  displays all the attributes affected by the event.

  ![](../../resources/images/it%20planning_images/properties-pane.png)
