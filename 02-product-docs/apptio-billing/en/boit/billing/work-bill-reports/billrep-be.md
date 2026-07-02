---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Billing reports in Billing Essentials"
breadcrumb:
  - "Billing"
  - "Working with Billing Reports"
source_path: "boit/billing/work-bill-reports/billrep-be.html"
images:
  - "resources/images/boit_images/billcostmodel.png"
  - "resources/images/boit_images/billdetail.png"
  - "resources/images/boit_images/billinv.png"
  - "resources/images/boit_images/billjournal.png"
  - "resources/images/boit_images/billprocessasmin1.png"
  - "resources/images/boit_images/ratemgmt.png"
  - "resources/images/boit_images/solnlib.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Billing reports in Billing Essentials

Billing Essentials includes a small, focused set of reports installed via the “Bill-
Charge Reporting” component:

Note: Applies to Billing Essentials only.

## Bill Detail report

- Purpose: Inspect charges, units, and rates by solution offering and receiving
  organization, across time (current month, QTD, YTD, annual), and compare actuals vs plan
  to explain variances.
- Questions answered:
  - What is my total charge for the selected period, and how does it compare to
    plan?
  - What are my YTD charges and forecasted annual charges (and are we trending over or
    under plan)?
  - Which solutions/offerings are driving the most charge for this organization?
  - Which solutions have the highest billable rate?
  - For a given offering, what were the billable units, unit of measure, and rate used
    to calculate the charge?
  - Which organizations are being charged for a given offering?
  - Where do we have charge variance vs plan, and is it driven by rate or units?
  - Where do we have units variance vs plan (consumption up or down)?
  - Are there charges with zero units (or units with zero charge), indicating a data or
    pricing issue?
  - How do charges and units shift when I switch between Current Month, QTD, YTD,
    Annual, or trended views?
- Target users: Consumers, Analysts, Service or Product Owners.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billdetail.png)

Fig #: Bill Detail report in Billing Essentials

## Bill Invoice report

- Purpose: Rolls up charges for the selected org and period, highlights the biggest cost
  drivers and most expensive unit rates, shows trend, and provides the invoice line items
  (offering, units, rate, charge, and MoM deltas) so the receiving org can review and
  validate the bill quickly.
- Questions answered:
  - What is this organization’s total charge for the current period, and how does it
    compare to plan?
  - What is the organization’s YTD charge, and are we trending over or under plan
    YTD?
  - What is the forecasted annual charge, and how does it compare to the planned annual
    charge?
  - Which top solutions/offerings drive the most charge for this organization?
  - Which solutions have the highest billable rates, even if they are not the top
    spenders?
  - How have charges for key offerings trended over time?
  - For each invoice line item, what were the billable units, billable rate, and
    resulting charge?
  - Which line items had the largest month over month change in units or charges?
  - Are there anomalies like units without charges or charges without units that suggest
    data or pricing issues?
- Target users: Service or Product Owners, Analysts, Consumers.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billinv.png)

Fig #: Bill Invoice report in Billing Essentials

## Solution Library report

- Purpose: Lists each solution with the key metadata needed to bill and govern it, like
  solution type and category, offering ID and name, owner, business capability, lifecycle
  stage, unit of measure, and billable rate. In practice, it’s the “what are we selling
  internally, who owns it, and what do we charge” reference.
- Questions answered:
  - What solutions/offerings exist in our billing catalog right now?
  - Which solutions are billable vs not billable?
  - What is the billable rate for each solution, and what unit of measure does it
    use?
  - Which solutions fall under a given solution type or solution category?
  - Who is the solution owner for each offering, and what does each owner “own” end to
    end?
  - Which solutions support a specific business capability (and how much catalog
    coverage do we have by capability)?
  - What lifecycle stage are solutions in (and which ones might be candidates to retire
    or stop billing)?
  - Where do we have inconsistent pricing patterns, like similar offerings with wildly
    different rates or units?
  - Which offerings are missing critical metadata for governance, like owner,
    capability, lifecycle stage, unit of measure, or rate?
  - What are the offering IDs for solutions so I can reconcile bills, usage feeds, or
    invoice line items back to the catalog?
- Target users: Service or Product Owners, Finance, Technology leadership.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/solnlib.png)

Fig #: Solution Library report in Billing Essentials

## Rate Management report

- Purpose: Set, govern, and tune billable rates for solutions and then validate whether
  those rates are recovering cost. It combines an editable rate card (base rate plus
  adjustments that roll into the billable rate) with cost vs charge variance analysis so you
  can reduce under or over recovery and keep bills defensible.
- Questions answered:
  - What is the current billable rate for each solution, and how is it built (base rate
    vs rate adjustment)?
  - Which solutions are billable vs not billable, and who owns them?
  - Where are we under-recovering or over-recovering (variance) this month and YTD?
  - Which solutions have the largest variance drivers between cost and charge?
  - For a given offering, do cost and charge align when you look at actual volume,
    billable units, unit price, and unit variance?
  - Which units of measure are being billed for each solution (and are they consistent
    with the rate card intent)?
  - Who last updated a rate, and when (audit trail)?
  - If I change a rate, what impact does it have on expected recovery (variance trending
    down or up)?
  - Are there solutions with rates set but no volume, or volume with zero or missing
    rate behavior that needs cleanup?
  - Where do we have multiple unit of measures billed under the same offering, and does
    that create pricing inconsistency?
- Target users: Service and Product Owners, Senior Leaders, Finance, Analysts.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/ratemgmt.png)

Fig #Bill Rate Management report in Billing Essentials

## Billing Process Admin report

- Bill Invoice Archive tab
  - Purpose: Review and create an archived copy of bill details for a specific fiscal
    period which can be referenced for audit purposes or other needs.
- Bill Journal Archive tab
  - Purpose: Review and create an archived copy of journal details for a specific fiscal
    period which can be referenced for audit purposes or other needs.
- Questions answered:
  - Did we archive the invoice details for the selected month or date range yet?
  - What offerings were billed, to which organizations, and for how much charge?
  - What were the billable units and billable rates used for each organization and
    offering?
  - What were the prior-period billable units and charges (for quick period-over-period
    comparison)?
  - What is the historical invoice line-item breakdown for a given organization,
    offering, or offering ID?
  - What is the historical billing journal record for the same time period (cost and
    related dimensions)?
  - Do invoice outputs and journal outputs tie out for a period, and where do they
    differ?
  - Which organizations or offerings are driving the biggest charges in the archived
    snapshot?
  - If someone disputes a bill later, what did we actually publish at the time (the
    archived truth)?
  - After a model/rate/config change, did it impact the current view but not the
    archived snapshot (expected), and which period is affected?
- Target users: Finance, Analysts.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billprocessasmin1.png)

Fig #: Billing Process Admin report’s Bill Invoice Archive tab

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billjournal.png)

Fig #: Billing Process Admin report’s Billing Journal Archive tab

## Billing Cost Model report

- Purpose: A quick, interactive way to see where billed charges are coming from and where
  they land across the core billing dimensions. It lets you base the view on a selected metric
  (Charge, Plan Charge, and Rate Adj Impact) by Solution Offering, Organization, and
  Department so you can validate the billing model outputs, spot concentration, and find the
  “who/what drove this bill” story fast.
- Questions answered:
  - Which solution offerings are generating the highest charges this period?
  - Which organizations are receiving the largest share of charges?
  - Which departments are the biggest consumers, and how much are they being charged?
  - If I pick a specific solution offering, which orgs and departments does it hit
    most?
  - Are charges concentrated in a few offerings or widely distributed?
  - What are the top drivers behind a spike in charges, by offering vs org vs
    department?
  - Do the results look structurally correct (for example, the right departments are being
    charged for the right offerings), or is something clearly mis-mapped?
  - Which combinations of offering + org + department are the largest contributors to
    total charge?
  - If a business leader disputes their bill, what are the top items driving their charges
    without digging into line-item invoice detail?
- Target users: Service and Product Owners, Finance, Analysts.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/billcostmodel.png)

Fig #: Billing Cost Model report in Billing Essentials
