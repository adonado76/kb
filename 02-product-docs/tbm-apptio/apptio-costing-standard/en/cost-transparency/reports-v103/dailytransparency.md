---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Report Overview - Daily Transparency"
breadcrumb: []
source_path: "cost-transparency/reports-v103/dailytransparency.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Report Overview - Daily Transparency

Applies to: ApptioCosting Standard or Apptio Cloud Cost Management running on
TBM Studio v12.3.3 to 12.5.x.

## Overview

The Daily Transparency report provides a view into your AWS spend as of the current point in time
and allows drilling into a fine grain of cost detail down to the hourly level. This report is fed by
the AWS Detailed Billing Report with
Resources and Tags (DBR) and is updated on a daily basis.

The Daily Transparency report integrates the AWS Cost and Usage Report (CUR) and the
Enterprise Agreement (EA) billing APIs for Azure.

## Metrics and KPIs

Note: All costs are sourced from the Unblended Cost in the AWS DBR and does not include most
monthly line items such as tax or enterprise support. It does include Reserved Instance purchase
costs for those hours where Reserved Instances were utilized.

Cloud Invoice Cost MTD
:   The cost incurred as of the last day reported for the currently selected month.

Prev Month Invoice Cost MTD
:   The cost incurred as of the same day during the previous month

Current Month Cloud Invoice Forecast
:   An estimate of the projected cost by the end of the current month. This value is calculated as a linear projection of the cost incurred month-to-date.

Prev Month Invoice Cost
:   The full month cost for the previous month.

Daily Cloud Invoice Cost
:   The cost invoiced for the day indicated.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
