---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Cost data configuration"
breadcrumb:
  - "Benchmarking"
  - "Configuration Guide"
source_path: "it-benchmarking/configuration/cost-data-configuration.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Cost data configuration

## Connecting to Costing

Cost data tells Interactive Benchmarking what it should compare. You can feed it directly from
Costing or by manual input.   
In Benchmarking’s Configuration settings:

1. Integrate with the Costing platform by selecting “Cost Transparency”.
2. Validate the connection.
3. Select the primary Costing project that holds your IT actual spend.
4. Select the fiscal period from the fiscal year that should be used for your baseline benchmarks.
5. Retrieve the data.

![Connect to Costing](../../resources/images/it%20benchmarking_images/connect-to-costing.png)

Checks:

- Confirm the total IT cost aligns with Finance for that year.
- Confirm that all major Resource Towers have non-zero amounts.
- If any values are missing or you feel deserve an override, enter the values manually and save
  them before proceeding.

**Manual cost input**  
Use manual input only when:

- You have not deployed a Costing project or it is not available.
- You are doing a pilot with simplified data.
- You are loading data from an external TBM-like model.

This method is fine for starting out, but plan to integrate with IBM Apptio Costing if you want
ongoing, governed use.

**Verify currency and fiscal year settings**  
Make sure:

- The currency for IT cost and revenue is the same.
- The period you use for benchmarking is a full fiscal year, not a half-year or mixed period.
- If Costing uses multiple currencies, conversion happens before data hits Benchmarking.

In Interactive Benchmarking’s Configuration settings, set the default currency.

![Interactive Benchmarking Configuration – Default Currency](../../resources/images/it%20benchmarking_images/currency-fiscal-year.png)

## TBM Cost Pools

Cost Pool support is available up through TBM version 4 and earlier. Details for the Cost Pools
appear in the table below:

Table 1.

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

Note: The “Facilities & Power” Cost Pool is specific to data center facilities.
It excludes office and other facility expenses. Typically, office facilities should be assigned to
the “Internal Labor” Cost Pool.
