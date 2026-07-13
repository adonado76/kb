---
concept: "Plan Data Operations (baseline adjustment, comparison, targets, layouts, bulk I/O, multi-currency, external data, reference data refresh, actuals updates)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/enter-financial-details.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/compare-versions-plans.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/set-financial-targets.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/customize-save-share.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/enter-import-line.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/export-populate-line.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/enter-display-line.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/ext-li.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/update-refdata-plan.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/update-actuals-data.md
last_updated: "2026-07-05"
---
# Working with Plans — How IBM Apptio Planning Addresses This TBM Capability

## A note on scope before the capability itself

Unlike the previous brief (Plan Creation & Lifecycle Management), this one doesn't cover a single
narrative capability — it's a cluster of **day-to-day plan operations** that a Cost Center Owner
or Budget Process Owner performs once a plan already exists. It's documented as a cluster
deliberately, because in a client conversation these ten mechanics tend to surface individually,
as answers to specific operational questions ("can I bulk-load last year's actuals?", "can two
regions plan in their own currency?"), rather than as one pitch.

## The capability

Once a plan is created, an organization needs a working set of tools to actually populate,
adjust, compare, and govern the data inside it over the course of a planning cycle: bulk-loading
data instead of manual entry, comparing scenarios and prior periods, setting top-down targets
against bottom-up submissions, standardizing how different users see the same plan, handling
multiple currencies, bringing in data owned by external systems without letting it be edited
locally, and keeping the plan synchronized with reference data and actuals that change after the
plan was first built.

## How Apptio Planning solves it

**Baseline adjustment.** Before opening a plan to Budget Owners, Admins can apply bulk
percentage or absolute adjustments to baseline values, scoped by Department/Account and period
range — useful for quickly modeling an across-the-board inflation or cost-reduction assumption.
This is only available while the plan is in the **New** state and is explicitly irreversible
(no undo), which is a governance detail worth flagging to clients up front.

**Comparisons.** Two comparison modes exist: **Period to Period** (comparing time periods within
the same plan — month/quarter/year-over-year) and **Plan to Plan** (comparing versions or entirely
different plans, useful for what-if scenarios). Both require choosing an alignment method — **Plan
Start Year** (align by relative year) or **Matching Fiscal Year** (align by calendar year) —
which matters whenever plans don't share a start year. **Comparison shortcuts** let a user pin up
to four comparison plans and toggle them on/off without reconfiguring each time, and Admins can
set an organization-wide default comparison.

**Targets.** OpEx, CapEx, and Headcount targets can be set top-down at the department level by
Admins/Budget Process Owners (for any department) or by Group Cost Center Owners (for their
subordinate departments), then allocated down or rolled up. Targets surface automatically in KPI
comparisons and in Summary page treemap/waterfall visuals as Plan vs. Target variance — giving
Finance a running view of how bottom-up submissions track against top-down expectations
throughout the cycle, not just at the end.

**Layouts.** Table views (columns, filters, grouping, sorting) can be saved as **Private**
(personal) or **Public** (Admin-managed, visible to all) layouts, with Admins able to set an
organization-wide default layout. This standardizes what different roles see without forcing
everyone into one rigid view.

**Bulk upload / export.** CSV-based bulk operations support four import modes — Replace All,
Replace All with Dimension Filter, Update Data (matched by Line Item Code), and Append Data — and
three export modes — Export All, Export Layout, Export for Re-import. This is the mechanism that
makes migrating a client off spreadsheet-based planning practical instead of requiring thousands
of manual line entries.

**Multi-currency.** Once enabled at the Company Profile level, Planning maintains separate
exchange-rate tables for **Actuals** and **Plan** periods, supports per-line-item currency entry,
and lets Departments carry their own default currency — addressing the common multinational
requirement where a regional team plans in local currency but Finance needs a consolidated view
in a reporting currency.

**External Line Items.** Data owned by another system (e.g., an ERP or PPM tool) can be imported
as read-only lines that Cost Center Owners cannot edit, visible for context but protected from
local overwrite — a clean way to blend externally-governed data into the same plan without losing
ownership boundaries.

**Reference data & actuals refresh.** Plans don't automatically inherit reference data changes
made after they were created; an explicit **Update Reference Data** action shows an impact
summary (items updated/deleted/added/reparented) before applying, and destructive updates are
blocked by default unless an Admin explicitly disables that restriction — in which case a backup
plan is auto-created first. Similarly, **Update Actuals Data** lets Admins refresh actuals in an
open or new forecast plan for selected months, without recreating the whole plan.

## Why this matters in a client conversation

This cluster is where "we already have a planning tool" objections usually get tested in
practice, because most spreadsheet-based or legacy tools handle one or two of these mechanics well
and force manual workarounds for the rest. The combination that tends to land hardest with
Finance stakeholders is Targets + Comparisons: the ability to see Plan vs. Target variance
automatically, without a separate reconciliation exercise, replaces a task that's often a
multi-day manual rollup at month-end in a spreadsheet-based process.

The External Line Items mechanism is a useful answer to a common integration objection — "we
already have this data in [ERP/PPM system], we don't want to duplicate it" — since it lets that
data appear in Planning for context and reporting without creating a second source of truth or
requiring Planning users to maintain it.

The safeguards around destructive reference-data updates (blocked by default, auto-backup when
enabled) and the irreversibility warning on baseline adjustments are both worth surfacing
proactively in governance-focused conversations with clients who've been burned by uncontrolled
spreadsheet edits in the past.

## Source documents

- Adjust Baseline Values — `02-product-docs/apptio-planning/en/it-planning/planning/enter-financial-details.md`
- Compare Versions or Plans — `02-product-docs/apptio-planning/en/it-planning/planning/compare-versions-plans.md`
- Set Targets — `02-product-docs/apptio-planning/en/it-planning/planning/set-financial-targets.md`
- Manage Layouts — `02-product-docs/apptio-planning/en/it-planning/planning/customize-save-share.md`
- Bulk Upload Line-Item Values — `02-product-docs/apptio-planning/en/it-planning/planning/enter-import-line.md`
- Export Plan Data — `02-product-docs/apptio-planning/en/it-planning/planning/export-populate-line.md`
- Working with Different Currencies — `02-product-docs/apptio-planning/en/it-planning/planning/enter-display-line.md`
- External Line Items — `02-product-docs/apptio-planning/en/it-planning/planning/ext-li.md`
- Updating Reference Data in Plans — `02-product-docs/apptio-planning/en/it-planning/planning/update-refdata-plan.md`
- Update Actuals in Forecast Plans — `02-product-docs/apptio-planning/en/it-planning/planning/update-actuals-data.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*