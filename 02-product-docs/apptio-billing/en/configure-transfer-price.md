---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "configure-transfer-price.html"
title: "Configure transfer pricing"
breadcrumb: []
source_path: "configure-transfer-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configure transfer pricing

◆ Applies to: Billing Standard on TBM Studio 12.7 and later

Transfer pricing refers to the rules and methods for pricing transactions within and between
legal entities that are under common ownership or control. Many multinational organizations,
especially in the banking and financial services industries, split their business into separate
legal entities (for example, separating investment banking from commercial banking operations) among
countries where they operate.

When services are consumed across legal entities, a transfer price or markup is often applied to
those services. Financial analysts for global companies need to accurately charge and allocate those
service costs and prices across legal entities, and adjust invoices to meet regulatory and
compliance reporting requirements.

SEE ALSO : [Inter
Company Transfer and Cross Charging (Transfer Pricing) report - Billing Standard](transfer-pricing-report.html "(Opens in a new tab or window)")

Prerequisites

- Install and configure the following Billing Standard components:
  - Billing Standard Foundation
  - Billing Standard Price
- Collect the following data:
  - Names and relationships between geographic legal entities, the services they provide, and the
    transfer pricing mechanism used in each case
  - Taxation rules that apply to transfer pricing markup between specific geographic locations
  - A table of rules followed by cross-charging business units that reside within the same legal
    entity as a consuming legal entity (see the following table for more information)

Transfer pricing data sets and models

The following data sets are used within the configuration:

- Inter Company Transfer Pricing Master Data - This data set uses customer data that
  defines transfer pricing markup rates between specific legal entities.
- Inter Company Transfer Pricing - This is the modeled version of the Inter Company
  Transfer Pricing Master Data.
- Legal Entity Taxation Master Data - This data set uses customer data
  that defines transfer pricing markup taxation rates between specific legal entities.

The following models are created with the transfer pricing use case. Red arrows indicate where
the drivers originate.

Configure transfer pricing

1. Upload the following data sets:   

   | Data set | Use Case | Description | Key Columns |
   | --- | --- | --- | --- |
   | Transfer Pricing Rates | Transfer pricing, transfer pricing with taxation | Defines transfer pricing markup rates between legal entities, and in some cases, service-by-service | Providing Legal Entity, Providing Location, Service (optional), Consuming Legal Entity, Consuming Location, Markup Rate (for example, enter 0.15 for a 15% markup) |
   | Transfer Pricing Taxation Rates | Transfer pricing with taxation | Defines transfer pricing markup taxation rates between legal entities, and in some cases, service-by-service | Providing Legal Entity, Providing Location, Service (optional), Consuming Legal Entity, Consuming Location, Markup Taxation Rate (for example, enter 0.15 for a 15% tax rate) |
2. Append the data sets to the corresponding master data sets.
3. Verify the modeled metrics are flowing correctly from Inter Company Transfer Pricing, through
   Business Units, to Legal Entities and Cross Charging.

**Parent topic:** [Billing Standard](home.html)
