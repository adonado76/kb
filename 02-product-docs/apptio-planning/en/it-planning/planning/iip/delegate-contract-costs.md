---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Delegate Contract Costs"
breadcrumb:
  - "Planning"
  - "Project Planning"
source_path: "it-planning/planning/iip/delegate-contract-costs.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Delegate Contract Costs

Important: Available with the ***Apptio Planning Standard****subscription*

The **Delegate Contract Costs** feature allows users to allocate contract expenses to a
different cost center starting on a specified date. *This capability is only available
when the Integrated Investment Planning (IIP) feature is enabled.*

This functionality is valuable in project planning scenarios where a contract spans
multiple phases—for example, **Build** vs. **Run**. A project cost center may own the
**Build**portion of a contract but want to delegate the **Run/Maintenance** costs to
an operational cost center (e.g., *Data Center Ops*). Delegation ensures expenses are
accurately attributed for budgeting, forecasting, and financial reporting.

## Steps to Delegate Contract Costs

**1. Create the Initial Contract Expense**

1. Navigate to **Plan** → **Expenses** → **Contracts**.
2. Create a contract expense.
3. In the **Summary** tab, the entire contract amount is initially assigned to the
   original cost center.

**2. Delegate the Contract Cost to Another Cost Center**

To shift the *run*portion of the contract:

1. Return to the **Contracts** tab. Set:
2. **Delegation Cost Center:**The cost center that will assume ownership of the
   contract expense starting on the Delegation Start Date.
3. **Delegation Start Date:**The date on which the contract expense should begin
   reallocating to the Delegation Cost Center. All amortized contract costs from this date
   forward will be assigned to the delegated cost center, while all earlier costs remain
   assigned to the original cost center.
4. The **Summary** tab will show separate lines for each cost center.
