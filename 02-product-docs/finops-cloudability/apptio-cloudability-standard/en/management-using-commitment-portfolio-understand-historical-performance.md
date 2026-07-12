---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Using Commitment Portfolio to Understand Historical Performance"
breadcrumb:
  - "Optimize"
  - "Guide to Commitment Management"
  - "Using Commitment Portfolio to Understand Historical Performance"
source_path: "SSVCLNQ/product/using_commitment_portfolio_to_understand_historical_performance.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Using Commitment Portfolio to Understand Historical Performance

## Purpose

The purpose of this document is to give a broad overview of how to use the Commitment Portfolio. At a summary level, you use the Commitment Portfolio to understand how your existing commitments have performed over time, where risk exists moving forward, and to provide a starting point to begin the conversation around where opportunities remain. When fully utilized, this page blends tactical insights with strategic interpretation, allowing FinOps practitioners to quickly move from signals (KPIs) to actions (alerts, reporting, recommendations).

## How to Access and Use

The Commitment Portfolio page is located under the Optimize section in the left-hand navigation menu and is organized by vendor. Each tab shares a common structure so you can compare across clouds without switching mental models. The header toolbar lets you build a focused portfolio view

Commitment Type

This selection is organized by vendor (AWS), to service (EC2), to commitment type (EC2 Reserved Instances). Note that the intermediate service page is not required where there is a single commitment type that covers the service.

- All level (vendor-based landing page): Shows all supported services/types for the selected vendor.
- Service level : Shows all supported commitment types for the selected service.
- Type level : Showed all commitment types for the various types.

Account

The account picker controls which accounts’ usage you’re analyzing and automatically pulls in any commitments that affected that usage, even if those commitments were purchased elsewhere. For example, if Account A’s commitment covers usage in Account B, selecting Account B alone will still reflect the impact of A’s commitment on B’s usage. As a best practice, choose accounts that align with your vendor console sharing settings so analysis mirrors how commitments are actually shared. The picker represents hierarchical nature of your accounts and is multi-select.

- Selecting a payer account(s) (Management, Subscription, Billing) selects all linked accounts beneath it.
- Selecting specific linked account(s) (Member, Subscription, Project) shows a partial‑selection state on the payer account.

You can narrow by the billed account using table filters. For provider hierarchies and sharing scopes, see Account Structure by Vendor .

Cost Basis

Choosing List or Adjusted pricing allows users to understand their recommendations from list or negotiated on‑demand and commitment rates. The KPIs and tables reflect the basis you select. Note that Azure commitment pages may not expose a toggle yet. When present, values reflect Custom where applicable. For more information, see How Custom Pricing Factors Across Commitments

Analysis Period

This selection drives all KPIs and table meta data on the page. The default is last month and times are in UTC. Our suggestion is to avoid reporting on the most recent 24 hours to allow data to complete processing in our pipeline. For more information, see Data Freshness .

## Interpreting the Portfolio KPIs

- Net Savings and Remaining Commitment Cost are dollar KPIs scoped to the analysis period.
- Savings Rate, Utilization, and Coverage are rate KPIs scoped to the analysis period.
- Portfolio Savings Rate (PSR) = Commitment Net Savings ÷ Committable Spend (under the selected basis). PSR isolates the effect of commitment discounts from negotiated on‑demand pricing, making it a cleaner portfolio metric than Effective Savings Rate (ESR) when negotiated rates are in play. When Cost Basis = List, PSR equals ESR since all values are in terms of list rate and there is no savings due to negotiated rates. For more information, see Commitment Key Performance Indicators .
- Utilization is weighted by the relative impact/size of commitments in the table.
- The KPI details modals are available for Net Savings and Coverage. These modals provide additional information in support of understanding how the KPI is calculated. For more information, see Commitment Net Savings and Coverage Modals .

## Per‑Type Summary & Details Panel

- All available metadata for the commitment.
- KPIs scoped to this commitment (same definitions as the header KPIs).
- Trend visuals for daily net savings and utilization for the selected analysis period. We include a lifetime toggle to snap the chart to the entire life of the commitment regardless of the current analysis period.

Table Operations & Filters

- Sort : Click a column header to sort descending, click again for ascending, a third time to reset.
- Show/Hide Columns : Use the columns control to choose which fields to display.
- Pagination : Standard pagination controls appear below the table.
- Export : The Export button produces a CSV in what‑you‑see‑is‑what‑you‑get format for the current scope and visible columns.

Add Filter & Inline Filtering

- Use add filter (below the header tool bar) to filter by any supported field.
- Cells that are hyperlinked are available for filtering, selecting a linked cell will filter the table by that attribute and add a chip to the filter bar.

Alerts & Views

- Alerts : The top‑right alerts button opens Commitment Alerts to configure Expiration and Utilization Threshold emails.
- Views support : The Portfolio supports account and vendor scoped views. Other business mappings aren’t supported here because per‑commitment metrics can’t be computed reliably under arbitrary remaps.

GCP’s Grouped vs. Ungrouped Tables

For GCP, the Portfolio supports two complementary perspectives, driven by how GCP reports commitments (credits without per‑usage commitment IDs and multi‑dimensional resource CUDs). In exports, Reservation ID is typically not set.

- Grouped View: Aggregates commitments at the applicable scope (e.g., Billing Account/region for GCE CUDs). In this view, the app can show performance metrics per group.
- Ungrouped View: Mirrors AWS/Azure with a row per commitment. Some per‑item performance metrics are omitted when underlying data lacks per‑commitment granularity. The grouped Details Panel lists the CUDs comprising the group.

## Using this page to implement best practice

- Time horizon : Trend by month/quarter for portfolio‑level signals; use week/day to confirm seasonality.
- Basis discipline : Keep price source and recognition basis consistent across comparisons. For more information see Cloudability Commitment’s Approach to Cost and How Negotiated Pricing Factors Across Commitments
- Showback/Chargeback : Use portfolio filters plus Coverage links to break out covered vs. uncovered by team/app for accountability.
- Renewal readiness : Compare Net Savings and Utilization for items nearing expiration; decide to renew, exchange (if applicable), or simply let them expire.
- Waste control : Persistent red in Net Savings often indicates scope mis‑alignment, over‑buying, or seasonality—adjust term, scope, or category mix.

## Key Takeaways

- The portfolio is your single view of owned commitments and historical performance.
- Read aggregate KPIs first, then use details panel and modals ( Coverage / Net Savings ) to understand drivers.
- Use filters, grouped/ungrouped toggles, and vendor context to go from signal to action.
- Use Alerts and Recommendations to operationalize findings.
- Treat the portfolio as your system of record; review weekly for trend checks and monthly for renewal planning.
