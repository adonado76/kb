---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Print and export reports"
breadcrumb: []
source_path: "studio/reports/printexportreports.html"
images:
  - "resources/images/studio_images/export-pdf-options.png"
  - "resources/images/studio_images/print-1.png"
  - "resources/images/studio_images/print-2.png"
  - "resources/images/studio_images/send-email_955x567.png"
  - "resources/images/studio_images/ugly-url.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Print and export reports

**Applies to**: Apptio TBM Studio R12.5 and later. TBM Studio relies
on exporting reports to PDF format for report printing and sharing outside of the TBM suite. The
TBMA or TBM Studio Admin can customize the PDF layout options per report for all Apptio users when
printing or emailing reports.

All users of Apptio costing applications (such as Costing Standard) can then export a report to
PDF format or email the report in PDF format. When they do so, the exported PDF will use the layout
options set via the instructions below.

**SEE ALSO**: [Best Practices: Printing to PDF](https://community.apptio.com/docs/DOC-9644 "(Opens in a new tab or window)")

## Create custom report layouts for PDF export

TBMAs can set layout options per report in TBM Studio.

1. Check out the report you want ([How?](../admin/bp-check-out.html "(Opens in a new tab or window)")).
2. From the **Home** tab, click **View**, and then select
   **Print Layout**.TBM Studio switches to Print Layout mode.
3. Click the **Print Layout** tab.

   ![](../../resources/images/studio_images/studioimages/studio_export%20to%20pdf_exit%20print%20layout%20mode.png)

   Tip: To exit this mode at any time, on the **Print Layout**
   tab, click **Exit Print Layout Mode**
4. Select a specific component in the report, and then make the components changes you want.
   Components options include:

   | Option | Description |
   | --- | --- |
   | **Pin/Unpin** | You can pin a single component to the end of a report. A typical use of this feature is to move slicers to the end of a report to capture the filtering applied to the report. Also, you can pin all components of a selected type to the end of a report. For example, you can pin all slicers to the end of a report. |
   | **Show/Hide** | You can hide a single component in a report. To hide multiple components, click **Show/Hide Report Components**, and then clear the boxes of the components you want to hide.**TIP**: To filter a long list of components to a specific set of components, enter text in the **Filter** field. |
5. Make the print layout changes you want. Page Setup options include:

   | Option | Description |
   | --- | --- |
   | **Page size** | Select a paper size from the drop-down menu. |
   | **Flow** | Flow controls the placement of the components in the Report page.  **Manual** - You place the components. Once placed, the objects will not move.  **Vertical** - The components are arranged automatically in a single vertical column.  **Horizontal** - The components are arranged automatically in rows, with the maximum number of components placed in each row. |
   | **Margins** | Select the margin settings you want. |
   | **Header** | You can add a header to a report. The header can be displayed on all pages or displayed only on the first page. You can change the size of the header by dragging the borders of the header box. You can format the text in the header using HTML format tags. Also, you can use dynamic text in the header. For example, the following dynamic text will add the current period: <%=CurrentDate()%> |
   | **Footer** | You can fully customize the footer. If you want a blank footer, clear the text in the Footer Left field, select the Specify footer text, and leave the field blank. Unlike headers, you cannot use dynamic text in the footer. |
   | **Portrait** | Click this option for vertical page orientation. |
   | **Landscape** | Click this option for horizontal page orientation. |
   | **Scale** | Select the zoom level you want applied. |
6. Click **Save** on the **Print Layout** tab to save your
   print layout settings, and then click **Exit Print Layout Mode**.
7. Check the report in.

Tip:

- If you've saved changes in the current Print Layout session but decide you want to cancel your
  saved changes, click **Update Layout from Report**. You can also revert to your
  last saved state in the current Print Layout session: click **Revert
  Layout**.
- Not all page layout changes you make will be visible in the Print Layout Mode (headers and
  footers are not visible, for example). You can preview your changes by clicking **Export to
  PDF** on the **Print Layout** tab. The PDF will open in a new tab.
- To get a high-fidelity preview of a report's custom layout in PDF format, complete the task
  "Export a report to a PDF file" described below, and select the **Download PDF
  directly** option.

Note: During export of excel, the order of the column is maintained as configured in the report
component. Remaining columns from which are not part of report are appended.

## Configure a table to print all rows across multi-pages

1. Checkout a report
2. From the **Home** tab, select **View**, and then select
   **Print Layout**.
3. Move the table to its own page.
4. Select the table and from **Print Layout** tab, select **Resize Component to
   Full Page**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/print-1.png)
5. Select the table and from **Table** subtab, select **Print All
   Pages**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/print-2.png)
6. Once the report is printed to PDF, the table will print across multiple pages.

## Export a report to a PDF file

TBMAs can generate and share a PDF rendering of a report.

To export a report in TBM Studio:

1. In the Project Explorer, display the report you want.
2. On the **Home** tab, click **Export** and then click
   **PDF**.The Export to PDF dialog box appears.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/export-pdf-options.png)
3. Click **Download to PDF directly**, and then click OK.The PDF rendering of
   the report is created. Depending on your browser's setting, it might open in a new window or tab, or
   appear on your browser's download bar ready for opening or saving.

## Email a report in PDF format to another Apptio user

You can generate the PDF rendering of a report and email it to a recipient. You can either email
a link to the PDF or send the PDF as an email attachment.

To email a report in TBM Studio:

1. In the Project Explorer, display the report you want.
2. On the **Home** tab, click **Export** and then click
   **PDF**.The Export to PDF dialog box appears.
3. Do one of the following:
   - Click **Include a link to the PDF in an email**.
   - Click **Attach the PDF to an email**.
4. The logged in user's email id is populated by default. If you wish to change, enter the
   appropriate email address.
5. Click **OK**.

   The sample email that receiver gets is -

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ugly-url.png)

   Note: If you open the report link in
   the email, you will see the report in the same context, i.e., any filters, slicers, pickers, and
   date-range applied will persist and the report will appear exactly as shared by the
   sender.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/send-email_955x567.png)

## Export a report to a PDF file in a TBM costing application

When completing this task, the exported PDF will use the layout options set with the "Create and
manage custom report layouts for PDF export" task, above.

1. Start the application (for example, Costing Standard) and view the report.
2. On the far-right edge of the report collection title bar, click the
   **Export** button, and then click **PDF**.![](../../resources/images/studio_images/studioimages/studio_print%20export%20reports_button.png)The Export to PDF dialog box appears.
3. Do one of the following:
   - Click **Download PDF directly**, and then click **OK**.
     The PDF rendering of the report is created. Depending on your browser's setting, it might open in a
     new window or tab, or appear on your browser's download bar ready for opening or saving.
   - Click **Include a link to the PDF in an email**, enter the recipient's email
     address, and then click **OK**.
   - Click **Attach the PDF to an email**, enter the recipient's email address,
     and then click **OK**.When emailing a link or attachment, the sender is
     identified as noreply@apptio.com.

Note: For certain features in Apptio, such as Export to PDF, users must allow pop ups in their
browser from their Apptio URL ([How?](https://community.apptio.com/docs/DOC-9655 "(Opens in a new tab or window)")).
