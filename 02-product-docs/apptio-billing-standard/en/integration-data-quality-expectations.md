---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Data quality expectations"
breadcrumb:
  - "Data Requirements and Integration"
  - "Data quality expectations"
source_path: "SSV8ML/boit/billing/datareq-integrate/data-quality.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Data quality expectations

*Weak data will show up immediately in Billing outputs: missing lines, unexplained charges, or rates that look wrong.*

At minimum, expect to maintain the following:

- Referential integrity Every consumer in Billing should exist in the consumer master. Every offering in consumption should exist in the offering catalog. Every domain object (application, server, cloud account, project) used in Billing views should exist in its master table.
- Completeness Consumption feeds for key offerings should be complete for each billing period. Critical master data attributes (for example, consumer ID, unit of measure, effective period, currency) must not be blank.
- Consistency IDs and keys should not change arbitrarily between periods. Hierarchies for consumers and offerings should remain stable enough for trending.
- Reasonableness checks Look for: Zero or negative volumes where they should not exist. Sudden spikes or drops in units that are not explained by real events. Rates that appear off by orders of magnitude.

These checks can be implemented in either Costing or Billing reports, but they should be part of a standard monthly routine before bills are published.
