---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "transfer-pricing-report.html"
title: "Transfer pricing report"
breadcrumb: []
source_path: "transfer-pricing-report.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Transfer pricing report

◆ Applies to: Billing Standard on TBM Studio 12.6 and later

For detailed information about transfer pricing, see [Configure transfer pricing](configure-transfer-price.html).

The Transfer Pricing component adds two new objects to the model:

- The
  Inter Company Transfer Pricing
  object gives you a location to model your debits and credits, or provides the ability to apply a ratio by which to adjust the price of a service. The object includes all of the data in the All Business Services Master Data and adds the following columns:
  - Providing Legal Entity
  - Provider Location
  - Consuming Legal Entity
  - Consumer Location
  - Transfer Rate
  - Adjusted Transfer Rate
- The
  Legal Entities and Cross Charging
  object is a duplicate of the Business Unit object and the master data set, above the Business Unit object for charges and business units in the Business Services and Business Units data sets. This object allows you to redistribute service charges to lower levels of the business unit hierarchy once the initial charge is incurred.
    
  An example of a legal entity might be business unit, functional unit, or cost center.

![](../resources/images/boit_images/boit_transfer-pricing-report_model.jpg)

Charges can be allocated either directly into the BU Allocation object or they can route through the Transfer Pricing object before getting charged. If there are services that are not able to be transfer priced, you can use a combination of these two paths.

The general flow for transfer pricing is:

1. An IT service provider sets a transfer pricing strategy.
2. That charge gets allocated into the Transfer Pricing object, where it gets adjusted at either a flat rate or ratio, depending on the strategy.
3. The cost is charged back to the business unit.
4. Once the first charge happens, the company can then use the Legal Entity and Cross-Charging object to localize that charge back to different departments within the same business unit.

NOTE
: A filter on the allocation from Business Services to Inter Company Transfer Pricing is based on Transfer Rate (if Transfer Rate = 0, values will flow up to BU Allocation, if Transfer Rate does not = 0, values will flow through Inter Company Transfer Pricing).

Examples

Use case 1
- Big Bank has six legal entities, or business units:

- Investment Banking UK LLC
- Investment Banking France LLC
- Investment Banking Germany
- Commercial Banking UK
- Commercial Banking France
- Commercial Banking Luxembourg

While these six business units function separately in Big Bank organization, a single Big Bank
IT organization supports all six. In this situation, IT acts as an internal service provider (or
external vendor) to deliver technology services to each of business unit and charge for the services
they provide.

Use case 2- Other organizations might divide into "centers of
excellence," or regional IT hubs that provide a focused service to the other centers in the
organization. Assume an organization has the following IT centers:

- Network management – UK
- Mid-range compute – Ireland
- Communication and collaboration – France

Each center charges the other centers for their specific services. A transfer price is applied
to each charge, and is often unique for each center-to-center charge. In this case, the transfer
rate has a "from–to" value that is different for each country and service so the organization can
accurately charge and allocate costs across the different business units, essentially allowing each
cost center to cross-charge another. In addition, some charges might need to be re-distributed to
lower levels of the business unit hierarchy.

Display the Transfer Pricing report

1. On theApplicationmenu, clickBilling Standard
   (see[Billing Standard menu](getting_started/boit-menu.html)).
2. On the
   Report collection
   menu, click
   IT Service Provider
   .
3. On the bar at the top of the page, click
   Inter Company Transfer and Cross-Charging
   .

The report contains the following elements:  
![](../resources/images/boit_images/boit_transfer-pricing-report_kpis.jpg)

(1) Report collection- The report collection contains the following
reports:

- IT Service Provider Summary
- Recovery Analysis
- Unit Rate Analysis
- Applications Recovery
- Cloud Recovery
- Projects Recovery
- Inter Company Transfer Pricing and Cross-Charging (described within this document)

(2) KPIs- KPIs provide a high-level view of your development spend
and other metrics.

- Charge
  - The core charge for a given service.
- Provider Modified Charge
  - The charge amount after the transfer pricing strategy is applied.
- Potential Savings
  - The cost of service with the pricing strategy that introduces the greatest cost avoidance.
- YTD Provider Modified Charge
  - The adjusted charge amount YTD.

(3) Charges and Modified Charges by Provider- This section helps you
understand the transfer rate for a given provider-consumer combination, as well as the resulting
charge being billed out, and the billable unit count. Questions answered:

- What are my transfer rates and resulting charges?
- What percentage of services are cross-charged?
- How are the cross-charged services trending over time?
- What is the distribution of charges per destination?

(4) Charge Details- This table provides a view into the relationship
of each transaction between the providing legal entity versus the consuming legal entity, and the
financial impact of each transaction. This information helps you understand and anticipate the
overall profit, loss, and tax burden of your transfer pricing strategy. Questions answered:

- What is the impact of our transfer pricing strategy?
- What is the impact of cross-charging between legal entities?
- What is the source and destination of my charges, per business unit?

**Parent topic:** [Billing Standard](home.html)
