---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Print and Export Settings"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Properties"
  - "Print and Export Settings"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/print-export-settings.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Print and Export Settings

Print layout settings control how reports appear when exported to PDF format or printed. These settings can be customized per report to optimize the printed output.

Accessing Print Layout Mode

1. Check out the report
1. On the Home tab, click View > Print Layout
1. The Print Layout tab becomes available for configuration

Page Setup Options

| Option | Description |
| --- | --- |
| Option | Description |
| Page Size | Select paper size from the dropdown (Letter, A4, Legal, etc.) |
| Orientation | Portrait (vertical) or Landscape (horizontal) page orientation |
| Margins | Configure top, bottom, left, and right margins |
| Flow | Manual: Components stay where placed. Vertical: Components arrange in a single column. Horizontal: Components arrange in rows with maximum components per row. |

Headers and Footers

Header options:

- Display on all pages or first page only
- Resize by dragging header boundaries
- Format text using HTML tags
- Use dynamic text (e.g., <%=CurrentDate()%> for current period)

Footer options:

- Customize left, center, and right footer sections
- Specify footer text or leave blank for no footer
- Dynamic text is not supported in footers

Component Print Options

| Option | Description |
| --- | --- |
| Option | Description |
| Pin/Unpin | Pin a component (such as slicers) to the end of the report to capture applied filters |
| Show/Hide | Hide specific components from the printed output. Use the Filter field to search for components in long lists. |

Export Options

Reports can be exported using the following methods:

| Export Method | Description |
| --- | --- |
| Export Method | Description |
| Download to PDF directly | Generates PDF and opens in browser or downloads based on browser settings |
| Include link to PDF in email | Sends email with a link to access the generated PDF |
| Attach PDF to email | Sends email with the PDF as an attachment |
