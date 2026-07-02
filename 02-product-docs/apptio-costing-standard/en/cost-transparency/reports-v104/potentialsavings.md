---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Report Overview - Potential Savings"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Previous Version Layouts"
  - "Cloud Reports"
source_path: "cost-transparency/reports-v104/potentialsavings.html"
images:
  - "resources/images/ct_images/potentialsavings_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Report Overview - Potential Savings

Note: Applies to: [Apptio Costing Standard](https://community.apptio.com/docs/DOC-8364.html "(Opens in a new tab or window)") or [Apptio Cloud
Cost Management](https://community.apptio.com/docs/DOC-8365.html "(Opens in a new tab or window)") running on TBM Studio v12.3.3 or later.

## Overview

The Savings Recommendations reports provide a view into opportunities where costs could be
reduced by changing how or what cloud services are being consumed. The data that feeds Savings
Recommendations is currently sourced from AWS Trusted Advisor, an online resource to help AWS
customers reduce cost, increase performance, and improve security by optimizing their AWS
environments. Apptio surfaces the Cost Optimization subset of Trusted Advisor information allowing
Apptio customers to identify opportunities to reduce costs and understand how they have done in
terms of taking action against those opportunities over time.

These reports provide a high level view of the potential savings associated with inefficiently
used resources as well as the ability to drill deeper to get more information about those individual
resources.

Note: Data associated with the Reserved Instance Optimization check available from
Trusted Advisor is presented in the Reserved Instances reports, not in the Potential Savings
reports.

## Metrics and KPIs

- **Recommendation Count** — the total number of resource recommendations
- **Potential Savings** — the total amount of monthly savings that could be realized by acting
  on the recommendations
- **Potential Annual Net Savings** — the total amount of annual savings that could be realized
  by acting on the recommendations

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/potentialsavings_1.png)
