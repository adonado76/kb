---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Troubleshoot reference data deletion errors"
breadcrumb: []
source_path: "planning/ts-reference-data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Troubleshoot reference data deletion errors

## About this task

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles.

If you delete an attribute and attempt to publish a dimension in reference data, you may receive
the following error:**Insert Image (itp\_publish-error-dialog.png)**

## Procedure

Many built-in dimensions have dependencies on other dimensions. For more information, see
[Reference data attribute and
dimensions dependencies](manage-reference-data.html).

For example, a Department dimension may contain a Cost
Center. Removing that Cost Center dimension would result in an error. To avoid receiving this error,
you must first remove the related dimension before you can remove the original dimension.

1. Export the affected reference data tables. For more information, see [Download and populate reference
   data tables or templates](manage-reference-data.html).
2. Edit the template as needed to remove the affected data.
3. Import and publish the updated reference data table. For more information, see [Import and publish reference
   data](manage-reference-data.html).

Note: If you continue to encounter issues, you can delete the contents of both dimensions and
re-import them.
