---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Report overview - Reconcile"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Previous Version Layouts"
  - "Cloud Reports"
source_path: "cost-transparency/reports-v104/reconcile.html"
images:
  - "resources/images/ct_images/8094_1.png"
  - "resources/images/ct_images/8094_2.png"
  - "resources/images/ct_images/8094_3.png"
  - "resources/images/ct_images/8094_4.png"
  - "resources/images/ct_images/8094_5.png"
  - "resources/images/ct_images/8094_6.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Report overview - Reconcile

Note: Applies to: [Apptio Costing Standard](https://community.apptio.com/docs/DOC-8364.html "(Opens in a new tab or window)") or [Apptio Cloud
Cost Management](https://community.apptio.com/docs/DOC-8365.html "(Opens in a new tab or window)") running on TBM Studio v12.3.3 or later.

## Overview

With Cloud Cost Management, Apptio provides the ability to reconcile the costs and consumption in
Apptio with that reported by the cloud providers in their billing management consoles. The Reconcile
report in Cloud Cost Management includes flexible reports allowing you to reconcile at various
levels within your billing and isolate specific subsets of costs (for example, for a single or
subset of accounts) to reconcile at a deeper level.

## Reconciling your AWS costs

With Amazon Web
Services (AWS), you can reconcile your monthly spend against data AWS provides in their Billing
Dashboard. (Simply select Bill Details, then select the month against which you wish to
reconcile.)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_2.png)

Within Apptio, the Reconcile report
provides the ability to view both cost and usage quantity grouped and filtered by various billing
attributes, such as, but not limited to, Account ID (Payer and/or Linked), Product Name, Seller of
Record, and others. To start, you can group by just Payer Account ID to get a view of the total
monthly spend for an master payer account.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_3.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_4.png)

This total number should reconcile to the
total number in your AWS bill for the same month.

**NOTICE**

If you have not ingested your
AWS Marketplace bills and have AWS Marketplace charges, you will need to reconcile against the total
AWS Service Charges instead of the AWS total. For more information on ingesting your AWS Marketplace
bills, see [Ingesting AWS Marketplace billing](../user-guide/ingestingawsmarketplacebilling-6655.html "If you are consuming services from the AWS Marketplace, you will want to ingest and model those AWS Marketplace bills just as you ingest and model normal AWS service bills. AWS creates a separate AWS Marketplace billing file for those billing reports you have configured to be created in your billing preferences. As with normal AWS services bills, Apptio recommends using the AWS Marketplace Cost Allocation report that aggregates at monthly level.").

You may begin to add more detail or filter for
specific attributes to reconcile at a deeper level in your bill. For example, you may reconcile
specific linked accounts by selecting the LinkedAccount checkbox, or filtering for a specific
account in the LinkedAccount slicer. Then, in the AWS bill, you can select the Bill Details by
Account and compare across the two systems.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_5.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_6.png)

## Reconciling your Azure costs

To reconcile your Azure costs, you can view your cost in your Azure portal and reconcile them to
the costs in Apptio via the Microsoft Azure EA Detailed Bill report. Within the Apptio report, you
can vary the level and subset of items you wish to reconcile by using attribute pickers and
slicers.
