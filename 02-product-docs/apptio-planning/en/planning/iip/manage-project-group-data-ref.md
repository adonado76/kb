---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Manage Project Group reference data"
breadcrumb: []
source_path: "planning/iip/manage-project-group-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Manage Project Group reference data

The Project Group reference data represents the hierarchical project or portfolio structure of
your organization.

1. In the navigation menu, select Reference Data > Standard Dimensions > Project Group.
2. Update the data table values as required:
   - Code - The unique identifier for a project group.
   - Name - The project group's name.
   - Parent Code - Represents your project group's hierarchy. A Parent Code value is the code value
     of its immediate higher-level or parent account (if any).
   - Currency Code - The common currency for the Project Group. This value is required when support
     for multiple currencies is enabled in the Company Profile. The common currency value should be the
     three-letter ISO code for the currency. If no currency code is entered, the default common currency
     is used.
   - Cost Center Code - The identifier for corresponding Cost Centers. When importing actuals, they
     are allocated per Cost Center, then mapped to Cost Object or dependent dimensions. A project can be
     associated with multiple Cost Centers and can include line items (volumes, labor, or expenses)
     recorded for more than one Cost Center. Add multiple Cost Centers to the table cell using a comma to
     separate them.
