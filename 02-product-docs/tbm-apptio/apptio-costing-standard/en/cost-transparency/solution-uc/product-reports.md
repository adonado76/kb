---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Products Reports"
breadcrumb:
  - "Costing Standard"
  - "Solution Use Cases"
  - "Products"
source_path: "cost-transparency/solution-uc/product-reports.html"
images:
  - "resources/images/ct_images/launched-retired.png"
  - "resources/images/ct_images/plist-bdrill.png"
  - "resources/images/ct_images/pr-model.png"
  - "resources/images/ct_images/product-list-drill.png"
  - "resources/images/ct_images/product-portfolio-report-insights.png"
  - "resources/images/ct_images/product-review-report-insights.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Products Reports

The **Products** collection provides a comprehensive, product-centric view of
technology costs, enabling organizations to understand, govern, and optimize Product Total Cost
of Ownership (TCO) across OpEx and CapEx. This collection brings together standardized product
hierarchies, lifecycle context, and financial insights to help Product, Finance, and Leadership
teams connect spend to business outcomes and make informed portfolio decisions.

The collection supports product-level transparency by tracing costs from foundational cost
sources through to individual products, allowing users to analyze cost drivers, compare
product performance, and assess investment efficiency across the portfolio. It also enables
consistent governance by standardizing how products are defined, launched, retired, and
reported across the organization.

- **Reports available in this collection**
  - Products Review Report
  - Products Portfolio Report
  - Launched & Retired Report
  - Product List Report
  - Product Model Review Report

## Products Review

The Products Review Report provides a comprehensive summary of product-related costs,
highlighting trends, key metrics, and hierarchical cost breakdowns. The report is structured
into multiple groups and tabs to enable detailed analysis of both operating (OpEx) and
capital expenditures (CapEx) at various levels of aggregation.

This report is designed for use by the following roles:

- IT Finance
- Product Management Office (PMO)
- Executives and IT Leadership

**Insights Provided:**

- Identify top spend areas to determine where to focus your analysis
- Analyze total and unit costs to uncover inefficiencies
- View costs by business driver or product hierarchy to connect costs to business
  outcomes
- Align financial insights with business priorities

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/product-review-report-insights.png)

## Products Portfolio

The **Products Portfolio Report** provides a detailed analysis of product-related
costs, trends, and hierarchical spend allocations. The report shares the same high-level
KPIs as the **Products Review Report**, ensuring consistency in monitoring and
comparison of OpEx and CapEx performance.

This report is designed for use by the
following roles:

- IT Finance
- Product Management Office (PMO)
- Executives and IT Leadership

**Insights Provided:**

- Segment by product hierarchies to focus on a specific area
- Understand product OpEx and CapEx within the portfolio
- View portfolio cost drivers across business units, applications, towers, and
  projects for transparency

Use insights into where costs originate and how they evolve to empower portfolio
planning

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/product-portfolio-report-insights.png)

## Launched & Retired

The Launched & Retired Report provides insights into product lifecycle spend by analyzing
products based on their launch and retirement dates. The report focuses on monitoring current and
year-to-date (YTD) spending for newly launched and retiring products, as well as identifying
products approaching or past their planned retirement dates.

This report is designed for use by the following roles:

- Product Management Office (PMO)

**Insights Provided:**

- Access a consolidated snapshot of all products within your portfolio
- Centralize essential product attributes to simplify portfolio governance
- Quickly filter by Product or TBM taxonomy hierarchy to align with reporting
  structures

![Launched-Retired](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/launched-retired.png)

## Product List

The Product List report provides a centralized view of all products defined within the Product
TCO model, along with their key attributes, hierarchy placement, and financial context. This report
serves as the foundation for product-level analysis by allowing users to validate product
definitions, understand portfolio composition, and ensure consistent governance across product
hierarchies before deeper cost and performance analysis.

This report is designed for use by the following roles:

- IT Finance
- PMO and PPM Leaders
- Product Managers and Portfolio Leaders

**Insights Provided:**

- View the complete list of products across the organization with associated attributes and
  classifications
- Validate product hierarchy alignment and ensure consistent product definitions across
  portfolios
- Identify active, new, aging, and retired products to support lifecycle management
- Understand product ownership and organizational alignment for accountability and governance
- Establish a clean foundation for downstream product cost, TCO, and performance reporting
- Introduced budget metrics in Product List report

![Product List](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/plist-bdrill.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/product-list-drill.png)

## Model Review Report

Model Reports in Apptio provide complete traceability of how cost data moves through the
Apptio model covering Allocation Models, Tower/Sub-Tower structures, Cost Pools etc. They
are used to validate, troubleshoot, and analyze the data transformations applied at each
stage of the TBM taxonomy.

For the Products TCO implementation, a dedicated Model Report has been introduced to show
the end-to-end flow of cost from the Cost Source to Business Unit, based on the **Is
Product = Yes** condition defined in the All Business Services master dataset. The
report also displays the specific products to which costs are allocated and provides the
ability to view cost movement across layers and improves transparency into the origin and
allocation of product-related costs.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pr-model.png)
