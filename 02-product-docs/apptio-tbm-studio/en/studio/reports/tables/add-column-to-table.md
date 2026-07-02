---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Add columns to a table"
breadcrumb: []
source_path: "studio/reports/tables/add-column-to-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add columns to a table

**Applies to**: TBM Studio 12.0 and later

Watch this demo video from Apptio Education Services: [Add a Rate
Column](https://community.apptio.com/videos/1893 "(Opens in a new tab or window)"). Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

After adding a table to a report, you can add columns to the table. The main types of columns are
described below:

- **Total** - Displays the totals for each row in a table ([How?](add-total-column.htm "(Opens in a new tab or window)")).
- **Formula** - The column can be based on a custom formula, the columns in the data set
  backing the table, or a modeled value ([How?)](add-formula-column-to-table.htm "(Opens in a new tab or window)").
- **Calculated** - The column can display values for a single column such as count, percent,
  and sum. It can also compare two columns in the table or compares values between projects ([How?](add-calculated-column.htm "(Opens in a new tab or window)")).
- **Calendar** - Displays values for the data based on a span of time greater than a month or
  period ([How?](add-calendar-based-column.htm "(Opens in a new tab or window)")).
- **Sparkline** - Displays a small trend line ([How?](add-sparkline-column-to-tables.htm "(Opens in a new tab or window)")).
- **Editable** - A blank column added to an editable table where users can enter data.

The table below shows where the types of columns can be used.

| **Column type** | **Object-based tables** | **Transform tables** | **Editable tables** |
| --- | --- | --- | --- |
| Formula | X | X | X |
| Calculated | X | X |  |
| Calendar | X | X |  |
| Sparkline | X | X |  |
| Total | X | X | X |
| Editable |  |  | X |

Word wrap is not applicable for primary source column for an Enriched Editable Table.
