---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "ApptioScript examples"
breadcrumb: []
source_path: "studio/apptioscript/apptioscript_examples.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioScript examples

Use the following examples to review uses of ApptioScript.

## Example 1

```
' An example script used in OnCellValueChanged
If State = "CA"
row.City.isRequired = "true"
' Any function can be called here
' example: lower case the city cell
row.City = LOWER(City)
' a better way of doing lookup instead of using dynamic text
row.Japanese = lookup(Number,Japanese,Number,Japan)
Else
row.City.isRequired = "false"
End If
```

## Example 2

```
If State = "WA"
row.City.isEditable = "false"
Else
row.City.isEditable = "true"
End If
```

## Example 3

```
An example of calling a procedure:
Sub Test()
Test2()
End Sub
Sub Test2()
Return("Foo")
End Sub
```

## Example 4

```
Test() 'this calls Test() subprocedure defined in Example 3
```

## Example 5 Editable Tables

Enter code in TBM Studio: **Editable Table > Script**.

## Audit trail

Edit cell - example 1

```
If eventType = "cellEdit(Name)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
```

Edit cell - example 2

```
If eventType = "cellEdit(Name)" OR eventType = "cellEdit(ID)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
```

Edit cell - error example

```
If eventType = "cellEdit(wrong column name)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
could not evaluate [wrong column name] in cellEdit command
```

Row level - capture Edited By and Edited Date (date format = MM-dd-yyyy hh:mm
a)

```
if eventType = "cellEdit" OR eventType = "addRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm a")%>"
end if
```

Row level - capture Edited By and Edited Date (date format = MM-dd-yyyy hh:mm
a)

```
if eventType = "cellEdit" OR eventType = "duplicateRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm a")%>"
end if
```

## Control editability of a column

```
row.FIELDNAME.isEditable = "false"
```

## Role-based Editable Cells

```
If "<%=$CurrentUser:Users.Role%>" = "Apptio Admin"
row.Amount.isEditable="false"
Else
row.Amount.isEditable="true"
End If
```

## Populate value in a cell from another lookup

```
{row.Unit of Measure}=All Business Services:Unit of Measure[Service ID=Service ID]
```

## Example 6 Button to Support Process Flow

Enter code in Button Properties: **Actions tab > Server Actions**.

## Submit Plan (Consumer status change)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status="Submitted")
```

## Unsubmit Plan (Consumer status change)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status="Not Submitted")
```

## Reject Plan (Finance status change)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], Finance Status="Rejected")
```

## Unsubmit Plan (Finance status change)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], Finance Status="Approved")
```

## Reset (Finance status change)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status = "Not Submitted", Finance Status = "Pending", CopyTable="No")
```

## Reset All (Process owner status change)

```
EditRows("Jun 2019", Demand Plan Status[], CSM Status = "Not Submitted", Finance Status = "Pending", CopyTable="No")
```

## CopyTable

```
copytable("reference.apptio.com:<%=ProjectName()%>/Reports/<%=CurrentDate("MMMM:yyyy")%>/CostModels/Default/.TableTransform:Volume Forecasts Transform/.Summary/","reference.apptio.com:<%=ProjectName()%>","Volume Forecasts Approved","<%=CurrentDate("MMMM:yyyy")%>")
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CopyTable="Copied")
```

Note: CopyTable will place the table in the current users dev workspace and DOES NOT check-in the
changes. For this reason, you may want this functionality controlled by an Admin rather than a
user.

## Example 7 ApptioScript from ApptioOne Demand

Volume Plan entry editable table

```
row.Service ID.isEditable = "false"
row.Service Offering.isEditable = "false"
row.Application Name.isEditable = "false"
row.Unit of Measure.isEditable = "false"
row.Rate.isEditable = "false"
row.Baseline Volume.isEditable = "false"
if eventType = "cellEdit" OR eventType = "addRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm:ss a")%>"
end if
```
