---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Net Savings Modal"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Guide to Advanced Commitment Functionality"
source_path: "product/net_savings_modal.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Net Savings Modal

## Purpose

Net Savings is the most important KPI. It is ultimately what is used to clearly communicate out
performance and justify past and future commitment purchases, as such, we want to bring transparency
and added detail to how this KPI is calculated. This modal attempts to satisfy this desire.

## How to Access

Soon, you can access the coverage modal via the details button on the Net Savings KPI on the
portfolio page. We have future plans to provide access to this modal on the recommendations and
manger pages. The modal inherits the current header selection and filters on the page such that the
modal data is always in context to what you were previously viewing.

## Layout of the Net Savings Modal

**Net Savings Calculation**— Explicitly displays [gross] savings and waste (unused commitment)
for a given reporting range. Savings - Waste = Net Savings.

**Aggregate Net Savings Histogram** — Time series daily chart with green bars (when savings is
greater than waste) and red bars (when waste is greater than savings). This UI mirrors the Net
Savings chart displayed in the Details Panel for a given commitment. Here, it is simply aggregated
across whatever commitments are shown on the table.

**Forecasted Net Savings by Year**— As a nice to have, we show the expected net savings by
year assuming a similar utilization percentage as the current selection. Note that this value is
directionally correct given that it makes some assumptions and ignores future purchases. It does
include an understanding of future expiration's.

## Net Savings Modal Terminology

**Savings -** The difference between the covered ODE and the commitment cost for the selected
period. Savings is implied as 'gross'.

**Waste** - Value of unused commitments over the period.

**Net Savings** - The KPI. Savings - Waste.

## Interpreting Net Savings vs. Waste

Use the top cards to anchor on what happened (Actuals) and what we expect (Forecast). Then use
the bars to understand why:

**All Green** - No days exist where the waste from your portfolio selection was greater than
the savings it generated.

**Consistent green, minimal red** - Healthy utilization of purchased commitments.

**Green with periodic red** - Seasonal or scheduling gaps. Ensure you understand your
workloads before making additional purchases. Understand whether the more flexible spend commitments
could be more advantageous that resource commitments that have limited applicable scope.

**Frequent red spikes** - Systematic overbuying; evaluate exchanges/convertibles or reduce
future purchase size/term.

## Key Takeaways

Net Savings = Savings − Waste is the primary performance indicator for commitments.

Know that you can track expected savings by year via this modal.

**Parent topic:** [Guide to Advanced Commitment Functionality](../product/guide_to_advanced_commitment_functionality.html)
