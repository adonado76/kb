---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "apptioscript"
title: "Loop function"
breadcrumb: []
source_path: "apptioscript/loop_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Loop function

Use the Loop function to loop over a raw data set and execute statements for each row in
the data set.

## Syntax

```
Loop data set
statements
End Loop
```

## data set

The data set.

## statements

The statements you want to execute for each row in the data set.

## Example

The following example prints Cost = and the Cost value for each row in the data set named
mydatasetname.

```
Loop mydatasetname
Debug("Cost=" Cost)
End Loop
```
