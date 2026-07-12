---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Cloud mapping"
breadcrumb: []
source_path: "configuration/cloudmapping.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cloud mapping

The cloud mapping feature (sometimes known as *tag mapping* provides the ability to
map cloud metadata (such as tags and accounts) to attributes in Apptio, such as Business Unit,
Application, etc. Mapping cloud data will allow you to see not only what cloud services are
consumed, but also to tag cloud billing data with information that helps you understand your cloud
spending and ownership.

## Before you begin

As a prerequisite, you need to decide whether to use direct mapping rules, which allow you to
populate the destination column from a predefined list of columns, or the table match rules, which
requires you to create your own rules table and define the column that populates the destination
column. If you plan to use table match rules, you need to create a rules table (for example,
TMRules\_2) prior to performing the following steps.

To create a rules table, do one of the following:

- Create a rules table in a format supported in TBM Studio, then upload it into TBM Studio.
- Create a rules table in TBM Studio and save it.

Example:

![](../../resources/images/ct_images/10077_1.png)

## About this task

- Mappings apply to both the monthly file (used in the Monthly TCO report) and the daily/hourly file (used in the Daily Transparency report).
- Changes to monthly reports appear immediately after the changes are saved in your In Development environment, then checked in to the Staging environment.
- Changes to daily reports appear as soon as the next bill is ingested via the pre-processor after clicking Promotion to Production in TBM Studio.

**NOTE** The cloud mapping feature is enabled for Cloud Cost Management (CCM) and Cloud
Business Management (CBM) only. It is not available for any other tables in Studio. Tables with
cloud mapping cannot use a formula step in their transform pipeline. If you need to add formulaic
logic to the transform pipeline, see [Adding a formula step to 12.6 cloud tables](addformulastep.html "Currently, Apptio does not support the addition of formula steps to AWS and Azure cloud tables. However, if the need arises (for example, if you need to modify Cost), use the following workaround.").

**NOTE** The DataLink AWS Connector can process Cost and Usage Report (CUR) bills

Types of mapping rules

The two types of mapping rules are available:

Direct mapping rules
:   - Each rule consists of 4 columns: 1 destination column | column 1 | column 2 | column 3
    - The rule will first try to populate the destination column with the value in column 1. If that column is empty, the value from column 2 is used. If that column is empty, the value from column 3 is used. If all columns are empty, the destination column will be empty.
    - The list of values for columns 1, 2, and 3 are pulled from the AWS table header.

Table match rules
:   - Each rule consists of 2 columns: 1 destination column | 1 rules input table
    - The rules table must have one column that matches the destination column that was selected. For example, if the destination column is Project, the rules table must contain a column named Project.
    - The rules table can only have input columns that are part of the original bill. In other words, the columns that are already output and processed cannot be used as input columns.

To map ap your cloud billing, do the following in the Development environment in TBM Studio:

## Procedure

1. From the Project Explorer, open one of the following cloud tables:
   1. AWS Cost and Usage Report Raw
   2. Azure EA Bill Raw
2. In the **Home** tab, click **Check Out**.

   ![](../../resources/images/ct_images/10077_2.png)
3. Click the **Add step** plus sign.
4. Click **Cloud Mapping**.

   **NOTE** The Cloud Mapping step appears (replacing the Formulas step) only after you select a
   cloud table.
5. Click **Add a new mapping**.

   ![](../../resources/images/ct_images/10077_3.png)
6. From the **Destination Column** list, select one or more columns to use as the
   source.
7. From the **Mapping Rule** list, select either **Direct Mapping** or **Table
   Match**. For a description of these rules, see the [Prerequisite](cloudmapping.html#base_file_name__prereq) section.

   ![](../../resources/images/ct_images/10077_4.png)
8. In the **Rule Input** lists, do one of the following:
   1. For direct mapping, in one or more of the drop-down lists, select the name of the
      column you want to use to populate the destination column.

      - The rule will first try to populate the destination column with the value in the first column
        list (for example, Application in the image). If that column is empty, the value in the second
        column list (for example, Business Unit) is used. If that column is empty, the value from the third
        column list (for example, Cost Center) is used. If all columns are empty, the destination column
        will be empty.
      - The list of values for columns 1, 2, and 3 are pulled from the AWS table header.
   2. For table matching, select the name of the rules table you created previously (for
      example, TMRules\_2).

      The rules table must have one column that matches the destination
      column that was selected. For example, if the destination column is "Project," the rules table must
      contain a column named "Project."
9. Check in your changes.

   The new column now appears in the CCM Monthly TCO report and in the Daily Transparency report
   (Daily/Hourly > Reports > Iaas Paas > Daily Transparency), but the data in the Daily Transparency
   report will not be accurate until after the next scheduled ingestion of cloud billing data (no more
   than 24 hours).

   Next, you need to promote to production to allow your changes to be used in the Daily/Hourly
   Transparency report.
10. Change to the **Staging** environment.
11. Click the **Project** tab.
12. Click **Lock**.
13. Click **Promotion Options**.
14. Click **Promote Now**.
15. When processing is complete, click **Unlock**so the next daily update can
    succeed.

    The mapping data will appear in the Daily/Hourly Transparency report after the next scheduled
    cloud bill is ingested (no later than 24 hours).

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
