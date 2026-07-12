---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Using the Commitment Manager Overview to Align the Organization on Commitment Strategy"
breadcrumb:
  - "Optimize"
  - "Guide to Commitment Management"
  - "Using the Commitment Manager Overview to Align the Organization on Commitment Strategy"
source_path: "SSVCLNQ/product/using_commitment_manager_to_align_the_organization_on_commitment_strategy.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Using the Commitment Manager Overview to Align the Organization on Commitment Strategy

## Purpose

The overview page is the orientation layer for Cloudability Commitments. It brings together current posture (historical performance) and future opportunity (modeled recommendations) into one cross-service, cross‑vendor view. From this landing page, teams can begin to align on a holistic understanding of the current impact rate optimization has on their portfolio, and where immediate opportunity might lie. The tailored chart and standardized KPIs directly align users before drilling into Portfolio or Recommendations. This document will provide instructions for how to use this page.

## Access and Basic Configuration

The Commitment Manager page is located under the Optimize section in the left-hand navigation menu, below the Optimization Dashboard, and unlike the portfolio and recommendation pages.

Service Type

To start, the service type selector is a multi-select dropdown used to select which service usage you would like to analyze. When a service is selected, only the committable usage , is analyzed and displayed in the chart. This is an overview page, so further analysis of your portfolio or opportunities at the individual commitment type level must be done on the portfolio and recommendations pages. Notably, the aggregate pages at the vendor and service level ensure that the recommendations provided are mutually exclusive from each other.

For more information on this behavior, see the Recommendation Type section below.

Account

The account picker chooses which accounts’ usage our model will analyze. The picker represents hierarchical nature of your accounts and is multi-select. When selecting a payer account(s) (Management, Subscription, Billing), the button selects/unselects all linked accounts beneath it. When selecting specific linked account(s) (Member, Subscription, Project), the button similar selects/unselects the account while displaying a partial‑selection state on the payer account. It is generally best practice to choose an account selection that corresponds with your sharing preferences configured in the vendor console.

For more information about account terminology, see Account Structure by Vendor .

Cost Basis

The overview page does not allow for the option to choose your cost basis, instead if Adjusted is configured the chart will be in terms of Adjusted.

For more information, see How Negotiated Pricing Factors Across Commitments .

Analysis Period

The analysis period selection on the overview page differs from the portfolio recommendation pages in that a user selects a range in months. Importantly, users can select into the future. By default, the analysis period is one month look back and three months look forward in relation to today. If today's current month is considered part of the look forward or "forecast", because all days for the month have not yet been completed, the analysis period selection allows for both a selection of a range in months or a single month. To understand how the KPIs function with respect to the analysis period selected, see the KPI options in the subsequent section.

Recommendation Type

This section allows for the report to include or exclude the recommendation for the service selected. Optimal refers to the optimal recommendation type. For more information about the optimal recommendation type see Recommendation Type . For service spend that can be covered by multiple commitment types, assume the recommendation applied corresponds to the spend based commitment type. As an example. for AWS compute, the recommendation used on this page corresponds to compute savings plans.

## Configuring and Interpreting the KPIs

KPI Options - Type

This selection is used to configure the KPIs. Standard, the default, provides two values per KPI that demonstrate the earliest period and latest period selected. As such, standard allows you to compare the KPIs at two moments in time. Total, simply computes the KPI across the entire analysis period selected. Average, provides you the average across the analysis period selected for the KPI granularity selected.

KPI Options - Granularity

This selection defines the KPI granularity to be week or month based. In conjunction with KPI type, the user is provided the flexibility to analyze actual and forecasted performance across time.

KPI Options - Comparison

This selection will add a comparison KPI when either standard or average KPI option type is selected. Use the adjacent toggle to configure the comparison KPI to support absolute and percent change comparison methods.

More Options - Cost Granularity

Today, we only support daily granularity on the chart. Therefore, each bar on the chart, is representative of a cost in a day

More Options - Cost Type

We support true cost and on-demand equivalent (ODE). When true cost is selected, the default, all values on the chart are in terms of the cost paid or expected to be paid. When ODE is selected, all values are in terms of ODE, therefore the recommendation and existing commitment cost are transformed into ODE terms. Note, when ODE is selected as the cost type, the bar chart equals that of the ODE usage because all cost shown are in terms of on-demand.

Here are some examples on how to configure the KPI for a specific use case.

Example 1

Use Case: "Today is July 1st 2026, I would like to understand how my portfolio has improved or declined over the course of the first half of the year."

Configuration: Select All Services and a specific payer, select an analysis period of January 2026 to June 2026, select recommendation type to be off, select KPI options type to be standard, granularity month, and comparison on.

Interpretation: The KPI marked with the yellow annotation corresponds to January. The KPI in purple corresponds to June. The comparison KPI for each individual KPI will represent the percent change between January, and June. This configuration can be used for any combination of multiple months, therefore it can compare to two months/weeks in the past, two months/weeks in the future or the past with the future. In the user interface, the past is explicitly called actual, while the future is explicitly called forecast.

Example 2

Use Case: "Today is July 1st 2026, I would like to understand my net savings and coverage across the entire year in the event I make no future purchases."

Configuration: Select All Services and a specific payer, select an analysis period of January 2026 to December 2026, select recommendation type to be off, select KPI options type to be total.

Interpretation: There will now be one single value per KPI*. The KPIs will now represent values across the entire selected period.

*The remaining cost is also included in the cost KPI.

Example 3

Use Case: "Today is July 15th 2026, I would like to understand the value of the immediate commitment opportunities for the upcoming month. I would like to see this in comparison from the previous month."

Configuration: Select All Services and a specific payer, select an analysis period of June 2026 to August 2026, select recommendation type to be optimal, select KPI options type to be standard, granularity month, and comparison on.

Interpretation: The KPI marked with the yellow annotation corresponds to actual observed performance in June. The KPI in purple corresponds to the forecasted performance net of the optimal recommendation in August. The comparison KPI for each individual KPI will represent the percent change between June and August.
