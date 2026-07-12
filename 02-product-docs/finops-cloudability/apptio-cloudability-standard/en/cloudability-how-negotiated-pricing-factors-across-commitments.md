---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "How Negotiated Pricing Factors Across Commitments"
breadcrumb:
  - "Optimize"
  - "Understanding Commitment Management Basics in Cloudability"
  - "How Negotiated Pricing Factors Across Commitments"
source_path: "SSVCLNQ/product/custom_pricing_factors_across_commitments.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# How Negotiated Pricing Factors Across Commitments

## Purpose

Explain how negotiated pricing interacts with commitment programs and KPIs so teams read results consistently across pages and providers.

Negotiated pricing may also be referred to as custom pricing for commitments we will use them interchangeably

## Pricing Basics

Negotiated Pricing Changes the Baseline - Committable spend, provided in terms of on-demand equivalent (ODE) reflects list or adjusted rates depending on your selected cost basis. That choice flows into each of the 5 key performance indicators.

Negotiated Pricing Changes the Commitment Discount Rate - In addition to negotiating on-demand rates, CSPs allow for the negotiation of commitment discounts, often varying across commitment type, region, instance, term, etc.

Stacking Matters - Negotiated pricing may stack with commitments (additive) or supersede certain line items (non stacking). Always confirm how your contract interacts with the commitment program for the affected services. As Cloudability Commitments pulls this pricing from your public APIs, we are able to formally determine the real result/expectation for a given commitment or recommendation.

## Cost Basis — List vs. Adjusted

Cost basis determines what prices are used for ODE and cost calculations.

List - Uses public/list rates for both on-demand and commitment pricing.

Adjusted - Uses your negotiated/custom rates for both on-demand and commitment pricing. One caveat as mentioned in the introduction to savings rate section, ESR uses a mix of negotiated commitment pricing and list on-demand rates when the adjusted basis is selected. As such, this ensures that negotiated pricing is included when assessing Rate Optimization at the highest level.

Implication - With adjusted cost basis, often on-demand, commitment discount, and thus ODE are all lower than when list. As a result, magnitude of Net Savings and Commitment Cost are likely to be lower since the discount on a commitment is less, the cost applicable to the commitment is less, or a combination of both.

## Stacking Rules

Negotiated pricing contracts differ wildly across customer size and CSP. The largest cloud service users naturally have leverage in negotiating discounts relative smaller customers. At a high level, there are no hard and fast rules. Treat the following as patterns to verify against your agreements.

Additive Stacking - Negotiated discounts reduce the on-demand rate; commitment discounts apply on top, resulting in lower effective rates.

Superseding Terms - Negotiated pricing may establish a floor that replaces list discounts for certain SKUs/services.

Program Priority - Some programs apply credits after commitments, others reduce the base used to calculate commitment value.

While Cloudability can systematically help expose negotiated pricing implications, it is prudent for FinOps practitioners to understand the negotiated terms inside and out. Confirm stacking order for your services. Misunderstanding stacking can lead to double counting expected savings.

## Practical Guidance

- Isolate list based KPIs from negotiated based KPIs. Mixing them could give the wrong interpretation of performance.
- Pay attention to your cost basis across commitment pages. Ensure adjusted is set as default. Document your basis on shared dashboards and exports outside of the application.
- Validate stacking per service family before proceeding with purchases.
- Explore the list cost basis to better understand the impact of your negotiated terms. Leverage this knowledge in future negotiated pricing conversations.
