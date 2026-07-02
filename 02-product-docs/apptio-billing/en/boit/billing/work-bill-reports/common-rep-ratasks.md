---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Common report tasks and usage patterns"
breadcrumb:
  - "Billing"
  - "Working with Billing Reports"
source_path: "boit/billing/work-bill-reports/common-rep-ratasks.html"
images:
  - "boit/billing/work-bill-reports/clip_image001_-162976121.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Common report tasks and usage patterns

Regardless of edition, users tend to perform the same core actions in Billing reports.
This subsection focuses on patterns rather than specific UI controls.

## Filtering and focusing

Common tasks:

- Filter to a single period or a small range of periods.
- Filter to a specific consumer (for example, one business unit).
- Filter to a specific offering or service.
- Combine filters (for example, one consumer and one service across three months).

Usage tips:

- Start broad, then narrow to the area of interest as questions arise.
- Save commonly used filter combinations if the front end supports saved views or
  bookmarks.

## Drill-down and traceability

Users often need to drill from a summary to detail:

- From a total charge by consumer to the list of services driving that charge.
- From a service total to the underlying line items or domain-level breakdown (for
  example, cloud accounts, applications, or devices).
- From a current period view to prior periods to understand trends.

Usage tips:

- Use drill actions to avoid exporting unnecessarily.
- For repeated investigations (for example, always drilling into one particular service),
  consider documenting that path in local procedures or internal training.

## Comparing periods

Billing reports are frequently used to answer “what changed this month?”

Typical approaches:

- Use comparison columns in the same report:
  - Current period vs prior period.
  - Current period vs same period last year.
- Use chart or table views that show multiple periods across the same axis.
- Export two periods and compare externally when required.

Usage tips:

- Focus on significant movements by value or by percentage, not small noise.
- Use Billing in combination with Costing when changes are driven by underlying cost model
  changes.

## Exporting data

Exports are used for:

- Local analysis (spreadsheets, custom charts).
- Sharing with people who do not log into the front end.
- Feeding external tools or Finance systems.

Common export patterns:

- Export invoice-style reports for:
  - Individual consumers.
  - Groups of consumers with a shared manager.
- Export detail reports when deeper analysis or custom pivoting is required.
- Export journal reports in the exact layout required by Finance.

![](../../../../../../03-media/apptio-billing/boit/billing/work-bill-reports/clip_image001_-162976121.png)

Fig #: Export menu showing options to export Invoice report to Excel, PDF, Email, and
Email Subscription.

Usage tips:

- Keep a small set of “official” export layouts that Finance expects, and avoid creating
  multiple slightly different variants.
- If you find yourself exporting the same custom view repeatedly, consider adding a
  dedicated report or saved view.

## Reconciling to Costing and Finance

Billing reports often sit in the middle of reconciliation work:

- **To Costing**
  - Sum Billing charges by consumer and compare to Costing’s recoverable cost.
  - Investigate gaps:
    - Intentional (for example, planned subsidy or margin).
    - Unintentional (for example, missing consumption or incorrect rates).
- **To Finance**
  - Compare Billing journal output to posted journal entries.
  - Ensure:
    - Totals align.
    - Consumer segments or cost centers match.
    - Any foreign currency or FX treatment matches agreed rules.

Documenting the reconciliation steps helps avoid repeating the same investigations every
month.
