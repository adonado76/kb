---
tbm_concept: "Business Value Streams — general framework"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 01-practice-sources/tbm-council/2025_-_TBM_Taxonomy_Version_5_0_1_-_Whitepaper.pdf
  - 01-practice-sources/tbm-council/TBM_Practitioner_Student_Guide.md
  - 01-practice-sources/tbm-council/TBM_Apptio_Advisory_Establishing_TBM_Practice.md
last_updated: "2026-07-02"
---
# Value Streams — How IBM Apptio Costing Standard Enables This View of IT Investment Value

## The concept

The TBM Taxonomy v5.0.1 formally defines Business Value Streams as part of the Technology
Consumer layer: "Cross-functional flows of work that deliver value to customers or internal
stakeholders — such as 'Customer Onboarding,' 'Claims Processing,' or 'Product Fulfillment.'
Value streams typically span multiple functions and align with product or process-based
delivery models."

That "cross-functional" and "span multiple functions" language is the operational challenge:
a value stream like Customer Onboarding doesn't map to one application, one team, or one cost
center — it cuts across several. A CIO trying to show "the value of IT investment" business-unit
by business-unit, or application by application, will systematically miss how much of that
investment is actually organized around end-to-end outcomes the business actually experiences.

The TBM Council's practitioner training material reinforces this as a live capability, not just
a taxonomy entry: it explicitly names "Connecting Costs Across Value Streams" as a TBM practice,
noting that "value streams are enabled by a mix of TBM Solutions and Resources" — meaning value
stream costing is always a composite view built on top of the Solutions and Resource Tower
layers, not a separate ledger.

## How IBM Apptio Costing Standard enables this view

Costing Standard doesn't have a feature literally named "Value Streams," but the structural
mechanism it already provides is exactly what a value stream view requires:

- The **Labor Mapping workbench** (documented in the Cost Pool to Resource Tower allocation
  brief) already tags each resource to "Solution Type and Solution Category" — the same
  hierarchical structure (Type → Category → Name → Offering) the TBM Taxonomy Solutions layer
  defines. A value stream can be modeled as a custom Solution Category or a set of tagged
  Offerings that span the applications and services actually involved in that cross-functional
  flow.
- **Product TCO** and **Services TCO** (documented in their own briefs) already aggregate cost
  across labor, infrastructure, vendor, and platform for a single product or service — the same
  aggregation mechanism, applied to a value-stream-aligned grouping instead of a single
  application, is what produces a value stream's fully burdened cost.
- **Business Unit** views' "Drill and Trace of Costs" capability (documented separately) is what
  lets that aggregated value-stream cost be decomposed back down to the individual applications,
  towers, and cost pools that fed it — critical for explaining *why* a value stream costs what it
  costs, not just reporting the total.

## Why this matters in a client conversation

This is a genuinely useful reframe for a CIO trying to show IT investment value in board-level
terms: "our Compute spend" or "our Application portfolio spend" doesn't mean much to a business
leader, but "the cost to deliver Customer Onboarding end-to-end, and how that's trending" does.
Costing Standard's Solution tagging structure is the mechanism that gets from one view to the
other without building a second, parallel cost model — a client asking "can this show value by
value stream, not just by application" gets a structural yes, built on capabilities already
documented in this knowledge base, not a custom development effort.

An honest scoping note: value stream reporting is a *configuration* of the existing Solution
taxonomy (defining which Types/Categories/Offerings constitute a given value stream), not an
out-of-the-box report that ships pre-built — it requires the client to define their value streams
first, typically in partnership with business stakeholders, before Costing Standard can report
against them.

## Source documents

- TBM Taxonomy Version 5.0.1 Whitepaper (Technology Consumer Layer, "Business Value Streams"
  definition) — `01-practice-sources/tbm-council/2025_-_TBM_Taxonomy_Version_5_0_1_-_Whitepaper.pdf`
- TBM Practitioner Student Guide ("Connecting Costs Across Value