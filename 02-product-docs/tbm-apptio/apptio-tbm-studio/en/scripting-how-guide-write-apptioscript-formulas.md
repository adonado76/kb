---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "How-To Guide: Write ApptioScript Formulas"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "Scripting"
  - "How-To Guide: Write ApptioScript Formulas"
source_path: "SSWRJM/studio/new-uc/howtoguides/integrate-extend/htg-write-as.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# How-To Guide: Write ApptioScript Formulas

Objective: Learn the fundamentals of ApptioScript and write your first working script.

Time estimate: 30 minutes

Prerequisites: Access to TBM Studio with at least one editable table

## Understanding ApptioScript Basics

ApptioScript runs in two primary contexts: attached to editable tables (responding to cell changes, row additions, or data loading) and attached to buttons (executing on user click). Understanding these contexts is essential before writing any script.

It is recommended that some form of text editor is used for ease of writing longer scripts. The text can be copy/pasted into the editor.

Where Scripts Run

| Location | When It Executes | Common Uses |
| --- | --- | --- |
| Location | When It Executes | Common Uses |
| Editable Table Script | On cell edit, row add, or table load/refresh | Validation, cell formatting, audit trails, lookups |
| Button Server Action | When user clicks the button | Workflow transitions, data operations, copy operations |

## Script Structure

Every ApptioScript consists of statements that execute sequentially. The basic building blocks are:

- Statements — Function calls that perform actions (e.g., EditRows(), AddRow())
- Conditional logic — If/ElseIf/End If blocks for branching
- Variables — row and eventType are available in editable table scripts
- Subprocedures — Reusable blocks of code defined with Sub/End Sub
- Comments — Lines starting with ' (apostrophe) are ignored
- Dynamic text — <%=%> syntax for inserting runtime values

## Key Variables in Editable Table Scripts

The row Variable

```
' Read a cell value
If row.Status = "Complete"
 
' Set a cell value
row.LastUpdated = "<%=CurrentDate()%>"
 
' Make a cell required
row.ApproverName.isRequired = "true"
 
' Make a cell read-only
row.SystemID.isEditable = "false"
 
End If
```

The eventType Variable

The eventType variable tells you what triggered the script. This is essential for scripts that should behave differently based on context:

| eventType Value | When It Occurs |
| --- | --- |
| eventType Value | When It Occurs |
| "onload" | Table initially loads or refreshes |
| "cellEdit" | User edits any cell in the row |
| "cellEdit(ColumnName)" | User edits a specific column (e.g., cellEdit(Status)) |
| "addRow" | User adds a new row |
| "duplicateRow" | User duplicates an existing row |

## Step-by-Step: Create Your First Script

This walkthrough creates a simple audit trail script that records who edited a row and when.

## Step 1: Prepare Your Editable Table

Before adding a script, ensure your editable table has columns to store the audit information. For this example, add two columns:

1. Edited By — Label type, to store the user ID
1. Edit Date — Label type, to store the timestamp

## Step 2: Access the Script Editor

1. Check out the editable table
1. Navigate to the editable table in the Project Explorer
1. Go to Steps > Script
1. The script editor opens, showing any existing script or an empty area for new scripts

## Step 3: Write the Audit Trail Script

```
' Audit trail: capture who edited and when
' This script runs on every cell edit or new row
 
If eventType = "cellEdit" OR eventType = "addRow"
 ' Store the current user's ID
    {row.Edited By} =
        "<%=$CurrentUser:Users.Id%>"
 
    ' Store the current date and
        time
    {row.Edit Date} =
        "<%=DateFormat(NOW(),"MM-dd-yyyy hh:mm a")%>"
End If
```

## Step 4: Save and Test

1. Click Save to save the script
1. Check in the editable table
1. Open a report containing this editable table
1. Edit any cell in the table
1. Verify that the Edited By and Edit Date columns populate automatically

Expected result: When you edit any cell, the Edited By column shows your user ID (e.g., "jsmith") and Edit Date shows the timestamp (e.g., "01-15-2025 02:30 PM").

## Using Dynamic Text

Dynamic text (<%=%>) lets you insert values that are evaluated at runtime. All dynamic text is evaluated and replaced before any line of ApptioScript executes.

Common dynamic text patterns:

| Expression | Returns |
| --- | --- |
| Expression | Returns |
| <%=$CurrentUser:Users.Id%> | Current user's ID |
| <%=$CurrentUser:Users.Full Name%> | Current user's full name |
| <%=$CurrentUser:Users.Role%> | Current user's role |
| <%=CurrentDate()%> | Current date (default format) |
| <%=CurrentDate("MMMM:yyyy")%> | Current period in Month:Year format |
| <%=DateFormat(NOW(),"MM-dd-yyyy")%> | Today's date formatted |
| <%=ProjectName()%> | Current project name |

## Common Pitfalls

- Forgetting curly braces for columns with spaces: Use {row.Vendor Name} not row.Vendor Name
- Incorrect string comparisons: Values are case-sensitive. "Active" ≠ "active"
- Missing End If: Every If statement requires a matching End If
- Comments on code lines: Comments must be on their own line. The ' character cannot appear at the end of a code line
- Boolean values as strings: isRequired and isEditable use string values "true" or "false", not Boolean true/false
