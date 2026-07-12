---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Common TBM Use Cases"
breadcrumb:
  - "Concepts and Architecture"
  - "TBM Fundementals"
  - "Common TBM Use Cases"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/tbm-use-cases.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Common TBM Use Cases

TBM methodology supports several distinct use cases, each addressing a different business need. Understanding these use cases helps you design your TBM Studio implementation to deliver the most value for your organization.

## Showback

What It Is Showback is the practice of communicating IT costs to business units for visibility purposes without actually billing them. Business units see what their IT consumption costs, but the charges are informational only—they do not affect departmental budgets or trigger financial transfers.

- Your organization is new to TBM and wants to build cost awareness gradually
- You need to validate your cost model before tying it to real financial consequences
- Business units are not yet ready to accept IT cost accountability
- You want to drive behavioral change through transparency rather than financial pressure

| Benefits | Limitations |
| --- | --- |
| Benefits | Limitations |
| Low-risk way to introduce cost transparency | No financial incentive to optimize consumption |
| Builds trust in cost data before enforcement | Business units may ignore informational reports |
| Allows time to refine allocation models | Requires ongoing effort without immediate ROI |

Example Scenario Acme Corp’s IT team creates monthly showback reports for each business unit showing their allocated IT costs. The Sales division sees they consume $2.4M/month in IT services. While no money changes hands, the Sales VP begins asking why their CRM system costs more than the industry average, sparking a productive optimization conversation.

## Chargeback

What It Is Chargeback takes transparency one step further by actually billing business units for their IT consumption. IT costs are transferred from the IT budget to consuming departments through formal financial transactions, typically as internal journal entries or inter-company charges.

- Your organization has mature, validated cost models
- Business units have accepted accountability for IT consumption
- You need to create financial incentives for consumption optimization
- Your finance team supports internal cost transfer processes

- Data accuracy is critical: Errors in chargeback directly affect departmental budgets, so your allocation model must be well-validated
- Communication is essential: Business units need to understand what they are being charged for and how they can influence costs
- Dispute resolution: Establish a clear process for business units to challenge charges they believe are incorrect
- Timing: Align chargeback cycles with your organization’s financial close process

Example Scenario After a year of successful showback, Acme Corp moves to chargeback. Each quarter, IT costs are allocated to business units and transferred via journal entries. The Marketing division, now paying $1.8M/quarter for IT, consolidates two redundant analytics platforms, saving $200K annually.

Why This Matters in TBM Studio

TBM Studio’s published tables feature (Data Studio) enables chargeback by exporting allocated cost data in a structured format suitable for import into your ERP or financial system. Budget and Forecast metrics alongside Cost enable variance tracking for chargeback reconciliation.

## Cost Optimization

TBM data provides the foundation for identifying and pursuing cost savings opportunities. By understanding the true cost of IT services and how costs flow through the organization, you can identify inefficiencies, redundancies, and optimization opportunities that are invisible without structured cost data.

- Redundancy elimination: Identify duplicate services or underutilized resources across business units
- Right-sizing: Match infrastructure capacity to actual demand by analyzing consumption metrics
- Vendor consolidation: Use vendor-level cost visibility to negotiate better contracts or consolidate suppliers
- Cloud optimization: Compare on-premises versus cloud costs for specific workloads
- Labor efficiency: Analyze labor costs by service to identify opportunities for automation or process improvement

Why This Matters in TBM Studio

TBM Studio’s Model Report (Sankey view) provides intuitive visualization of cost flows, making it easy to spot disproportionate allocations. Calculated metrics enable variance analysis and trend detection. Drill-through capabilities let you trace any cost back to its source for root-cause analysis.

## Benchmarking

Benchmarking compares your IT costs against reference points—either internal baselines, peer organizations, or industry standards. Effective benchmarking helps answer: “Are we spending the right amount?”

- Time-period comparison: Track costs month-over-month or year-over-year to identify trends
- Business unit comparison: Compare per-user or per-transaction costs across divisions
- Industry benchmarking: Compare your cost ratios against industry peers using standardized TBM taxonomy categories

Why This Matters in TBM Studio

TBM Studio’s time period handling allows you to view cost data across multiple months for trend analysis. Calculated metrics can compute period-over-period variance, and the platform’s standardized taxonomy alignment facilitates external benchmarking.

## Budgeting and Forecasting

TBM data informs IT budget planning by providing a detailed, bottom-up view of IT costs. Instead of setting budgets based on last year’s spending plus a percentage, TBM enables service-level budgeting where each IT service has its own cost target.

- Variance analysis: Compare actual costs against budget each period to identify overruns early
- Service-level budgets: Set and track budgets for individual IT services rather than broad categories
- What-if scenarios: Model the impact of changes (adding users, retiring applications, migrating to cloud) on overall IT costs

Why This Matters in TBM Studio

TBM Studio supports multiple model metrics simultaneously—typically Cost, Budget, and Forecast. All three metrics flow through the same allocation model, ensuring consistent methodology. Report Studio dashboards can display budget vs. actual comparisons, and editable tables allow finance teams to input and refine budget assumptions.
