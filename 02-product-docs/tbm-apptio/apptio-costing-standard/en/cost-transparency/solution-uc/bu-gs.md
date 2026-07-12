---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Business Unit Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Solution Use Cases"
  - "Business Unit"
source_path: "cost-transparency/solution-uc/bu-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Business Unit Getting Started

The Business Units component enables organizations to understand how technology costs
are consumed across business units by consolidating service and application costs into a single,
business-aligned view. It provides end-to-end visibility into the total cost of applications and
services consumed by each business unit, supporting transparency, accountability, and informed
decision-making.

## Component Install

**CT– Business Units**

The CT- Business Units component installs the allocation structures required to roll up
application and service costs to business units. It introduces direct and indirect
allocation mechanisms that ensure a complete and defensible view of business unit
consumption.

Use this component when you want to analyze total technology spend by business unit,
understand cost drivers, and support showback or chargeback initiatives.

## **Prerequisites**

You must install the following components before installing the Business Unit Allocations
component:

- CTF- Cost Source
- CTF- IT Resource Towers
- CT Apps- Applications
- CT Apps- Services

**Common Sources of Data**

Business unit data typically comes from organizational hierarchy systems, HR systems,
service management platforms, and business planning applications. The data you use will
determine the level of detail available and the allocation methods you can support.

Common data sources include:

- **HR Systems:** Employee and contractor headcount data for indirect allocations
  (Workday, SAP SuccessFactors, Oracle HCM).
- **Service Management Platforms:** Service consumption data and business unit mappings
  (ServiceNow, BMC Remedy).
- **Business Planning Systems:** Business unit structure, programs, and projects
  (Anaplan, Adaptive Insights).
- **Application Portfolio Management:** Application-to-business unit relationships and
  consumption metrics.
- **Organizational Hierarchy:** Business unit structure, ownership, and reporting
  relationships from enterprise organizational charts.

**Master Datasets**

You may need to upload multiple tables and map them to the master data tables provided with
the component. The two primary master data tables are:

- **Business Unit Allocation Master Data**
  - This table defines the business units in your organization and contains attributes
    used for indirect cost allocation. It includes organizational hierarchy information,
    headcount data for allocation ratios, and business unit ownership details.
  - **Service Allocations Direct Master Data**
  - This table defines the direct consumption relationship between business services and
    business units. It contains the consumption quantities that drive direct cost
    allocation, along with service and business unit identifiers for mapping.

**Allocation Flow**

After you map the data, costs should flow through the model as follows:

- **Business Services → Service Allocations Direct**
- **Business Services → Service Allocations Indirect**
- **Service Allocations Direct → Business Unit Allocation:** Direct costs allocated to
  business units based on consumption quantities
- **Service Allocations Indirect → Business Unit Allocation:** Indirect costs allocated
  to business units based on headcount ratios
- **Projects → Business Unit Allocation:** Project costs allocated directly to
  associated business units

**Direct vs. Indirect Allocations**

In Apptio, costs are allocated as either **direct** or **indirect** to ensure
accurate and defensible cost attribution. **Direct allocations** are consumption-based
and assign costs such as labor, software, or equipment directly to a specific product,
service, department, or project. These costs can be clearly traced to a cost object and
typically represent the largest share of controllable spend. **Indirect allocations**
represent shared or overhead costs required to run the organization, such as facilities,
utilities, end-user equipment, and general infrastructure, and are distributed using defined
allocation ratios like total staff or departmental headcount.

Within the Apptio cost model, direct and indirect allocations are calculated at the top of
the model using four core objects: **Business Services**, **Service Allocations
Direct**, **Service Allocations Indirect**, and **Business Units Allocation**.
Business Service costs flow to **Service Allocations Direct** based on explicit
service-level mappings, while shared costs flow to **Service Allocations Indirect** based
on configured allocation logic. This structure ensures clear separation of direct
consumption-driven costs from indirect shared costs, enabling transparency, consistency, and
accurate downstream reporting across services, applications, and business units.
