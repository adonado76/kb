---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Import Actuals"
breadcrumb: []
source_path: "it-planning/planning/import-publish-actuals.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Import Actuals

To help manage spend, you compare the budget plan or forecast with historical actuals. The source
of actuals may be your financial management system, TBM Studio, or Costing Standard.

## Populate the actuals .csv file

Import actuals one month at a time. To import each month:

1. In the navigation menu, select Spend Management > Transactions.

   Note:

   The Enforce View Permissions feature can be enabled in the Company Profile. See [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning."). If
   the feature is enabled, the Spend Management page is visible only to the following:
   - Budget Process Owners
   - Admins
   - Budget Owners (who are able to view only the transactions for their permitted Cost Objects)
2. Select Actions > Export Template to download a template you can populate with your actuals data.
   Your Apptio Planning application downloads the transaction items template in .csv format.
3. Open the downloaded .csv file.
   - Do not rename the column headings in this template. The Apptio Planning application requires
     this data structure.
   - Column headers in the template must be in your files in order to import. Column headers can be
     reordered.
   - Optionally, add custom dimension column headings to the template (see [Add and manage custom attributes of
     dimensions)](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.").
4. Paste the actuals data for the month into the template, ensuring you match the exact structure
   shown in the template. Add Cost Center and Cost Object information. Cost Objects without Cost
   Centers will not receive actuals.
5. Save the template in .csv format to your local drive.

## Import the actuals .csv file

1. In the navigation menu, select Spend Management > Transactions.
2. Select a year and month to receive the actuals.
3. Select Actions, then select from the following:
   - Import Actuals - Import a .csv file containing your actuals.
   - Import from Costing Standard - Import actuals from Costing Standard (see [Integrate
     with Cost Transparency](integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.")).
4. Navigate to the .csv file you want, then click Import.

## Open and view the actuals

1. In the navigation menu, select Spend Management, then select a month to view
2. Select Open Month.

When actuals are imported, actuals and plan amounts appear on two separate line items on the
Summary or Ledger page. See [Analyze a plan or forecast](analyze-plan-forecast.html). Note that:

- Budget owners can edit attributes of forecast line items while still being able to align actuals
  to plan. You can group line items to view actual and plan values on a single line item and save
  these settings to a view using the Custom Layouts feature (see [Customize, save, and share table layouts)](customize-save-share.html).
- You can add custom attributes to the table which can help capture supplemental information to
  enhance analysis and reporting (see [Add
  and manage custom attributes of dimensions)](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.").
- When entering data in a table, you can enter a quarterly or annual value and that amount will be
  proportionally distributed between months.
- If your organization runs both Planning and Apptio Costing Standard, you can integrate the two to share data (see [Integrate with Cost Transparency)](integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.").
