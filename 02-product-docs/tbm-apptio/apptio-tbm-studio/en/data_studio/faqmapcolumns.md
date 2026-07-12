---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Frequently asked questions about Map Columns"
breadcrumb: []
source_path: "data_studio/faqmapcolumns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Frequently asked questions about Map Columns

Applies to: TBM Studio 12.7 and later

Tip: If you don't find what you are looking for here, review posts in the [TBM Studio 12 Q&A Forum](https://community.apptio.com/community/apptio/product-central/apptio-qa-forum "(Opens in a new tab or window)"), or [post a question to the Forum](https://community.apptio.com/community/apptio/product-central/apptio-qa-forum "(Opens in a new tab or window)") .

## Transform pipeline and Map Columns

Why don't I see all my columns when mapping?

Only columns with the same type can be mapped. Therefore, when you select a column for a
destination column with a type of label, only your columns with a type of label will appear. If your
initial upload contained no data (headers only), then no type is selected by default. Codes often
import as numeric. In both cases, go to the Import step to override the default column
type.

When you select the type Date in Import, fill in the format of the date to the right of type
selectors.

Example: Date format

```
yyyy-mm-dd:
      2018-09-26
```

.

I want to join another table to this, but I need to do some logic on the results. What
should I do?

Use the pipeline step Join just prior to Map Columns to return columns linked to the primary
table by a column of matching information. When possible, complete any logic on the other table. You
can select "Add Custom Column" to add the column to the output, or map to an available existing
destination column.

For "Is Labor" and "Is Depr": The Chart of Accounts Master Data will calculate these fields in
v107. Alternatively, leave the columns blank and change the allocation to use the cost pool or sub
pool to filter the allocations' source instead.

However, if you need to complete logic based on columns in both the primary and the joined table,
use a Lookup() formula in the pipeline step Formulas. You can still use the Join step to return the
rest of the columns, if needed.

Can I move the order of the Join and Map Columns step?

At this time, the Join step will either appear next to the Model step or the Map Columns step
(select one or the other).

Map Columns will always be the step before Table, unless there is an Assign Cost Pools step.
Essentially, everything after Map Columns is a part of the content offering. However, you can have
as many steps or transforms prior to the Map Columns step.

## Mapped Tables and the master data set

**I see a Source Table column on the master data set but I didn't map anything to it. Where did
it come from?**

Apptio automatically adds a column with the name of the table that sent data to a master data set
through Map Columns. This allows you to trace your data from the model to the source data faster.
Only data added via Map Columns has this information. You must manually add any appended data to the
information or it will be blank.

SEE ALSO:

- [Map Columns](mapcolumns.htm "(Opens in a new tab or window)")
- [Assign cost pools with machine
  learning](assigncostpools.htm "(Opens in a new tab or window)")
- [Configure machine
  learning for cost pools](configuremachinelearning.htm "(Opens in a new tab or window)")
