---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Commitment Key Performance Indicators"
breadcrumb:
  - "Optimize"
  - "Understanding Commitment Management Basics in Cloudability"
  - "Commitment Key Performance Indicators"
source_path: "SSVCLNQ/product/commitments_key_performance_indicators.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Commitment Key Performance Indicators

## Purpose

Establish foundational understanding of common KPIs used across Cloudability Commitments. Across the commitment manager, portfolio, and recommendations, we leverage common KPIs that quantify savings and risk after accounting for all cost and pricing adjustments.

## Savings Performance Indicators

Net Savings — Savings minus waste. Reflects the true value realized/expected by your portfolio, commitment, or recommendations. Used at both individual commitment and aggregate levels.

Example - If a set of commitments cost $10k over a specific time period which equated to $15k in on-demand equivalent spend. The gross savings of the commitments would be $15k - $10k = $5k. If 5% of these commitments when unutilized, waste would equal $10k*5% = $500. Thus, the Net Savings = $5k - $500 = $4.5k.

Savings Rate — We have several saving rates surfaced in our application. Their definitions are as follows:

Generically — Savings Rate = Savings / Spend

Effective Savings Rate (ESR ) — Committable Spend is explicitly in terms of on-demand price. Therefore, a List cost basis means that neither the negotiated rates on on-demand nor commitments are included, ESR is based solely on list pricing. For an Adjusted cost basis, the list on-demand rate is used in conjunction with the negotiated commitment rate. While a bit nuanced, this definition is aligned with the FinOps Foundation and makes sense when negotiated pricing is included as a component of Rate Optimization. We only use this term on the Optimizations Dashboard since in is crucial to isolate commitment performance from negotiated pricing at the commitment feature level.

ESR = (Commitment Savings + Custom Rate Savings) / Committable Spend.

Negotiated Savings Rate (NSR) — While not explicitly used in Cloudability, the NSR is a term that can be used to isolate your negotiated on-demand rates. The numerator is simply the savings attributed to this negotiated rate while the denominator, Committable Spend, carries the same definition as with ESR.

NSR = Custom Rate Savings / Committable Spend.

Portfolio Savings Rate (PSR) — PSR is the core metric Cloudability Commitments uses to communicate the performance of a portfolio or set of recommendations. Notably, committable spend here is fully aligned with the cost basis. A List cost basis therefore implies the savings and spend is driven off of List rates while Adjusted implies the KPI is calculated off negotiated rates.

PSR = Commitment Saving / Committable Spend.

Commitment Savings Rate (CSR) — The realized (portfolio) or expected (recommendations) savings rate of a commitment. Can be compared directly with CDR to understand the impact of utilization. Notably, this KPI appears alongside PSR on the portfolio when applicable. Another way to describe this KPI when surfaced on portfolio is the weighted average of multiple commitment's savings rates.

CSR = Commitment Saving / ODE of Commitment Cost

Commitment Discount Rate (CDR) — The saving rate given that the commitment was fully utilized. We surface this alongside CSR to demonstrate maximum savings rate achievable by a given commitment.

CDR = 𝑆𝑎𝑣𝑖𝑛𝑔𝑠 𝑅𝑎𝑡𝑒 @ 100% 𝑈𝑡𝑖𝑙𝑖𝑧𝑎𝑡𝑖𝑜𝑛.

Subsequent help documents will dive further into this terminology and explain where it is relevant to fully understand commitment performance and evaluate opportunities.

## Strategy and Risk Indicators

Utilization — The extent to which purchased commitments were actually consumed; weighted and aggregated when displayed as a KPI. This metric is realized for portfolio but expected as a result of the usage range selected in recommendations.

Coverage — The portion of eligible usage covered by commitments (vs. on‑demand), shown as a percentage and extensively supported by a coverage modal.

Example - 75% coverage means three‑quarters of eligible usage benefited from discounted pricing.

Remaining Commitment Cost — What you owe from today until all active commitments expire, independent of the reporting range.

Importantly, commitment KPIs and meta data cannot often be derived across business metrics and therefore, the commitment pages only support account and vendor-based views. We strive to continue to improve this portion of our application and encourage you to flag requests on the IBM Ideas Portal . Leverage the "Rate Optimization" category.
