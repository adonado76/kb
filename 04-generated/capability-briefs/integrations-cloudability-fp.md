---
tbm_concept: "Integration with Cloudability Financial Planning (CFP) — cloud budget/forecast consolidation"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
  - apptio-cloudability-premium
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/connect-cfp.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/manage-cfp-wo-int.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/cfp-integration.md
last_updated: "2026-07-05"
---
# Integrations – Cloudability Financial Planning — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Cloud spend behaves financially like any other operating expense, but it's typically planned and
governed in a different tool (Cloudability) than the rest of an organization's IT budget (Apptio
Planning), because cloud cost data has its own granularity, tagging structure, and provider-level
detail that a general-purpose planning tool doesn't natively model. Without a bridge between the
two, an organization either double-enters cloud budget numbers manually in both systems, or
leaves cloud spend as a blind spot in its enterprise-wide departmental budget. TBM addresses this
through a dedicated **Cloud tab** in Planning that can work standalone or connect directly to
**Cloudability Financial Planning (CFP)**.

## How Apptio Planning solves it

**The Cloud tab is independently useful, with or without CFP.** Even without integrating CFP, a
Cloud tab in the Expenses view lets a client manually track cloud spend with the same dimensional
structure as the rest of the plan (Cost Center, Account, Vendor, Location) plus IIP-aware fields
— **Cost Type** (Build vs. Run, defaulting to Run if left blank) and **Project**. This means
the Cloud/Run distinction and project tagging seen elsewhere in this knowledge base (Asset,
Contract, IIP delegation) extends naturally into cloud spend as well.

**CFP integration is configured per plan, not globally**, connecting a specific Apptio Planning
plan to a specific CFP Plan and Cost Ownership View — with an explicit constraint that only CFP
plans sharing the *same start year* as the Planning plan are selectable, and that CFP integration
only supports Gregorian fiscal calendars (445 and 13-period calendars are not supported for this
specific integration, though the standalone Cloud tab works with any supported calendar). This is
a concrete scoping detail worth confirming early with any client using a non-Gregorian fiscal
calendar.

**Dimension mapping bridges two different data models.** CFP's Cost Ownership values must map to
Planning's Department, Cost Center, and Account (Project and Vendor optionally), with built-in
reference-data validation ensuring a mapped Department is actually valid for its Cost Center, and
a mapped Project is valid for that Cost Center — preventing an import from silently creating
orphaned or inconsistent dimensional combinations. Default fallback values (Default Department,
Default Cost Center, etc.) handle Cost Ownership values that don't have an explicit mapping,
rather than failing the import outright.

**Fill Forward controls how a CFP plan's typically-shorter horizon extends into Planning's
typically-longer one.** Three options — None, Copy Last Period, or Copy Last Year — determine
whether/how CFP data (which may only cover a shorter forecast window) gets projected into future
years that exist in the Planning plan but not in the CFP source, which matters because Planning
plans commonly run up to ten years while cloud forecasts are usually shorter-horizon.

**Imported lines are read-only External Lines** — the same governance pattern documented in
Working with Plans — identified with a `CL`-prefixed Line Item Code, and subsequent imports
overwrite the same lines (retaining their codes) rather than duplicating them. A notification
banner alerts users with import permission when the source CFP plan has new data available, so
re-importing to refresh is a deliberate, visible action rather than something that happens
silently or gets missed.

## Why this matters in a client conversation

For any client already using or considering Cloudability alongside Apptio Planning — a highly
relevant combination in Armando's FinOps/TBM practice — this integration is the concrete answer
to "does our cloud budget show up in the same departmental view as the rest of our IT spend, or
do we have to reconcile two systems by hand every cycle?" Leading with the fact that CFP lines
stay read-only and clearly tagged (as External Lines, with a distinct Line Item Code prefix)
addresses a natural governance question up front: cloud teams keep planning in the tool built for
cloud granularity, while Finance still gets a single consolidated departmental view without
anyone needing to double-key numbers.

The same-start-year and Gregorian-calendar-only constraints on CFP integration are worth
surfacing early in any technical discovery — they're the kind of detail that, if missed during
scoping, becomes a late-stage surprise. The standalone Cloud tab (no CFP required) is a useful
fallback to mention for clients not yet on Cloudability, or for clients on a non-Gregorian fiscal
calendar who still want structured cloud spend tracking inside Planning.

## Source documents

- Connect to Cloudability Financial Planning — `02-product-docs/apptio-planning/en/it-planning/planning/connect-cfp.md`
- Manage Cloud Expenses (without CFP Integration) — `02-product-docs/apptio-planning/en/it-planning/planning/manage-cfp-wo-int.md`
- Set Up and Manage Cloud Financial Planning Integration — `02-product-docs/apptio-planning/en/it-planning/planning/cfp-integration.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*