---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Overview of Costing Standard reports (v104+)"
breadcrumb: []
source_path: "cost-transparency/reports-v104/ctreportcollections104-plus.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Overview of Costing Standard reports (v104+)

- Applies to: Costing Standard on TBM Studio 12.3 and later, with Template v104 and later

To access the Costing Standard reports:

1. Log in to Apptio.
2. In the navigation bar, click **Cost Transparency**.
3. In the **Home** page, click one of the following report collections.

The following reports are available:

[IT Financials report collection](it-financials-report-collection.html)

## IT Financials

This collection provides OpEx and CapEx spend and variance reporting broken out by IT cost
centers, cost center owners and accounts. Budget owners and decision-makers can use these reports to
understand how spend is tracking to plan and where there are variances, then drill into detail to
see the underlying financial transactions.

- [Financial Review report](financialreview104.html). A summary overview of your
  OpEx and CapEx spend and variance for the current month, quarter, year-to-date, and projected
  forecast for the fiscal year, with ability to drill into underlying details.
- [Financial Review (OpEx) report
  (v107)](../reports-v107/itfmf-ct_financialreview107.html). A summary overview of OpEx spend and variance per cost pool and cost pool owner.
- [Financial Review - CapEx
  report (v107)](../reports-v107/itfmf-ct_financialreviewcapexv107.html). A summary overview of CapEx spend and variance per cost pool and cost pool
  owner.
- [Financial Analysis report](deprecate_financialanalysis104.html). An analyst's
  view (detailed table) of OpEx and CapEx spend, variance, and period-over-period changes.
- [Cost Pool Analysis report](deprecate_costpoolanalysis104.html). OpEx/CapEx and
  fixed/variable expenditures broken out by standard cost pools and cost subpools. You can drill into
  the accounts and transactions rolled into each category.
- [Financial Variance Review email
  report](deprecate_financialvariancereviewemail104.html). A budget variance review report with top outliers and annotated explanations that can
  be emailed.

## Labor

This collection brings HR and GL actuals together in single view, providing a baseline of an
effective labor rate across similar functions, and aggregating labor types by cost center, role, and
location to compare against plan:

- [Labor Review](itfmf-ct_itplaborreview104.html)
- [Labor Analysis](itfmf-ct_laboranalysis104.html)
- [ITP-Labor Review](itfmf-ct_itplaborreview104.html)

## IT Towers

This collection provides cost-per-unit so you can see total cost and efficiency trends according
to the standard ATUM taxonomy, aligned with peer benchmarks. Intuitive analytics start with a
summarized view that allow you to drill down to details when desired. The automated model shows how
GL budget variance impacts towers and functions:

- IT Towers
- Labor Review
- Labor Analysis
- ITP-Labor Review

## Vendors

This collection provides vendor costs aligned to IT towers, projects, and labor, aggregating
vendor cost by vendor type and function:

- Vendor Review
- Vendor Portfolio
- Vendor List

## Infrastructure & Cloud

This collection features automated data feeds from public cloud service providers, aggregating
and translating billing detail into standard IT categories. You can view public cloud TCO with fully
burdened cost in the same report as public cloud (IaaS/SaaS) and on-premise assets.

Also, infrastructure assets are grouped by categories using a standard taxonomy. OpEx and CapEx
are derived from the financial ledger and allocated to infrastructure assets for a fully burdened
view of costs. All infrastructure spending is combined with storage tier metrics with cost, so you
can see an analysis in a single view:

- Summary
- Server TCO
- Storage TCO
- Server Comparison

## Applications

This collection provides the total cost to own (TCO) for applications, calculated consistently
based on actual costs allocated through a best-practice standard cost model. The reports can start
with basic cost allocation strategies that can be refined with additional infrastructure data over
time. Application Portfolio reports provide summary views by application family, application type,
and other categories. The detailed application reports provide actionable insights into all
application costs, broken down by run and development costs, including the underlying infrastructure
and Cloud costs.

- [Application Review report](applicationreview.html). An executive overview of the
  application spend for your top applications, application families, and the underlying infrastructure
  costs. A simplified snapshot of any application is available with a quick click in any bar
  chart.
- [Application Portfolio report](applicationportfolio.html). A look across your entire
  application suite so you can gain insights related to who's consuming application spend, the cost
  drivers, the cost composition of vendors, and projects related to your applications.
- [Application List report](applicationlist.html). An analytical report that provides
  quick access to the complete details about any of the applications in the organization.
- [Infrastructure Analysis by Application report](infraanalysisbyapp.html). A detailed
  analysis of the percentage of application use per IT tower (Compute, Storage, and Service
  Desk).
- [New & Retired Apps report](newandretiredapps.html). A report of your application
  count, usage, and change YTD.

## Services

This collection allows you to quantify the full costs of individual services and the entire
Service Portfolio, showing costs in the context of services and business criticality that the
business understands and can assign value to. The data is modeled on a standard services hierarchy
to create a defensible TCO and accelerate defining services based on their cost makeup. Granular
analytics provide actionable insights to Service owners:

- Services Review
- Services Portfolio
- Service List

## Projects

This collection provides a single view of project OpEx and CapEx, broken down by labor, vendors,
and expense area for each. You can view project investment and spend alongside status, priority, and
budget. Project investment is linked to the applications and business units they support:

- Projects Review
- Projects Portfolio
- Projects List
- Projects at Risk

## Business Units

This collection shows the total cost of applications and services by business unit, with assigned
values. This can give business units visibility into consumption driven costs and discretionary
investment, making allocations more defensible by distinguishing between direct (consumption) vs.
indirect, and making costs understandable and actionable. You can use these reports to drill down
into interconnected detail about applications, services, assets, and projects. Baselines let you see
costs across business unit by comparing cost per FTE and department, providing the flexibility to
match allocation methods to the data available for each application or service:

- Business Unit Review
- Business Unit Portfolio
- Business Unit List

## Benchmarking

This collection provides benchmark data on-demand, including monthly comparisons of annualized IT
costs with benchmarks. Benchmark data uses the same standard taxonomy (ATUM) and methodology as cost
analytics. The benchmark metrics are provided by trusted industry sources and Apptio's own customer
data. Benchmark data is refreshed every six months:

- Industry & OpEx Benchmarks
- Infrastructure Summary
- Compute

**Data Dimensions**

- Dashboard
- Cost Source
- Labor
- Vendors
- Projects

## Data Quality (admins only)

This collection allows TBMAs and system administrators to identify and measure gaps within and
between data sets, and to prioritize their action per impact on cost allocations:

- Summary
- Data set Mappings
- Data Dimensions
- Financials

**See also**:

- [Compare v104 and v103 Costing Standard reports](comparev103v104reports.html)
- [Mapping Costing Standard reports from Template v103 to
  v104](mappingctreports103to104.html)
- [Specify component version in TBM
  Studio](https://community.ibm.com/community/user/viewdocument/upgrade-cost-transparency-from-temp-1?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Opens in a new tab or window)")
