---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Line Item Codes &amp; Prefixes"
breadcrumb: []
source_path: "planning/line-item-codes.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Line Item Codes &amp; Prefixes

## About Line Item Codes

Line items across the following tables have assigned unique Line Item Codes:

- Allocation
- Asset
- Contract
- Demand
- Financial
- Labor

A Line Item Code contains two parts:

- a prefix
- a numeric code

Planning generates the numeric code automatically for each line item. These numbers are unique
within a plan.

If you create a new plan using an existing plan as a baseline reference, you can choose to copy
over the Line Item Codes. If you choose not to, Planning generates new Line Item Codes. For more
information, see [Learn more about
creating plans](create-budget-plan.htm "(Opens in a new tab or window)").

## Line Item Code prefixes

In addition to a numeric portion to the code, each Line Item type will have a unique prefix. The
default prefixes are as follows:

| Line Item type | Default prefix |
| --- | --- |
| Allocation | LA- |
| Asset | A- |
| Contract | C- |
| Demand | LA- |
| Financial | F- |
| Labor | L- |

## Change a Line Item Code prefix

It is strongly recommended to keep the default prefixes, or change them only if it is absolutely
necessary.

1. In the left-hand navigation pane, select Configuration > Line Item Code Prefix.
2. Select the Line Item type you want to change.

   The Edit Prefix dialog is
   displayed.

   ![](../../resources/images/it%20planning_images/edit_prefix.png)
3. Enter the new prefix.

   Prefixes cannot be longer than 10 characters, cannot be empty, and
   cannot contain digits.
4. Select Save.

Changes to Line Item Code prefixes are applied immediately across all plans in the tenant.

## Line Item Codes in the Event Log

Line Item Codes can be tracked in the Change history in the Event Log. If a line item has a Line
Item Code, it is displayed in the Item column.

The Event Log displays the Line Item Code as it was at the time the event occurred. If a Line
Item Code prefix is changed, then:

- For any events which occurred before the change, the Event Log displays the previous Line Item
  Code prefix.
- For any events which occurred after the change, the Event Log displays the new Line Item Code
  prefix.

This means that two events which have the same Line Item type may use different prefixes,
depending on when they occurred. For more information on Change history and viewing the Event Log,
see [Learn more about Change
history](change-history.htm "(Opens in a new tab or window)").

## Source Line Item Codes

The Source Line Item Code is a code that points to where the line item came from. Planning only
assigns a Source Line Item Code if a line item has been created from another source. For example,
Delegations created from line items do not have a Line Item Code; instead, they have a Source Line
Item Code which is the Line Item Code of the item that caused their creation.

If you have enabled [Labor Summarization](https://help.apptio.com/en-us/it-planning/planning/edit-company-profile.htm#EnableCapabilities "(Opens in a new tab or window)"), then the Source Line Item Code may
display "varies" for line items originating from the Labor tab.

For more information on labor summarization, see [Labor Summarization](https://help.apptio.com/en-us/it-planning/planning/labor-summarization.htm "(Opens in a new tab or window)").

## Source Plan

The Source Plan is the plan from which a line item was copied. For example, if a plan is created
using an existing plan as a baseline, the Source Plan column displays the name of the plan from
which the line item originated.

Source Plan perpetuates across multiple copies. For example, if you create plan B using plan A as
a baseline, then create plan C using plan B as a baseline, in plan C the Source Plan will be plan A
for any line items that originated in plan A.

For more information on creating plans, see [Learn more about creating plans](create-budget-plan.htm "(Opens in a new tab or window)").
