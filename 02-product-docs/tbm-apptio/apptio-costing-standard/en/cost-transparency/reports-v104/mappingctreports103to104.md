---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Mapping Costing Standard reports from Template v103 to v104"
breadcrumb: []
source_path: "cost-transparency/reports-v104/mappingctreports103to104.html"
images:
  - "resources/images/ct_images/102-8842-17-189949_349-311_publiccloud.png"
  - "resources/images/ct_images/102-8842-17-189952_301-317_saas_insights.png"
  - "resources/images/ct_images/102-8842-17-189954_vendors.png"
  - "resources/images/ct_images/102-8842-17-189955_294-265_infrastructureinsights.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapping Costing Standard reports from Template v103 to v104

Note: Applies to: Costing Standard on TBM Studio 12.3 and later, with Template v104 and later ([Learn more](ctreportcollections104-plus.html))

The following list maps the movement and elimination of the Costing Standard Template v103
reports to Costing Standard running on TBM Studio 12.3+ with Template v104.

To understand the difference between the templates, go to [Compare v104 and v103 Costing Standard reports](comparev103v104reports.html).

For instructions about upgrading to Template v104, go to [Upgrade Costing Standard to
v104](../user-guide/upgradectto104-8841.html "This document describes the reasons behind the Costing Standard user interface (UI) upgrade and the recommended steps for upgrading Apptio application content from Template v103 to the latest version of the application template.").

## Analyst report collection

The **Analyst** collection (v103) has been eliminated and individual reports have been
moved:

- **Analyst – Applications** moved to the new Applications report collection as **Applications
  List**.
- **Analyst – Labor** moved to the new Labor report collection as **Labor Analysis**.
- **Analyst – Projects** moved to the new Projects report collection as **Project
  List**.
- **Analyst – Vendor** moved to the new Vendor report collection as **Vendor List**.

## CIO Dashboards report collection

The CIO Dashboards collection (v103) has been replaced with a new TBM Overview report
collection:

- **CIO Summary**has been replaced with the new**TBM Dashboard**summary.
- **Cost Transparency Summary**has been eliminated; the old layer views have been moved to new
  report collections.
- **Public Cloud Summary**moved to the new Public Cloud report collection.
- **Benchmarking Summary**moved to the new Benchmarking report collection.

## Infrastructure Optimization report collection

A new Infrastructure & Cloud report collection has been created for v104. It includes the
following reports:

- **IT Ops - Summary**
- **IT Ops - Server TCO**
- **IT Ops - Storage TCO**

The **Infrastructure Optimization** reports (v103) moved to the new Infrastructure Insights
module (from the Projects menu):

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189955_294-265_infrastructureinsights.png)

The following infrastructure reports can be found in this new Infrastructure Insights module
(from the **Projects** menu):

- **IT Ops - Servers Analysis**
- **IT Ops - Storage Analysis**
- **IT Ops - Data Centers Analysis**
- **IT Ops - Service Desk Analysis**

The following Infrastructure Optimization reports (v103) have been eliminated:

- **IT Ops - Servers - Efficiency Target**
- **IT Ops - Storage - Efficiency Target**

## IT Finance report collection

The IT Finance report collection (v103) moved to the new IT Financials report collection:

- **IT Finance – Summary** has been replaced by the new [Financial Review report
  (v104)](../reports-v107/itfmf-ct_financialreview107.html).
- **IT Finance – Outliers** has been replaced by the new [Financial Variance Review email
  report (v104)](itfmf-ct_financialvariancereviewemail104.html).
- **IT Finance - Cost Pools** is unchanged, but it now titled [Cost Pool Analysis report (v104)](itfmf-ct_costpoolanalysis104.html).
- **IT Finance – Labor** has been replaced with the **Labor Review** report
  in the new Resources report collection.
- **IT Finance – Fixed Assets** moved to the new Resources report collection.
- **IT Finance – Vendors** moved to the new Vendors report collection and broken into multiple
  reports.
- **IT Finance – Cloud Service Provider Bill Summary** has been eliminated.
- **IT Finance - ITPF Integration** has been eliminated, and the following reports have been changed:
  - **ITP – Labor Budget** and **ITP – Labor Forecast** have been consolidated and moved to
    the new Resources report collection.
  - **ITP – Asset Budget** and **ITP – Asset Forecast** have been consolidated and moved to
    the new Resources report collection.
  - **ITP – Contract Budget** and **ITP – Contract Forecast** have been consolidated and moved
    to the new Vendors report collection.

## IT Management report collection

The IT Management report collection (v103)has been reorganized into the following new report
collections for v104:

- **IT Management – Summary** has been replaced by the [Financial Review report
  (v104)](../reports-v107/itfmf-ct_financialreview107.html) in the new IT Financials report collection.
- **IT Management – Financials** has been replaced by the IT Financial Review report in the new
  IT Financials report collection.
- **IT Management – Projects** moved to the new Projects report collection and split into
  multiple reports.
- **IT Management – IT Towers** moved to the new Resources report collection.
- **IT Management – Public Cloud** moved to a new Public Cloud module outside of Costing Standard.
- **Application Portfolio** moved to the new Applications report collection and split into
  multiple reports.
- **IT Management – Services** moved to the new Services report collection and split into
  multiple reports.
- **IT Management – Business Units** moved to the new Business Units report collection and
  split into multiple reports.

## Benchmarking report collection

The Benchmarking report collection was changed in very little for v104, except for the
following:

- **Benchmark Summary** moved from the CIO Dashboards report collection to the new Benchmarking
  report collection.
- Reports were updated per ATUM v.2.
- **Communications** report was eliminated.

## Mobile report collection

The entire Mobile report collection was eliminated, including the following reports:

- **iPad CIO Dashboard – Finance**
- **iPad CIO Dashboard – Labor**
- **iPad CIO Dashboard – Projects**
- And so forth

## Public Cloud

The Public Cloud report collection moved to the new Public Cloud module (available from the
Projects menu).

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189949_349-311_publiccloud.png)

## SaaS Insights (new)

A new SaaS Insights module has been added (available from the Projects menu), that provides cost
and licensing analytics about the following applications:

- Office 365
- Salesforce
- Service Now
- Workday![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189952_301-317_saas_insights.png)

## Vendor Insight

Vendor Insight has been moved from being a separate module (from the Projects menu) to inside
Costing Standard as a new Vendors report collection.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189954_vendors.png)

## See also

[Compare v104 and v103 Costing Standard
reports](comparev103v104reports.html)
