---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Troubleshooting"
breadcrumb:
  - "Billing"
  - "Troubleshooting"
source_path: "boit/billing/troubleshooting/troubleshoot.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Troubleshooting

This appendix is a practical “what went wrong and what to check first” guide. Use it
when numbers look off, reports are empty, or journals do not reconcile.

## How to use this appendix

Each subsection is organized by:

- **Symptom**: What you see.
- **Likely causes**: The usual suspects.
- **What to check**: Concrete checks in data, configuration, or process.
- **Who acts**: Typically Admin / Analyst, with others looped in as needed.

## Bills look obviously wrong or empty

**Symptom: Bills are mostly or completely empty**

**Likely causes**

- No consumption data loaded for the period.
- Services not marked as billable.
- Rates missing or invalid for the period.
- Wrong period selected in reports.

**What to check**

1. **Consumption table** for the period:
   - Are there rows for expected services and consumers?
   - Are units nonzero where you expect usage?
2. **Services / offerings table**:
   - Are core services marked Active and Billable?
   - Were any codes or keys changed recently?
3. **Rate table**:
   - Are there rates for all billable services for that period?
   - Are effective dates correct (no off-by-one month problems)?
4. **Report filters**:
   - Confirm the report is filtered to the intended period and consumers.

**Symptom: Total Billing charges are far lower or higher than
expected**

**Likely causes**

- Partial or late consumption feeds.
- Changes in the Costing model not accounted for in Billing assumptions.
- Misconfigured rates (incorrect decimal place, wrong currency, wrong unit).
- Large structural change (migration, retirement) not communicated.

**What to check**

1. Compare **total units** by service vs prior period:
   - Look for big percentage changes.
2. Compare **rate values** vs prior period:
   - Look for rates that suddenly doubled, halved, or went to zero.
3. Cross-check **Costing outputs**:
   - Did total cost for key services or domains change in a similar way?
4. Ask domain owners:
   - Any major tech events this period (migration, large rollout, decommission)?

If nothing explains the change, treat this as a defect and trace back through data,
mappings, and rates.

## Missing or unexpected consumers / services

**Symptom: A known business unit, project, or product is missing from bills**

**Likely causes**

- Consumer not present in the consumer master.
- Consumer present but no consumption mapped to it.
- Consumer mapped incorrectly (for example, using the wrong ID or hierarchy).

**What to check**

1. **Consumer master**:
   - Search for the missing entity by ID and name.
   - Confirm it is marked active and assigned to the correct hierarchy.
2. **Mapping tables** (if used):
   - For external IDs or tags, verify mappings to the expected consumer.
   - Check for typos, retired IDs, or duplicate mapping rows.
3. **Consumption table**:
   - Are there any rows for the missing consumer this period?
   - If not, is the upstream system providing data for it?

**Symptom: Services show up that should be retired or internal only**

**Likely causes**

- Service not flagged as retired or non billable.
- Old service codes still referenced by consumption feeds.
- Internal “plumbing” services accidentally marked billable.

**What to check**

1. **Services / offerings table**:
   - Confirm lifecycle status (Active/Retired).
   - Confirm Billable = No for internal-only services.
2. **Consumption table**:
   - Check for usage rows against retired services.
   - Confirm upstream systems have stopped sending those IDs.
3. If necessary, design an **exception handling rule**:
   - For example, route retired service codes into a dedicated “Exception” service for
     a limited time while feeds are cleaned up.

## Units, rates, and unit rate anomalies

**Symptom: Unit rate spike or drop for a single period**

(Deep-dive recipe is in Section 15; this is the short version.)

**Likely causes**

- Fixed costs spread over fewer or more units.
- Costing allocation change.
- Rate change that was not understood or communicated.
- Volume or cost missing for part of the period.

**What to check**

1. **Unit rate report** for that service across multiple periods:
   - Compare Units, Charge, Unit Rate, and Cost per Unit where available.
2. **Rate table**:
   - Confirm the configured rate for that period did not change accidentally.
3. **Costing outputs**:
   - Did total cost for that service change noticeably?
   - Were any allocation drivers updated?
4. **Consumption data**:
   - Check that volume is not truncated (for example, partial month coverage).

**Symptom: Zero or negative charges where they should not exist**

**Likely causes**

- Zero units or zero rates for a service that should be billed.
- Negative adjustments loaded into consumption or cost tables.
- Incorrect sign conventions in model logic.

**What to check**

1. **QA / exception report** for zero or negative values:
   - Identify which services and consumers are affected.
2. **Rate table**:
   - Confirm that rates are nonzero and correctly signed.
3. **Consumption table**:
   - Inspect whether negative or zero volumes were loaded.
4. **Adjustment logic**:
   - If negative adjustments are intentionally used, confirm they are applied only to
     specific correction scenarios.

## Environment, build, and promotion issues

**Symptom: Changes tested in In Development do not appear in Staging**

**Likely causes**

- Documents checked out but not checked in.
- Build not created or not promoted from In Development to Staging.
- Looking at the wrong build in Staging.

**What to check**

1. In In Development:
   - Check for any Billing-related documents still checked out.
   - Ensure they are checked in after testing.
2. Builds view:
   - Confirm a new build was created after check-in.
   - Confirm that build is the one Staging is using.
3. In Staging:
   - Verify which build is active and that it contains the expected changes.

**Symptom: Staging looks correct, Production does not**

**Likely causes**

- Staging build was never promoted to Production.
- Promotion completed but Production is still using older data for the period.
- Users are looking at cached or bookmarked reports for a prior build.

**What to check**

1. **Promotion history**:
   - Confirm the intended Staging build was promoted and succeeded.
2. **Production build ID**:
   - Verify the active Production build matches the validated Staging build.
3. **Reports**:
   - Confirm users are opening reports from the correct endpoint and collection.
   - Refresh filters and, if necessary, bookmarks.

## Reporting issues

**Symptom: Reports time out or are extremely slow**

**Likely causes**

- Very wide time ranges (multiple years).
- Heavy reports with too many unfiltered dimensions.
- Underlying model or dataset queries not optimized.

**What to check**

1. Encourage users to **filter** by:
   - A single period or short date range.
   - Specific consumers or services.
2. Identify reports with consistent performance problems:
   - Consider redesigning them:
     - Aggregating more.
     - Removing rarely used columns.
3. For persistent issues, consider creating **summary reports** for large audiences
   and reserve heavy detail reports for analysts.

**Symptom: Columns or filters changed “unexpectedly”**

**Likely causes**

- Report definition updated in In Development and promoted.
- A cloned local report looks similar but is not the same.
- Saved views or personal filters overriding defaults.

**What to check**

1. Confirm the **canonical report** name and location.
2. Compare current layout to documented design in Appendix B or internal specs.
3. If changes are legitimate, update documentation and training screenshots.
4. If changes are accidental, restore the intended layout in In Development and
   re-promote.

## Journals and Finance integration issues

**Symptom: Finance cannot load journal file**

**Likely causes**

- File layout does not match expected GL import format.
- Required fields (accounts, cost centers, company codes) missing.
- Special characters or encoding issues.

**What to check**

1. Compare the current export to the **agreed template**:
   - Column order, naming, data types.
2. Use QA reports or validations:
   - Look for missing or invalid Finance segments.
3. Test with a **small subset** of lines:
   - Helps isolate formatting vs data content problems.

**Symptom: Journals posted, but totals do not match Billing reports**

**Likely causes**

- Filters applied differently in Billing vs Finance.
- Posting to different periods (for example, accrual vs usage month).
- Rounding or currency conversion differences.
- Some lines rejected during posting.

**What to check**

1. Re-run the **journal export report** for the period:
   - Confirm total by account and consumer.
2. In Finance:
   - Pull a **trial balance or journal listing** for the same accounts and
     period.
3. Compare:
   - If there is a difference, check for:
     - Rejected lines.
     - Manual adjustments.
     - Different period codes.

If mismatches are recurring, agree a **standard reconciliation view** and
calendar cutoffs between Billing and Finance.

## Edition-specific pitfalls

**Essentials-specific pitfalls**

Notice: Applies to Billing Essentials
only.

Common issues:

- Expecting to see domain-rich views (cloud, applications, projects) that require
  Billing Standard.
- Assuming TBM Studio access exists for all roles, when Essentials configuration is
  often owned by a partner or separate team.

Mitigations:

- Set clear expectations about what Essentials can and cannot show.
- Document how to request configuration changes from the team that has Studio
  access.

**Standard-specific pitfalls**

Notice: Applies to Billing Standard
only.

Common issues:

- Over deploying domain components without stabilizing the core PxQ path.
- Misaligning Costing changes with Billing expectations (for example, renaming services
  or altering allocations mid-period).
- Tagging governance gaps undermining cloud and application views.

Mitigations:

- Stabilize the **core service × consumer billing** before layering cloud, project,
  and transfer pricing complexity.
- Coordinate changes to Costing with Billing stakeholders and Finance.
- Use domain-specific QA and exception reports to enforce data discipline.

## When to escalate

Some issues are better handled by a specialized team or a supporting partner.

Escalate when:

- Multiple billing cycles in a row fail to complete or require heavy manual
  workarounds.
- Journal export and posting issues persist even after local checks.
- Model defects are suspected in the delivered components themselves, not only in local
  configuration.
- Legal or regulatory deadlines are at risk due to Billing defects.

Before escalating:

- Capture:
  - Clear symptom description.
  - Period(s) affected.
  - Screenshots or report excerpts.
  - Steps already taken and findings so far.

A disciplined troubleshooting approach plus this appendix will usually resolve most issues
locally. When it does not, good documentation of what you already checked will make any
escalation far more efficient.
