---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Integrating consumption data"
breadcrumb:
  - "Billing"
  - "Configuring Billing Essentials (Implementation)"
source_path: "boit/billing/config-be/integrate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Integrating consumption data

Consumption data is what drives units in the PxQ calculation.

Typical integration steps:

1. **Identify sources**
   - Ticketing or ITSM systems (for example, number of tickets).
   - Identity systems (active users).
   - Monitoring or metering tools (capacity or usage).
   - Spreadsheets where no system of record exists.
2. **Define the target layout**
   - Each record should include:
     - Period.
     - Consumer ID or a mappable key.
     - Offering ID or a mappable key.
     - Units consumed.
     - Optionally include attributes like environment, region, or cost center.
3. **Build ETL or upload processes**
   - Use TBM Studio ETL, Datalink, or an equivalent integration to load data into the
     Billing consumption table.
   - For small or ad hoc feeds, use Table Upload and a controlled CSV template.
4. **Run initial load into In Development**
   - Load a sample period and confirm:
     - Volumes look reasonable.
     - Keys match offerings and consumers.
5. **Promote tested consumption logic**
   - Once patterns are validated in In Development and Staging, promote to Production.
