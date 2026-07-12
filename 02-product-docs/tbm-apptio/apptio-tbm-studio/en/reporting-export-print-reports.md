---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Export and Print Reports"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Advanced Reporting"
  - "Export and Print Reports"
source_path: "SSWRJM/studio/new-uc/howtoguides/create-reports/export-print-rep.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Export and Print Reports

Objective: Generate reports for distribution through PDF export, email delivery, print output, and automated subscriptions.

When to use: When sharing reports with stakeholders outside TBM Studio, creating scheduled report distributions, or producing printed materials for meetings and presentations.

Time estimate: 10-20 minutes per report

## Configure Print Layout

Before exporting or printing, configure the print layout to control how the report appears on paper or in PDF:

1. Check out the report.
1. From the Home tab, click View, then select Print Layout. The report switches to Print Layout mode.
1. Click the Print Layout tab to access layout options.
1. Configure page setup: Page size: Select from standard paper sizes Orientation: Portrait or Landscape Margins: Set page margins Scale: Zoom level for the printed output
1. Configure component flow: Manual: Components stay where you place them Vertical: Components arrange in a single column Horizontal: Components arrange in rows
1. Configure headers and footers: Header: Add text, HTML formatting, or dynamic text. Can appear on all pages or first page only. Footer: Add custom footer text (note: footers do not support dynamic text)
1. For individual components: Pin/Unpin: Move components (like slicers) to the end of the report Show/Hide: Control which components appear in the printed output
1. Click Save on the Print Layout tab to save your settings.
1. Click Exit Print Layout Mode to return to normal editing.
1. Check in the report.

## Configure Multi-Page Table Printing

For large tables that span multiple pages:

1. Enter Print Layout mode.
1. Move the table to its own page (tables print best when they have a dedicated page).
1. Select the table and on the Print Layout tab, click Resize Component to Full Page.
1. With the table selected, go to the Table subtab and check Print All Pages.
1. Save and exit Print Layout mode.

## Export to PDF

1. Display the report you want to export.
1. On the Home tab, click Export, then click PDF. The Export to PDF dialog appears.
1. Select an export option: Download PDF directly: Opens or downloads the PDF to your computer Include a link to the PDF in an email: Sends an email with a link to the PDF stored in TBM Studio Attach the PDF to an email: Sends the PDF as an email attachment
1. For email options, enter the recipient's email address.
1. Click OK to generate and export/email the PDF.

## Export to Excel

To export report data to Excel for further analysis:

1. Display the report.
1. On the Home tab, click Export, then click Excel.
1. The report data exports to an Excel workbook. Column order matches the report configuration.

## Export Tree View Tables

When exporting tree view (hierarchical) tables to Excel:

- All parent and child rows are exported
- The first column shows indentation indicators (>> symbols) to represent the hierarchy level
- The Excel export is a flat table representation (not a collapsible tree structure)

## Browser Requirements

For PDF export features to work correctly:

- Allow pop-ups from your Apptio URL in your browser settings
- PDFs may open in a new tab or appear in your browser's download bar depending on browser settings

Expected Results

- PDF exports use the configured print layout settings
- Email subscriptions deliver reports on the configured schedule
- Shared report links preserve the context (filters, date range) from when the link was created
- Excel exports include all visible table data with columns in the configured order

Common Pitfalls

- PDF not displaying correctly: Verify print layout is configured. Preview by clicking Export to PDF on the Print Layout tab before checking in.
- Email subscription fails: Verify recipient email addresses are in authorized domains for your environment.
- Headers/footers not appearing: Headers and footers are not visible in Print Layout Mode. Export to PDF to see them.

## Related Tasks

- Configure report permissions (Section 3.4)
- Create report collections (Section 3.3.1)
- Set up recurring builds (Section 6.1)
