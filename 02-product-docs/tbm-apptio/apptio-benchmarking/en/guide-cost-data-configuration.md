---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Cost data configuration"
breadcrumb:
  - "Configuration Guide"
  - "Cost data configuration"
source_path: "SSIU957/it-benchmarking/configuration/cost-data-configuration.html"
images:
  - "03-media/apptio-benchmarking/connect-to-costing.png"
  - "03-media/apptio-benchmarking/currency-fiscal-year.png"
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Cost data configuration

## Connecting to Costing

1. Integrate with the Costing platform by selecting “Cost Transparency”.
1. Validate the connection.
1. Select the primary Costing project that holds your IT actual spend.
1. Select the fiscal period from the fiscal year that should be used for your baseline benchmarks.
1. Retrieve the data.

![Connect to Costing](../../resources/images/it%20benchmarking_images/connect-to-costing.png)

- Confirm the total IT cost aligns with Finance for that year.
- Confirm that all major Resource Towers have non-zero amounts.
- If any values are missing or you feel deserve an override, enter the values manually and save them before proceeding.

- You have not deployed a Costing project or it is not available.
- You are doing a pilot with simplified data.
- You are loading data from an external TBM-like model.

- The currency for IT cost and revenue is the same.
- The period you use for benchmarking is a full fiscal year, not a half-year or mixed period.
- If Costing uses multiple currencies, conversion happens before data hits Benchmarking.

![Interactive Benchmarking Configuration – Default Currency](../../resources/images/it%20benchmarking_images/currency-fiscal-year.png)

## TBM Cost Pools

| Cost Pool | Description |
| --- | --- |
| External Labor | External contractor fees, travel & expenses. |
| Facilities & Power | Data center space, power, security and other operating expenses. |
| Hardware | Hardware expense. |
| Internal Labor | Employee wages, benefits, expenses & occupancy. |
| Other | Miscellaneous or non-standard expenses. |
| Outside Services | External managed service providers. |
| Software | Software expense of non-capitalized software purchases. |
| Telecom | Voice and data network connectivity expenses including circuit and usage expenditures. |
