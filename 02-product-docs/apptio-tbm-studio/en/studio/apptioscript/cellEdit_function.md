---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Send Mail and Cell Edit functions"
breadcrumb: []
source_path: "studio/apptioscript/cellEdit_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Send Mail and Cell Edit functions

Two features have been released to support the ability to trigger an email based on an event
change in an editable table.

- **SendMail()** function
  - General syntax: `SendEmail("email address","Subject","Content")`
- **cellEdit()** - feature enhancement
  - General syntax: `cellEdit("column_name")` where column name is
    optional. If a column name is included, the event will trigger only if a cell change is
    made in that column. For the SendMail function, this eliminates the "resending" of an
    email if other columns are changed.

**Example code for a Demand Planning use
case**

```
if eventType = "cellEdit(Submission_Status)"
'
if {row.Submission Status} = "Submitted"
' Send email to designated Approver
SendEmail(row.Approver,"Demand Plan submitted for review and approval","Demand Plan submitted by " & row.Submitter & " for the " & row.Organization Name & " department. Here is any special comment from the submitter: " & row.Submission Comment)
end if
'
end if
```

In a similar manner, a script could be configured to send an email to the submitter if the
approver "rejects" the submitted plan.
