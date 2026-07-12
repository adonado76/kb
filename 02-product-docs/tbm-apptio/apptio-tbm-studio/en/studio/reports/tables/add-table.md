---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Add a table to a report"
breadcrumb: []
source_path: "studio/reports/tables/add-table.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep281.png"
  - "resources/images/studio_images/studioimages/studio/aug391.png"
  - "resources/images/studio_images/studioimages/studio/aug448_588x346.png"
  - "resources/images/studio_images/studioimages/studio/stu617.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a table to a report

**Applies to**: TBM Studio 12.0 and later

Add a table to a report by clicking the **Home** tab, clicking **New**, and clicking
**Table**. Add an editable table to a report by copying the table to the Report Clipboard and
pasting it into the report.

1. Open the report and check it out.
2. From the **Report** tab, click **Table**. The application adds a placeholder to the report
   and opens the **Ad Hoc Component Configuration** panel as shown in the following image:

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu617.png)
3. Use the **Ad Hoc Component Configuration** panel to build the table.
4. To build the table, open the sections in the **Project Explorer** and drag fields into the
   four areas of the **Configuration** panel.

## Example

We describe how to build the table shown below.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug391.png)

The table is based on:

- A table called Data Centers
- Two metrics: Cost and YTD Cost

When you are done building the table, the **Ad Hoc Component Configuration** panel will look
like the panel shown below:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep281.png)

To build the table:

1. Open a report.
2. On the **Home** tab, click **New**, and then click **Table**.A table placeholder is
   added to the report and the **Ad Hoc Component Configuration** panel is displayed.
3. In the **Project Explorer**, click the **Tables** section, click **Data Centers Info**,
   and drag **Data Center** to the **Rows** section of the **Configuration** pane as shown in
   the following image:

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug448_588x346.png)
4. In the **Project Explorer**, click the **Metrics** section.
5. Drag the Cost metric into the **Values** section of the **Configuration** pane.
6. Drag the YTD Cost metric into the **Values** section of the **Configuration** pane.
