---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "IT Financials Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "IT Financials"
source_path: "cost-transparency/it-financials/itf-getting-started.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# IT Financials Getting Started

## Getting Started

Use the IT Financials components to load and manage the financial data required for
reporting on OpEx and CapEx spend. The CTF- Cost Source component provides the foundational
financial data for all OpEx reporting. The optional CTF- CapEx component enables
CapEx-specific reporting and ensures that CapEx fields are only displayed when your
organization uses CapEx data.

Install and configure these components before loading your financial data. After the
components are installed, upload your cost and budget datasets and map them to the
appropriate master data tables.

## Components Install

**CTF- Cost Source (Automatically Installed)**

The CTF- Cost Source component
is installed automatically when the Costing Standard project is created. It provides the
master data structure required for all OpEx reporting. You will use this component when
uploading cost actuals, cost budgets, and mapping fields to the Cost Source Master Data
table.

**CTF- CapEx (Additional Component)**

The CTF- CapEx component separates
CapEx reporting from OpEx reporting. Install this component if your organization loads
CapEx data or requires CapEx specific reporting.

Use this component when:

- You want to analyze capital expenditures by account, cost pool, and cost center.
- You need to review CapEx variances in budget and forecast reports.

**CTF- Cost Source NX Reports (Additional Component)**

This component provides
predefined NX reports based on Cost Source data for cost analysis across cost centers, account
groups, and time periods.

Use this component when:

- You need standard cost reports
- You want to compare actuals and budgets
- You require consistent Cost Source reporting

**To install the component:**

1. Open the Costing Standard project.
2. Select **Project** > **Components**.
3. Select **CTF – CapEx**.
4. Click **Install**.

After installation, proceed with loading data into the master data tables.

## Common Sources of Data

Cost and budget figures usually are pulled from sources such as the general ledger and
chart of accounts. This data often is provided by applications such as Oracle, SAP, Lawson,
Netsuite, and Cognos Financial Statement Reporting. The data you use will determine the
level of detail available and the columns that you will map to the Cost Source Master Data
table.

**Datasets**

You may have to upload multiple tables and map to the master tables provided with the
components. Tables are:

- General Ledger (GL): Source of truth for all financial transactions, categorized by
  account and often associated with cost centers or regional owners.
- Chart of Accounts : A complete listing of accounts used in the financial system.
  Determines the account-level granularity available for reporting. An account is a
  unique record for each type of asset, liability, equity, revenue, and expense.
- Organizational Hierarchy: Defines the structure of the organization, including cost
  center ownership and reporting relationships.
- Budget: Expected spend by cost center and account. Required for budget variance and
  forecast analysis.
