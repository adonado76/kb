---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Manage Project reference data"
breadcrumb: []
source_path: "planning/iip/manage-project-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Manage Project reference data

The following information describes the Project dimensions' fields.

1. In the navigation menu, select Reference Data > Standard Dimensions > Project.
2. Update the data table values as required:
   - Code - The unique identifier for a project.
   - Name - The project's name.
   - Parent Code - Represents your project hierarchy. A Parent Code value is the code value of its
     immediate higher-level or parent account (if any).
   - Allow Any Cost Center - A value of TRUE allows you to assign the project to any Cost Center. A
     value of FALSE defaults to the current Cost Center.
   - Default Cost Center - The default value, unless a different Cost Center code value is
     provided.
   - Description - A summary of the project.
   - Cost Center Code - The identifier for corresponding Cost Centers. When importing actuals, they
     are allocated per Cost Center, then mapped to Cost Object or dependent dimensions. A project can be
     associated with multiple Cost Centers and can include line items (volumes, labor, or expenses)
     recorded for more than one Cost Center. Add multiple Cost Centers to the table cell using a comma to
     separate them.
