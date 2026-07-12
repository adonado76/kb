---
tbm_concept: "Approval Workflows & Collaboration (governance routing, versioning, audit trail, threaded review)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/about-approval-workflows.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/aw-sub-return-approve.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/snapshots.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/view-upd-li.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/plan-status.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/change-history.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/comments.md
last_updated: "2026-07-05"
---
# Workflows & Collaboration — How IBM Apptio Planning Addresses This TBM Capability

## The capability

A budget isn't finished when the numbers are entered — it's finished when the right people have
reviewed and signed off on it, in the right order, with a record of what changed and why. Most
spreadsheet-based planning processes handle this with email chains and manually-tracked approval
status, which breaks down as soon as an organization has more than a handful of departments or
needs anything beyond a single, flat sign-off. TBM addresses this through structured **Approval
Workflows** paired with **versioning, audit trail, and collaboration** tooling that keeps the
review process traceable rather than ad hoc.

## How Apptio Planning solves it

**Two distinct workflow models cover different organizational realities.** **Hierarchical
Approvals** route a plan up the Department org structure itself — approval must climb level by
level, Group Departments can submit (and auto-approve) all their children together, and
"skip nodes" let an organization bypass management layers that don't need to individually
approve. **Multi-Level Approvals** instead define a custom, sequential chain (L1 → L2 → up to
L10) per Department, independent of the org chart — useful when sign-off needs to come from
specific roles (e.g., Finance, then Security, then a VP) rather than following reporting lines.
Critically, these aren't just cosmetic differences: rejection behavior differs (hierarchical
rejection cascades down one level at a time; multi-level rejection resets all the way back to
Level 1), and Edit vs. Approval permission are unified in hierarchical mode but explicitly
separated in multi-level mode (someone can approve without edit rights, or edit without being an
approver).

**Submission creates an automatic snapshot — governance without extra clicks.** Every plan
submission (and every New→Open state transition) automatically generates a read-only,
timestamped snapshot, giving every planning cycle a real audit trail by default, not one that
depends on someone remembering to save a version. Snapshots can also be created manually at any
time, used as a comparison basis (feeding directly into the Comparisons capability), and restored
as the current version if a department needs to revert unwanted changes — with the safety
behavior that restoring first snapshots the current state before overwriting it, so a restore is
itself non-destructive.

**View Updated Line Items turns a full-table review into a delta review.** Rather than an
approver re-reading an entire department's line items every cycle, this toggle filters the
Expenses table to only what changed (New/Updated/Deleted) since the last snapshot, with
Modified-By and Last-Updated metadata — directly reducing review time for large plans while
keeping accountability visible.

**Plan Status gives a single governance dashboard.** Every department's current state
(In Progress / Submitted / Approved / Returned) is visible centrally, with hierarchical or flat
list views depending on workflow type, bulk approve/return/submit actions, and a full exportable
history — the answer to "which departments still haven't submitted" without chasing people
individually.

**Change History is the system-of-record audit trail beyond just approvals** — capturing plan
lifecycle events, data entry, reference data changes, and role/permission changes, each with
before/after values, filterable and exportable to CSV for compliance or BI integration.

**Comments support both open and confidential collaboration in context.** Threads can be public
(visible to everyone with plan access) or private (restricted to named members), support
@mentions with email notification, assignment, and resolution — keeping variance and planning
discussions attached to the actual data rather than scattered across email or chat.

## Why this matters in a client conversation

The choice between Hierarchical and Multi-Level Approvals is a good early diagnostic question in
a sales conversation, similar to the Project access-control patterns: an organization whose
approval chain genuinely follows the reporting structure fits Hierarchical cleanly; one where
sign-off needs to come from cross-functional roles (Finance, Compliance, a specific committee)
regardless of org placement needs Multi-Level. Getting this choice right early avoids a
painful mid-cycle workflow migration.

The automatic snapshot-on-submit behavior is worth emphasizing specifically to clients coming
from spreadsheet-based budgeting, where "what did the plan look like when it was submitted for
approval, before these three revisions" is often unanswerable without someone having manually
saved a dated copy — this makes it automatic and guaranteed.

For regulated industries like banking, Change History's exportable, before/after audit trail is
frequently a hard compliance requirement, not a convenience feature — it's worth surfacing this
capability proactively in any conversation with a client whose internal audit or regulatory
function will eventually ask "who approved this budget change, and when."

## Source documents

- Approval Workflows Overview — `02-product-docs/apptio-planning/en/it-planning/planning/about-approval-workflows.md`
- Submit, review, approve, and return plans — `02-product-docs/apptio-planning/en/it-planning/planning/aw-sub-return-approve.md`
- Snapshots (Versioning) — `02-product-docs/apptio-planning/en/it-planning/planning/snapshots.md`
- View Updated Line Items — `02-product-docs/apptio-planning/en/it-planning/planning/view-upd-li.md`
- Plan Status — `02-product-docs/apptio-planning/en/it-planning/planning/plan-status.md`
- Change History — `02-product-docs/apptio-planning/en/it-planning/planning/change-history.md`
- Comments — `02-product-docs/apptio-planning/en/it-planning/planning/comments.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*