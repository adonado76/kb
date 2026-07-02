---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How-To Guide: Use Common Script Patterns"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "Scripting"
source_path: "studio/new-uc/howtoguides/integrate-extend/htg-use-common-pattern.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How-To Guide: Use Common Script Patterns

**Objective:** Learn proven ApptioScript patterns for common business scenarios.

**Time estimate:** 45 minutes to review all patterns

**Prerequisites:** Completed the first how-to guide or equivalent ApptioScript
knowledge

This guide presents eight common patterns you can adapt for your implementations. Each
pattern includes the business use case, complete code example, and implementation notes.

## Pattern 1: Lookup Values from Another Table

**Business Use Case**

You have a labor mapping table where users select an employee. You want to automatically
populate the employee's department from a master employee table, similar to Excel's VLOOKUP
function.

**The Script**

```
' Lookup department from employee master table
' When user selects Employee ID, fetch their department
 
row.Department = lookup(EmployeeID, Department, EmployeeID, EmployeeMaster)
```

**How It Works**

The lookup() function takes four parameters: the value to match (EmployeeID from current
row), the column to return (Department), the column to match against (EmployeeID in the
lookup table), and the lookup table name (EmployeeMaster).

**Alternative Using Table Reference
Syntax**

```
' Alternative lookup syntax using table reference
{row.Unit of Measure} = All Business Services:Unit of Measure[Service ID=Service
        ID]
```

Note: The lookup function only works with editable tables. For lookups to other table types,
use the table reference syntax shown above.

## Pattern 2: Conditional Logic (IF/THEN)

**Business Use Case**

When a user selects a state, you want to make the City field required for some states (like
California) but optional for others, and automatically convert city names to lowercase for
consistency.

**The Script**

```
' Make City required for California, optional for others
' Also standardize city name to lowercase
 
If State = "CA"
 row.City.isRequired = "true"
 ' Standardize to lowercase
 row.City = LOWER(City)
Else
 row.City.isRequired = "false"
End If
```

**Multi-Condition Example**

```
' Different validation based on expense type
If ExpenseType = "Capital"
    row.DepreciationPeriod.isRequired =
        "true"
    row.DepreciationPeriod.isEditable =
        "true"
ElseIf ExpenseType = "Operating"
    row.DepreciationPeriod.isRequired =
        "false"
    row.DepreciationPeriod.isEditable =
        "false"
 row.DepreciationPeriod = ""
End If
```

Tip: You can nest If statements inside other If statements for complex logic but
keep nesting shallow (2-3 levels maximum) for maintainability.

## Pattern 3: Role-Based Cell Access Control

**Business Use Case**

You want to allow only administrators to edit financial amounts, while regular users can
view but not modify them. This provides an additional layer of control beyond row-level
security.

**The Script**

```
' Only Apptio Admins can edit the Amount column
If "<%=$CurrentUser:Users.Role%>" = "Apptio Admin"
 row.Amount.isEditable = "true"
Else
    row.Amount.isEditable =
        "false"
End If
```

**Implementation Notes**

- This script runs on load, so the cell editability is set when the table displays
- The role check uses the exact role name as defined in TBM Studio administration
- Combine with row-level security (RLS) for comprehensive access control

## Pattern 4: Date Manipulation

**Business Use Case**

You need to work with dates in various formats for different purposes: recording timestamps
for audit trails, specifying fiscal periods for data operations, or calculating the start of
the fiscal year.

**Common Date Patterns**

```
' Capture current timestamp with custom format
row.Timestamp = "<%=DateFormat(NOW(),"MM-dd-yyyy hh:mm:ss a")%>"
 
' Get current fiscal period (for use in data operations)
' Returns format like "January:2025"
AddRow(CurrentDate("MMMM:yyyy"), MyTable, Name="NewRecord")
 
' Add row for start of fiscal year
AddRow("!START_OF_YEAR(February:2025)", BudgetTable, Category="Annual")
 
' Add row for most recently edited period
AddRow(".MostRecent", AdjustmentsTable, Type="Correction")
```

**Date Format Reference**

|  |  |  |
| --- | --- | --- |
| **Format String** | **Example Output** | **Use Case** |
| MM-dd-yyyy | 01-15-2025 | US date format |
| MMMM:yyyy | January:2025 | Fiscal period (required for data operations) |
| MMMM:FYyyyy | January:FY2025 | Fiscal year format |
| hh:mm a | 02:30 PM | Time with AM/PM |
| hh:mm:ss a | 02:30:45 PM | Time with seconds |

Warning: For data operations like AddRow() and EditRows(), dates must use the full
month name (January, not Jan) in the MMMM:yyyy format.

## Pattern 5: String Operations

**Business Use Case**

You need to standardize data entry, combine values for display, or build dynamic messages.
String functions help ensure data consistency and create informative user feedback.

**Common String Patterns**

```
' Standardize text to uppercase
row.VendorCode = UPPER(VendorCode)
 
' Standardize text to lowercase
row.Email = LOWER(Email)
 
' Concatenate values for a composite field
row.AcceptedBy = "Accepted by <%=$CurrentUser:Users.Full Name%> on
        <%=CurrentDate()%>"
 
' Build a detailed comment
row.Comment = "Approved: " & Description & " (" & Amount & ")"
```

**String Concatenation**

Use the & operator to join strings. You can combine literal text (in quotes), column
values, and dynamic text in a single expression.

## Pattern 6: Workflow Status Changes (Button Actions)

**Business Use Case**

You have a demand planning process where cost center managers submit plans, and finance
approves or rejects them. You need buttons that update the workflow status (e.g., "Submit",
"Approve", "Reject").

**Submit Button Script**

```
' Submit Plan - changes CSM Status to "Submitted"
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 CSM Status="Submitted")
```

**Approve Button Script**

```
' Approve Plan - Finance approves the submission
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 Finance Status="Approved")
```

**Reject Button Script**

```
' Reject Plan - Finance rejects the submission
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 Finance Status="Rejected")
```

**Reset All Button Script (Admin
Only)**

```
' Reset All - Returns all records to initial state
' Note: Empty filter [] applies to all rows
EditRows("Jun 2019", Demand Plan Status[], 
 CSM Status="Not Submitted", 
 Finance Status="Pending", 
 CopyTable="No")
```

**How to Attach Scripts to Buttons**

1. In Report Studio, switch to Edit Mode
2. Right-click the button and select **Properties**
3. Select the **Actions** tab
4. Enter your script in the **Server Action** field
5. Click **OK**

## Pattern 7: Email Notifications on Events

**Business Use Case**

When a cost center manager submits a demand plan, you want to automatically notify the
designated approver by email with details about the submission.

**The Script**

```
' Send notification when plan is submitted
If eventType = "cellEdit(Submission_Status)"
    If {row.Submission Status} =
        "Submitted"
        ' Send email to the designated
        approver
 SendEmail(row.Approver, 
            "Demand Plan submitted for
        review and approval", 
            "Demand Plan submitted by
        " & row.Submitter & 
            " for the " &
        row.Organization Name & " department. " &
            "Special comment from
        submitter: " & row.Submission Comment)
 End If
End If
```

**SendEmail Syntax**

`SendEmail("recipient@company.com", "Subject Line", "Email Body
Content")`

**Implementation Notes**

- Using cellEdit(ColumnName) prevents the email from being re-sent when other columns are
  edited
- The recipient can be a cell value (like row.Approver) or a hardcoded email address
- Use & to concatenate strings for dynamic email content

Warning: Test email scripts thoroughly in a development environment. Incorrect
scripts can send unintended emails to real recipients.

## Pattern 8: Copy Data Between Tables

**Business Use Case**

After finance approves a demand plan, you want to copy the forecasted volumes to an
"approved" table that feeds downstream reporting. This creates a snapshot of the approved
state.

**CopyTable Example**

```
' Copy approved forecast to snapshot table
CopyTable(
   
        "reference.apptio.com:<%=ProjectName()%>/Reports/<%=CurrentDate("MMMM:yyyy")%>/CostModels/Default/.TableTransform:Volume
        Forecasts Transform/.Summary/",
   
        "reference.apptio.com:<%=ProjectName()%>",
 "Volume Forecasts Approved",
   
        "<%=CurrentDate("MMMM:yyyy")%>"
)
```

**CopyEditableTable Example**

```
' Copy editable table with auto check-in
CopyEditableTable(
   
        "tests.apptio.net:MyProject/Data/January:FY2015/Source Data",
 "tests.apptio.net:MyProject",
 "Archived Data",
 "overwrite",
 autocheckin="true"
)
```

## Key Differences

|  |  |  |
| --- | --- | --- |
| **Function** | **Use For** | **Auto Check-in** |
| CopyTable() | Report tables, raw data sets | No (places in dev workspace) |
| CopyEditableTable() | Editable tables with mode control | Optional (autocheckin parameter) |

Note: CopyTable places data in the current user's dev workspace and does NOT check in changes
automatically. Consider restricting this functionality to administrators.

## Additional Patterns

## Looping Through Data

Use the Loop function to iterate through rows in a data set and perform operations on each
row.

```
' Process each row in a data set
Loop mydatasetname
 Debug("Cost=" & Cost)
 ' Add additional operations here
End Loop
```

## Deleting Rows Conditionally

Use DeleteRows() to remove rows matching specific criteria from an editable
table.

```
' Delete all rows where BU is "Sales" OR Other is "Foo"
DeleteRows(CurrentDate(), BuList[BU="Sales" OR Other="Foo"])
 
' Delete rows matching multiple conditions (AND)
DeleteRows("January 2010", BuList[BU="Sales" AND Date="Jan 2010"])
```

## Adding Rows Programmatically

Use AddRow() to create new records in editable tables with initial
values.

```
' Add a new project record for the current period
AddRow(CurrentDate("MMMM:yyyy"), All Projects, 
 Project Name="unnamed", 
 Status="Pending")
 
' Add a server record for a specific period
AddRow("February:2008", MyServers, 
 servername="server001", 
 ram="128", 
 os=UPPER("windows"))
```

## What's Next

- Section 5.6: ApptioScript Reference — Complete function documentation with all parameters
  and options
- [Configure Data Security](../work-with-data/data-security.html) — Learn
  about row-level security that complements script-based access control
- [Connect via APIs](api-integration.html) — For advanced integrations beyond
  ApptioScript

**Parent topic:** [Scripting](../../../../studio/new-uc/howtoguides/integrate-extend/scripting.html)
