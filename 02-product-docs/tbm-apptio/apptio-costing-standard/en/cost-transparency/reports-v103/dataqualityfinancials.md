---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Data Quality - Financials report"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Previous Version Layouts"
  - "Data Quality Reports"
source_path: "cost-transparency/reports-v103/dataqualityfinancials.html"
images:
  - "resources/images/ct_images/dataqualityfinancials_1.png"
  - "resources/images/ct_images/dataqualityfinancials_2.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Data Quality - Financials report

Applies to: Costing Standard 11.8.x running on either TBM Studio v12
or TBM Studio v11.

## Introduction

The Financials report focuses on the unallocated costs.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/dataqualityfinancials_1.png)

## Navigation

Data Quality > Financials

## Roles

This report is designed for TBM administrators.

## Objectives

Use this report to analyze the allocations for the financials layer of the cost model shown
below. The report focuses on the Cost Source data set and the specific records that are not flowing
up the model.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/dataqualityfinancials_2.png)

Specific objectives include the following:

- Quickly see unallocated costs from the financial layer.
- Assess unallocated cost trends over time by IT Financial model objects.
- Identify unallocated costs by IT Financial model objects.
- Review allocation strategies for the IT Financial objects in the model (e.g. Cost Source,
  Labor, Fixed Assets, etc.).

## Questions answered

The information presented on this report can be used to answer the following questions:

- Which specific records are not being allocated to one of the destination objects (Labor,
  Fixed Assets, etc.)?
- Can I see any patterns that might identify the error?
- Are all the important fields which drive my allocations complete and valid?

## Next actions

- Export specific records to review and fix.
- Adjust or correct allocation rules in Studio.
- Correct data in the source data or through data transforms in Data Studio.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
