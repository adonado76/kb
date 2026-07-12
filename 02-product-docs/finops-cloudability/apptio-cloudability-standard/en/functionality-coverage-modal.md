---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Coverage Modal"
breadcrumb:
  - "Optimize"
  - "Guide to Advanced Commitment Functionality"
  - "Coverage Modal"
source_path: "SSVCLNQ/product/coverage_modal.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Coverage Modal

## Purpose

As previously discussed, coverage is an important KPI. It gives insight into both performance, what you currently have rate optimized through commitments, and risk, what percent of your total committable spend is currently covered. The coverage modal exposes how this KPI is calculated to give our users confidence and to unlock insights around performance and opportunity.

## How to Access

Currently, you can access the coverage modal via the details button on the coverage KPI on the portfolio page. We have future plans to provide access to this modal on the recommendations and manger pages. The modal inherits the current header selection and filters on the page such that the modal data is always in context to what you were previously viewing.

## Layout of the Coverage Modal

Coverage Calculation: The modal will first show what two values in the chart below were used to calculate the coverage metric.

Coverage Metric Breakdown : The modal then breaks down each of the covered and uncovered costs. Taking inspiration from a financial statement, the values direct proceeding a line is a sum of the previous values.

Vendor Coverage Summary : To provide a sense of materiality when assessing different service coverage metrics, we provide the covered, uncovered, and ineligible ODE values for the selected vendor. Note that this section does not change with the current header selection and filters on the underlying page.

Important : All amounts in the Coverage Modal are expressed in terms of on-demand equivalent (ODE) costs. For 'uncovered' values, this means that they are in terms of on-demand, and thus the on-demand value = ODE. For 'covered' values, this means that the value shown is not cost, it is ODE. This allows for an apples-to-apples comparison across covered and uncovered costs.

## Coverage Modal Terminology

All vales are in terms of ODE. First, a reminder of two important terms:

Resource–based Commitments: Abbreviated to resource commitments. Provides a discount in exchange for a commitment to a certain amount of usage on a product or service (Reserved Instance, CUD).

Spend-based Commitments: Abbreviated to spend commitments. Provides a discount in exchange for a commitment to a certain amount of spend on a product or service (Savings Plan, Flexible CUD).

Coverage Metric Breakdown - Covered

- Resource Covered : The covered amount fulfilled by resource based commitments.
- Spend Covered : The covered amount fulfilled by spend based commitments.
- Spend Covered, Resource Eligible : Portion covered by spend commitments that could have been covered by resource commitments given the same eligibility rules.
- Resource Covered, Spend Eligible : Portion covered by resource commitments that could have been covered by spend commitments given the same eligibility rules.
- Total Covered Amount : The ODE of the total amount covered.

Coverage Metric Breakdown - Uncovered

- Spend Exclusive Uncovered : On-demand usage that only a spend commitment could have covered.
- Resource Exclusive Uncovered : On-demand usage that only a resource commitment could have covered.
- Nonexclusive Uncovered : On-demand usage that either a resource or spend commitment could have covered.
- Total Uncovered Amount : The total amount that could have—but was not—covered.

Coverage Metric Breakdown - Total amount

- Total Amount : The Total Covered Amount + the Total Uncovered Amount. Another interpretation is this value is the ODE of what could have or was covered by commitments.

Vendor Coverage Summary

- Covered Amount : The amount commitments covered. Note that this value ignores commitment cost that was left unutilized.
- Uncovered Amount : The amount that commitments did not cover. Because it was billed on-demand, this can be viewed as both ODE and actual cost.
- Commitment Ineligible : Costs that cannot be covered by commitments due to service or usage type rules.
- Total Service Amount : The total ODE (cost if no commitments were purchased for the given vendor) of the services supported by Cloudability Commitments. (See Commitment Types Summary)
- Sustained Use Discount Credits (SUDs) : A GCP specific monthly discount for sustained GCE usage when not receiving other discounts. Minor but included here for awareness.

## Covered vs. Uncovered Usage: How to Interpret

Coverage helps you answer two questions:

1. How much of my eligible demand was optimized through discounted rates? (covered)
1. Where could commitments have applied but didn’t? (uncovered)

Potential Interpretations of data

- A high Spend Covered share with large Resource Eligible overlap may indicate room to convert some demand into more resource commitments that often carry a higher commitment discount rate (CDR).
- High Nonexclusive Uncovered suggests broad opportunity—either resource or spend commitments could close the gap. Use Recommendations to determine what category mix is right for your risk tolerance.
- High Resource Exclusive Uncovered often points to specific instance families/regions lacking resource commitments. Spend commitments wouldn't apply here so a resource specific commitment strategy must be created to optimize this spend.
- High Spend Exclusive Uncovered can indicate infrequent, mixed, or cross service usage patterns better suited to spend commitments. Take solace in knowing this spend can not be further optimized with a resource commitment.

Reminder: If your organization uses custom pricing, the ODE baseline will reflect those rates; savings rates derived from ODE will differ from retail baselines.

## Reporting Link Integration

Debuting with GCP, we have introduced deep linking into the values shown on the coverage modal. These links open a new tab and build a report using Cloudability native reporting. This feature further extends the purpose of modal in the first place by:

- Exposing the underlying costs such that there is full transparency to how the coverage KPI was calculated.
- Exposing the underlying covered costs for chargeback/show back use cases.
- Exposing the underlying covered costs to develop an understanding of what was covered for the purpose of determine whether a commitment renewal is appropriate.
- Exposing the underlying uncovered costs to develop an understanding of whether or not this cost is stable enough that it would result in savings if covered by a commitment. In conjunction with the recommendations functionality, users can develop confidence that future purposes will result in a positive outcome for a risk worth taking.

## Key Takeaways

- Coverage is presented in ODE to standardize interpretation across providers.
- The modal separates what was covered from what could have been covered, and classifies the uncovered portion by eligibility (resource only, spend only, either).
- Use the reporting links to move from signal to root cause, then trial strategies in Commitment Recommendations.
