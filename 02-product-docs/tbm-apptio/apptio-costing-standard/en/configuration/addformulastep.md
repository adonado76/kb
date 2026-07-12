---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Adding a formula step to 12.6 cloud tables"
breadcrumb: []
source_path: "configuration/addformulastep.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Adding a formula step to 12.6 cloud tables

Currently, Apptio does not support the addition of formula steps to AWS and Azure cloud
tables. However, if the need arises (for example, if you need to modify Cost), use the following
workaround.

Applies to: Cloud on Costing Standard and Cloud Business Management (CBM) on TBM Studio 12.6 or
later

To add a formula step to your monthly AWS report, do the following:

## Procedure

1. Unappend the **AWS Cost and Usage Raw** from the **AWS Cost** and **Usage Master
   Data**.
2. Create a transform off of the last step in the pipeline Table and name it **AWS Cost and Usage
   Transform**. Place it in the **Cloud Service Provider Category**.
3. Append the **AWS Cost and Usage Transform** into the **AWS Cost and Usage Master
   Data**.
4. Map the following fields:

   - Cost = Provider Unblended Cost
   - Provider Cost = Provider Unblended Cost
   - RowID = Row ID

**Parent topic:** [Costing Standard](../home.html)

## 

To add a formula step to your monthly Azure report, do the following:

### Procedure

1. Unappend the **Azure EA Bill Raw** from the **Azure EA Bill Master Data**.
2. Create a transform off of the last step in the pipeline Table, and name it Azure EA Bill
   Transform. Place it in the Cloud Service Provider Category.
3. Append the Azure EA Bill Transform into the Azure EA Bill Master Data. All fields should map
   automatically.

### Example

![](../../resources/images/ct_images/10838_1.png)![](../../resources/images/ct_images/10838_2.png)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
