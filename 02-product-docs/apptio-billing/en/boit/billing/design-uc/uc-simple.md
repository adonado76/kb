---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Simple PxQ service showback"
breadcrumb:
  - "Billing"
  - "Design Patterns and Use Cases"
source_path: "boit/billing/design-uc/uc-simple.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Simple PxQ service showback

**Problem**

You want a transparent monthly view that answers:

“Who is using which services, how much are they using, and what is the calculated
charge?”

**Inputs**

- Service / offering catalog with units and billable flags
- Consumer master
- Monthly consumption data (units by service and consumer)
- Rates by service and period

**Steps**

1. Confirm the **offering catalog** is up to date and billable flags are set
   correctly.
2. Load or refresh **consumption data** for the current period.
3. Load or confirm **rates** for each active offering for the period.
4. Run the Billing models in the appropriate environment (In Development/Staging for testing,
   Production for live).
5. Open the **invoice / summary report** for the period.
6. Filter by consumer as needed and confirm:
   - Services listed match expectations.
   - Units and rates look correct.
   - Total charges are reasonable.

**Key reports**

- Invoice / summary report
- Consumer summary report
- QA / exception report for missing mappings
