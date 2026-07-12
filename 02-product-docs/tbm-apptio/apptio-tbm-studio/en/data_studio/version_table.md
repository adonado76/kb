---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Version a table"
breadcrumb: []
source_path: "data_studio/version_table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Version a table

Applies to: TBM Studio 12.0 and later

There may be times when the data in a table changes. For example, the accounts assigned to
departments may be changed at the beginning of a new fiscal calendar year. This can impact the
calculations in a model. You want to preserve the prior assignments so historical calculations
remain correct, but you want the new data to apply in the new fiscal year. To preserve the old data
and to support entering the new data, version the table.

The following rules apply to versions:

- You must check out a table to version it.
- Time must be configured for the project.
- You cannot delete a version if only one exists.
- You can only delete a version if the time is set to the first period in the version and a prior
  version exists.
- You cannot create a version if the time is set to the first period in the version.

To version a table, on the Home tab, click Create Version.

To delete a version, on the Home tab, click Remove Version.
