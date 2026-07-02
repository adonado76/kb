---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "ServiceNow Reports"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "ServiceNow"
source_path: "cost-transparency/technology-integration/servicenow/sn-reports.html"
images:
  - "resources/images/ct_images/snr1.jpg"
  - "resources/images/ct_images/snr2.jpg"
  - "resources/images/ct_images/snrep-1.jpg"
  - "resources/images/ct_images/snrep-2.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# ServiceNow Reports

While no specific ServiceNow reports exist in IBM Apptio Costing today, the integration
(specifically the automated Ingress of key ServiceNow datasets) significantly enhances existing
IBM Apptio reports and capabilities. Producing data-driven, defensible, best-in-class financial
intelligence.

The IBM Apptio Costing report collections mostly impacted are:

- Services
- Applications
- Products
- Infrastructure
- Tickets/Service Desk
- Projects

On the ServiceNow side, the IBM Apptio Egress pushes Application and Service Total Cost of
Ownership (TCO) from IBM Apptio into native ServiceNow dashboards.

**IBM Apptio Service TCO in ServiceNow Digital Portfolio Management (DPM)**

IBM Apptio’s Service TCO appears natively within ServiceNow DPM, providing Digital Product
and Service Owners with comprehensive cost visibility across plan–build–run activities. By
combining operational data from the CMDB with Apptio’s financial model, users gain insight
into key cost drivers, breakdowns, and trends for each service. This enables more informed
prioritization, better budgeting and forecasting, and a unified understanding of the financial
performance of the digital portfolio.

The report provides (from top to bottom):

- A gateway to IBM Apptio for more detailed report analysis (the IBM Apptio landing page can
  be set in the respective ServiceNow properties)
- Key metrics such as the Monthly and Year-to-date Total Cost of Ownership (TCO)
- Cost Trend Analysis spanning 6months

  ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snrep-1.jpg)
- Key Cost driver analysis (2 views), nominated with your choice of breakdowns, as sourced
  from IBM Apptio’s cost model
- Visibility into the Top 5 Service Offerings in terms of Monthly change and impact

  ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snrep-2.jpg)

**IBM Apptio Application TCO in ServiceNow Enterprise Architecture (EA)**

The integration brings IBM Apptio’s Application TCO directly into ServiceNow EA, enabling
Enterprise Architects to assess applications using both architectural context and financial
impact. Application rationalization decisions—such as invest, sustain, migrate, or retire—are
now informed by trusted TCO data, cost drivers, and alignment to investment objectives. This
gives EA teams a single, consistent source of financial truth to prioritize modernization,
eliminate redundancy, and optimize the application portfolio.

Two reports are lit up with IBM Apptio’s Application TCO numbers.

**Report 1:**Dedicated Portfolio TCO Tab on the Enterprise Architecture Dashboard. This
Tab delivers:

- Total Application TCO views trended over time
- Application TCO pivoted by critical dimensions such as Application Category and Planned
  Disposition (Invest, Sustain, Migrate, Retire)
- Application TCO as part of a ServiceNow calculated Application TCO Score. This score helps
  understand the relative distribution/weight of the various Applications. E.g.: Do we have
  many low or high-cost Applications
- Application TCO presented on 2 axes:
  - One being the Planned Disposition (Invest, Sustain, Migrate, Retire)
  - Other one being a breakdown, as nominated with your choice and sourced from IBM
    Apptio’s cost model. This could be e.g.: Cost Pool or Resource Tower.

This view quickly helps identify which areas have significant cost associated with it. E.g.:
For the applications marked as “Retire”, the bulk of the costs sits in the “Compute” Resource
Tower

![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snr1.jpg)

**Report 2:**TCO Dimension available on the Application Rationalization Dashboard

The Application Rationalization Dashboard is an out-of-the-box dashboard from ServiceNow that
allows you to quickly understand your application landscape. It presents the applications into
4 quadrants, driven by the Planned Disposition (Invest, Sustain, Migrate, Retire).

The placement of applications within these quadrants is user-defined, based on a selectable
set of primarily qualitative measures such as Business Value, Technical Fit, and Technical
Risk Score. Application Total Cost of Ownership (TCO) can be selected as the sizing metric,
determining the relative size of each application bubble.

![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snr2.jpg)
