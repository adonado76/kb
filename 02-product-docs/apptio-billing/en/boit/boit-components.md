---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Billing Standard components"
breadcrumb: []
source_path: "boit/boit-components.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Billing Standard components

The Billing Standard components are described below. Billing Standard - Foundation is the only
required component and it installs most data sets, models, and dimensions.

- **Billing Standard - Foundation**(required) - The Foundation component is
  required for Billing Standard . It provides reports based on charges, including an invoice that may
  be sent to users. All required models and tables are also installed with the Foundation component.
- **Billing Standard - Applications**(optional) - The Application component
  adds new reports focused on application reporting. The component adds two new reports:
  - The **Application Charges** report provides the Business Unit and Business
    Relationship Manager views into application charges and licenses (units) used.
  - The **Application Recovery** report provides IT a view of over/under recovery
    data by application where the charges for the application are compared to the IT cost of the
    application.
- **Billing Standard - Cloud**(optional) - The Cloud component adds new
  reports focused on cloud IaaS reporting. The component adds two new reports plus drills:
  - The **Cloud Charges** report can be used by the Business Unit and Business
    Relationship Manager to understand cloud service charges. It includes a detailed list of the Cloud
    services used by the business unit.
  - The **Cloud Recovery** report provides over/under recovery data by service.
    The charges for the service are compared to the cost of delivering the service.
- **Billing Standard - Cost Variance**(optional) - The Cost Variance
  component supports the comparison of charges to the actual cost of providing the services. The Cost
  Variance component includes many reports only viewable by staff with Service Owners or Business
  Relationship Manager roles.
- **Billing Standard - Plan Variance**(optional) - The Plan Variance
  component adds the ability to compare charges to budget, and to compare cost to a budget. The
  component enables new reports for budget and forecast variance analysis and exposes comparisons to
  budget and forecast in existing reports.
- **Billing Standard - Price**(optional) - The Price component enables
  exposing a price to end users. Prices are set in the Service Library. Any adjustments or combination
  of prices applied to a service may cause the effective price to differ from the price stated in the
  Service Library.
- **Billing Standard - Projects**(optional) - The Projects component adds new
  reports focused on Project reporting. The component adds two new reports with supporting drills:
  - The **Project Charges** report can be used by the Business Unit and Business
    Relationship Manager to see project charges and the supporting services that the business unit has
    used.
  - The **Project Recovery** report provides IT over/under recovery data by
    project, budget variance, and status.
- **Billing Standard - Servers**(optional) - The **Servers** component gives the IT Service Provider and Business Consumer insight into the
  composition of the offered and consumed services. Billing Standard - Servers can be configured to
  accommodate both an Application and Service based view of Server Costs and Consumption.
- **Billing Standard - Units**(optional) - The **Units**
  component adds units on all existing reports, and calculates an effective price by dividing charge
  by billable units. One unit type may be defined per Service Offering. When Cost Variance is also
  installed, unit rates may be compared.

**Install Billing Standard components**

Billing Standard components are not installed automatically when you create a Billing Standard
project. You must install each component separately. Only the Billing Standard - Foundation
component is required.

To install the components:

1. In TBM Studio, click the **Project** tab.
2. Click **Components**.
3. Click the **Billing Standard Foundation** component.
4. Click **Install**.
5. Repeat the above steps for each of the optional Billing Standard components you want to
   install.
