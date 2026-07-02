---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Export and Print Reports"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Advanced Reporting"
source_path: "studio/new-uc/howtoguides/create-reports/export-print-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Export and Print Reports

**Objective:** Generate reports for distribution through PDF export, email delivery,
print output, and automated subscriptions.

**When to use:** When sharing reports with stakeholders outside TBM Studio, creating
scheduled report distributions, or producing printed materials for meetings and
presentations.

**Time estimate:** 10-20 minutes per report

## Configure Print Layout

Before exporting or printing, configure the print layout to control how the report appears
on paper or in PDF:

1. Check out the report.
2. From the Home tab, click View, then select Print Layout. The report switches to Print
   Layout mode.
3. Click the Print Layout tab to access layout options.
4. Configure page setup:
   - **Page size:** Select from standard paper sizes
   - **Orientation:** Portrait or Landscape
   - **Margins:** Set page margins
   - **Scale:** Zoom level for the printed output
5. Configure component flow:
   - **Manual:** Components stay where you place them
   - **Vertical:** Components arrange in a single column
   - **Horizontal:** Components arrange in rows
6. Configure headers and footers:
   - **Header:** Add text, HTML formatting, or dynamic text. Can appear on all pages
     or first page only.
   - **Footer:** Add custom footer text (note: footers do not support dynamic
     text)
7. For individual components:
   - **Pin/Unpin:** Move components (like slicers) to the end of the report
   - **Show/Hide:** Control which components appear in the printed output
8. Click Save on the Print Layout tab to save your settings.
9. Click Exit Print Layout Mode to return to normal editing.
10. Check in the report.

Tip: Use dynamic text in headers to include the current period. For example:
<%=CurrentDate()%> displays the report period automatically.

## Configure Multi-Page Table Printing

For large tables that span multiple pages:

1. Enter Print Layout mode.
2. Move the table to its own page (tables print best when they have a dedicated page).
3. Select the table and on the Print Layout tab, click Resize Component to Full Page.
4. With the table selected, go to the Table subtab and check Print All Pages.
5. Save and exit Print Layout mode.

## Export to PDF

1. Display the report you want to export.
2. On the Home tab, click Export, then click PDF. The Export to PDF dialog appears.
3. Select an export option:
   - **Download PDF directly:** Opens or downloads the PDF to your computer
   - **Include a link to the PDF in an email:** Sends an email with a link to the PDF
     stored in TBM Studio
   - **Attach the PDF to an email:** Sends the PDF as an email attachment
4. For email options, enter the recipient's email address.
5. Click OK to generate and export/email the PDF.

Note: When you share a report link via email, the recipient sees the report in the same
context as when you share it. Any filters, slicers, and date range selections are
preserved.

## Create Email Subscriptions

Set up automated recurring report delivery via email:

1. Navigate to the report you want to subscribe to.
2. Click the Export icon and select Email Subscription. This option is available for TBM
   Administrators.
3. In the Email Subscription dialog, configure the subscription:
   - **Subscription name:** A descriptive name for the subscription
   - **Recipients:** Email addresses (must be from authorized domains in your
     environment)
   - **Schedule:** Daily, weekly, or monthly delivery
   - **Include print layout view:** Attach the PDF with configured print layout
   - **Include link with slicer selections:** Include a hyperlink to the report with
     pre-applied filters
4. Click Save to create the subscription.

Warning: Row-Level Security (RLS) is not applied to email subscriptions. All
recipients see the full report data. Consider this when distributing reports with sensitive
information.

## Manage Email Subscriptions

To view and manage existing subscriptions:

1. From the report, click Export > Email Subscription.
2. Click on Manage Subscriptions.
3. From here you can:
   - View all subscriptions for the report
   - Edit subscription settings
   - Enable or disable subscriptions
   - Delete subscriptions

## Export to Excel

To export report data to Excel for further analysis:

1. Display the report.
2. On the Home tab, click Export, then click Excel.
3. The report data exports to an Excel workbook. Column order matches the report
   configuration.

Note: Excel limits sheet names to 31 characters. Report names longer than this limit are
truncated with "-0" appended.

## Export Tree View Tables

When exporting tree view (hierarchical) tables to Excel:

- All parent and child rows are exported
- The first column shows indentation indicators (>> symbols) to represent the hierarchy
  level
- The Excel export is a flat table representation (not a collapsible tree structure)

## Browser Requirements

For PDF export features to work correctly:

- Allow pop-ups from your Apptio URL in your browser settings
- PDFs may open in a new tab or appear in your browser's download bar depending on browser
  settings

**Expected Results**

- PDF exports use the configured print layout settings
- Email subscriptions deliver reports on the configured schedule
- Shared report links preserve the context (filters, date range) from when the link was
  created
- Excel exports include all visible table data with columns in the configured order

**Common Pitfalls**

- **PDF not displaying correctly:** Verify print layout is configured. Preview by
  clicking Export to PDF on the Print Layout tab before checking in.
- **Email subscription fails:** Verify recipient email addresses are in authorized
  domains for your environment.
- **Headers/footers not appearing:** Headers and footers are not visible in Print Layout
  Mode. Export to PDF to see them.

## Related Tasks

- Configure report permissions (Section 3.4)
- Create report collections (Section 3.3.1)
- Set up recurring builds (Section 6.1)

**Parent topic:** [Advanced Reporting](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
