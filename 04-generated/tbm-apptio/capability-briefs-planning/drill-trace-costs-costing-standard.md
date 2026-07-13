---
concept: "Drill and Trace of Costs (model traceability)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-reports.md
last_updated: "2026-07-02"
---
# Drill and Trace of Costs — How IBM Apptio Costing Standard Addresses This TBM Capability

## The capability

Every other capability in this knowledge base — Business Unit showback, Application TCO,
Product TCO, Hybrid IT impact analysis — depends on one underlying trust question: when a number
shows up on a report, can someone actually follow it back to where it came from? A TBM Model that
can't be traced is a black box, and a black box doesn't survive the first hard question from
Finance. Drill and trace is the capability that keeps every other capability defensible.

## How IBM Apptio Costing Standard covers it

Costing Standard names this explicitly as a supported out-of-the-box use case under Business
Unit views: "**Drill and Trace of Costs** — Illustrate how costs flow through the cost model
layers, from infrastructure to applications to services, to provide deeper insight into cost
drivers and allocation logic."

This is operationalized concretely through **Model Reports** (seen here in the Application
context as the "Application Model" report, and available at other levels of the model): "Model
Reports in Apptio provide complete traceability of how cost data moves through the Apptio model
covering Allocation Models, Tower/Sub-Tower structures, Cost Pools etc. They are used to
validate, troubleshoot, and analyze the data transformations applied at each stage of the
model."

In practice, this means an analyst (or, in a well-run model, a business stakeholder) looking at
an Application TCO number that seems off can drill directly into the allocation path — which
Cost Pool, which Resource Tower, which allocation rule — rather than being told to "trust the
model" or re-derive the number manually in a spreadsheet.

## Why this matters in a client conversation

This is the capability that separates a TBM Model that survives audit scrutiny from one that
doesn't. Almost every TBM engagement eventually hits a moment where a business stakeholder
disputes a number — the difference between a productive conversation ("let's drill in and see
exactly where that cost comes from") and a credibility crisis ("we'll have to check the
spreadsheet and get back to you") is whether this traceability capability was built into the
model from the start.

It's also directly relevant to model governance conversations: when allocation rules change
(a common event as an organization matures its TBM practice), drill/trace is what lets a team
verify the change had the intended effect before it ships to end users, rather than discovering
a broken allocation only after a business unit complains about a wildly wrong number.

## Source documents

- Business Unit Overview (names "Drill and Trace of Costs" as a supported use case) — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-overview.md`
- Applications Reports (documents the Application Model report mechanism) — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-reports.md`