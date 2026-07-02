---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Create a dynamic title for a monthly Forecast report"
breadcrumb: []
source_path: "cost-transparency/reports-v103/createdynamictitlemonthlyforecast.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Create a dynamic title for a monthly Forecast report

**Problem**

You create a monthly re-forecast report. You want the title to
include the forecast month, displayed as 1+11, 2+10, 3+9, etc. The title should read e.g.
"1+11 Forecast as of Jan 2015".

**Solution**

Use Dynamic Text in the HTML
object to evaluate the date selected in the date picker and translate to X+(12-X)
notation.

`<%=EVAL(CurrentDate("MM")-1)&"+"&EVAL(13-CurrentDate("MM"))&"
Forecast as of "&CurrentDate("MMM ffff")%>`
