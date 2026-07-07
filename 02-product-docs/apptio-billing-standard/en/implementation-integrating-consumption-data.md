---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Integrating consumption data"
breadcrumb:
  - "Configuring Billing Essentials (Implementation)"
  - "Integrating consumption data"
source_path: "SSV8ML/boit/billing/config-be/integrate.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Integrating consumption data

*Consumption data is what drives units in the PxQ calculation.*

Typical integration steps:

1. Identify sources Ticketing or ITSM systems (for example, number of tickets). Identity systems (active users). Monitoring or metering tools (capacity or usage). Spreadsheets where no system of record exists.
1. Define the target layout Each record should include: Period. Consumer ID or a mappable key. Offering ID or a mappable key. Units consumed. Optionally include attributes like environment, region, or cost center.
1. Build ETL or upload processes Use TBM Studio ETL, Datalink, or an equivalent integration to load data into the Billing consumption table. For small or ad hoc feeds, use Table Upload and a controlled CSV template.
1. Run initial load into In Development Load a sample period and confirm: Volumes look reasonable. Keys match offerings and consumers.
1. Promote tested consumption logic Once patterns are validated in In Development and Staging, promote to Production.
