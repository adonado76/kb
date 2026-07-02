---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Optional configuration"
breadcrumb: []
source_path: "configuration/optionalconfig.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Optional configuration

The following items are optional. Configure one or more of the following functions as
needed.

- [Enter estimated non-provider costs](estmatednonprov.html "The manually entered, estimated non-provider costs are primarily for new Cloud Cost Management-only customers who have not lit up actuals with their GL in Costing Standard. For anyone who has Costing Standard, the better option is to drive non-provider costs from the actuals in the Costing Standard Cost model. There is a link between the two models (CT Cost model and CCM Cloud Invoice model) to allow you to do this via the IT Resource Towers object.")
- [Identify shared services](idsharedservices.html "A portion of your cloud costs might be attributable to public cloud infrastructure services shared across the departments that build applications on the public cloud. A good example is Enterprise Support, whose costs could be a large lump sum amount that needs to be allocated to the cloud services that are directly consumed by teams and departments in your organization. The costs of these shared infrastructure services can be allocated to those services that are directly consumed, ensuring that the costs to the application departments account for all the costs incurred from using public cloud providers.")
- [Map AWS Marketplace to ATUM](mapawstoatum.html "If you consume services from the AWS Marketplace, you must ingest and model those bills the same as your AWS service bills. AWS creates a separate AWS Marketplace billing file for each billing report you configure to be created in your billing preferences.")
- Multi-currency:
  - For new customers, update the Azure EA Detailed Bill Master Data.CurrencyCode with the currency
    code of the bill.
  - For existing customers, follow these instructions: [Configure
    Cloud Cost Management for multi-currency](multicurrency.html "You can enable multi-currency support for Apptio Cloud products.").
- [Daily/Hourly Reports - Extending or
  Changing](clouddailyhourlyreports.html "The Daily/Hourly reports are built on a data format that enables rapid and efficient storage and queries on very high-volume data sets (such as very granular cloud bills like the AWS Cost and Usage Report). As a result, extending the schema of the data sets involved and modifying reports built on those data sets requires some configuration")

**Parent topic:** [Costing Standard](../home.html)
