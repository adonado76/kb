---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Appendix A: Glossary & Acronyms"
breadcrumb:
  - "Getting Started"
  - "Appendix A: Glossary & Acronyms"
source_path: "SSIU957/it-benchmarking/key-terminology.html"
images: []
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Appendix A: Glossary & Acronyms

This appendix gives clear definitions for the terms and acronyms used across this Benchmarking Help. It is meant to be quick to scan and quote.

If you are in a meeting and someone asks “what exactly does that mean,” this is what you should be channeling.

## Core TBM, ITFM, and Apptio terms

ATUM (Apptio’s TBM Unified Model)

Apptio’s implementation of TBM. More information about ATUM is available here .

Benchmark enabled Costing report

A Costing report that includes benchmark values alongside your own numbers. For example, a report that shows your cost per server, the benchmark median, quartiles, and the variance. These reports allow drill from benchmark gap to accounts, vendors, services, or applications.

Cost Pool

A TBM category that groups cost by what was bought or how it is accounted for. Examples: Labor, Hardware, Software, Outside Services, Facilities. These are cross cutting and show cost types across towers.

Costing project

A single Costing “container” or endpoint inside your Apptio environment. Each Costing project has its own data sources, mappings, allocation logic, reports, metrics, and permissions, usually scoped to a specific organization, department, region, or IT footprint. In Benchmarking context, the “Costing project” is the chosen container that acts as the system of record, supplying annual IT cost by Cost Pool and Resource Tower.

IBM Apptio (Interactive) Benchmarking

The product that compares your IT costs, structure, and infrastructure efficiency against external benchmarks, using TBM concepts. It combines external datasets, your Costing data, and your organizational profile.

IBM Apptio Costing

The Apptio product that models and allocates technology costs. Previously branded as “Cost Transparency.” In this guide, “Costing” is the preferred system of record for IT cost that feeds Benchmarking.

ITFM / ITFMA (IT Financial Management / IT Financial Management Analyst)

The function and analyst focused on IT budgeting, forecasting, and financial analysis. They often share responsibility with TBMAs for Costing and Benchmarking and work closely with Finance.

Resource Sub-Tower (Sub-Tower)

A sub-unit a Resource Tower, used heavily for Infrastructure benchmarking. Examples: within Compute, you might have Servers; within Storage, you might have Block, File, Object. Sub-Towers are where infra unit cost and efficiency metrics are usually defined.

Resource Tower (Tower)

A major logical grouping of IT capabilities or infrastructure defined by the TBM Taxonomy. Examples: End User, Compute, Storage, Network, Data Center, Platform, Application, Security. Towers tell you where IT costs sit from a technical domain perspective.

TBM (Technology Business Management)

A management discipline and framework that connects technology spend, resources, and services to business outcomes. In practice, TBM gives you a standard way to categorize tech costs and talk about them with Finance and business leaders. TBM defines standard Cost Pools, Resource Towers, and Resource Sub-Towers. More information about the TBM Taxonomy is available here .

TBMA (Technology Business Management Analyst)

The practitioner who builds and maintains the TBM model, configures Apptio products, and explains results. In this guide, TBMAs are usually the primary users of configuration and troubleshooting content.

## Key Benchmarking concepts

Archetype

A standard pattern of IT spend or structure found by clustering organizations. Examples: “labor heavy” vs “vendor heavy,” “data center heavy” vs “cloud forward.” Archetypes explain why you differ from median and which broad pattern you resemble.

Benchmark

A metric that describes how a group of organizations perform on a defined measure. For example, the median cost per server for a peer group in your industry and size band.

Benchmark profile

A collection of benchmark values computed for a specific peer group and time period. A profile is essentially “the benchmark view of the world” that your data is compared against and that can be reused in multiple reports.

Industry metrics

Enterprise level IT economics metrics, such as IT spend as percentage of revenue or IT spend per employee. These are used to answer “how big is IT compared to the business” versus peers.

Infrastructure benchmarks

Unit cost and efficiency metrics for infrastructure towers and Sub-Towers. Examples: cost per server, cost per TB, FTE per 100 servers. These are used in tower level deep dives and optimization work.

IT OpEx benchmarks (IT OpEx benchmarks)

Metrics that describe how your operating expense is distributed by Cost Pool and by IT Tower. These help answer “how is our spend structured” compared to peers.

Peer group

The set of organizations you are compared to. Typically filtered by industry, revenue or size band, region, and sometimes other attributes. Peer groups must be large enough to meet minimum sample thresholds or metrics are suppressed.

Percentile

A value that indicates the position in a distribution. The 50th percentile is the median. The 25th and 75th percentiles are the lower and upper quartiles.

Quartiles / Interquartile range

The 25th percentile (lower quartile), 50th percentile (median), and 75th percentile (upper quartile). The interquartile range is the band between the 25th and 75th percentiles. Benchmark charts often show the median as a line or point and the interquartile band as a box or shaded region.

## Data and scope terms

Business OpEx

The total operating expense of the business units supported by the in-scope IT organization. It should reflect all ongoing business operating costs for that scope, not just IT, and is used as the denominator for metrics like “IT spend as a percentage of Business OpEx.” If you are an insurance company, include underwriting expenses, and loss and loss-adjustment expenses. If you are a bank, include interest expenses and non-interest expenses. If you are a government or nonprofit, use the enterprise operating budget for the supported scope.

CapEx / OpEx

Capital Expenditure and Operating Expenditure. Benchmarks typically focus on periodic IT cost (an OpEx view that includes depreciation or amortization of capitalized investments). It is important to understand whether CapEx related costs are included in the IT cost used for benchmarking.

FTE (Full Time Equivalent) A normalized headcount measure. In cost modeling, billing, and benchmarking, FTE does not translate or refer to a full-time employee. One FTE represents a standard full-time person utilized at 100% of their capacity. Two half-time people together would amount to one FTE. The measurement is used for metrics such as FTE per 100 employees or FTE per 100 servers.

Headcount

The simple count of people in scope, without adjusting for how many hours they work. Each individual counts as 1 , whether they are full time, part time, or temporary. Typically reported as a point-in-time snapshot (for example headcount as of month end).

IT cost

All costs that are treated as in scope for IT in the TBM model. Usually includes Labor, Hardware, Software, Outside Services, and Facilities that support technology towers. May include depreciation and amortization, depending on accounting treatment. In-scope IT costs exclude other technology-related costs found in other organizations/departments.

Organizational profile

The set of attributes that define how you appear to the benchmark engine. Typical fields: organization name, industry, region, annual revenue, headcount or FTE count, and sometimes complexity indicators like number of applications or customers. The profile drives peer group selection and scaling metrics.

Revenue

The enterprise revenue associated with the business units supported by the IT organization being benchmarked. Only include revenue for the portion of the company that the in-scope IT spend actually supports, not total group revenue if IT covers only a subset. If you are a bank, determine revenue by using total interest income plus non-interest income, minus provision for loan losses. If you are an insurance company, determine revenue by using gross written premiums plus other relevant operating income.

Scope

The boundary of what is included in the analysis. For example: only Corporate IT vs IT plus telecom, or global IT vs one region. Scope must be consistent between IT cost, revenue, and headcount for benchmark ratios to make sense.

Unit cost

A cost normalized by a volume or capacity measure. Examples: cost per server, cost per TB, cost per employee. Unit costs allow comparison between organizations of different size.

Volume / Capacity data

Non financial counts or measures used as denominators in unit cost and efficiency metrics. Examples: number of servers, TB of storage, number of network devices or ports, number of end user devices, FTE counts for specific teams.

## Program and governance terms

Change log (for Benchmarking)

A simple record of meaningful configuration changes that can affect interpretation of results. For example: switching TBM version, switching Costing project, changing default peer group, enabling Infra domain. Used to explain structural breaks and avoid confusion.

Configuration summary

A short, documented snapshot of how Benchmarking is currently wired. Typical contents: Costing project used, TBM version, default peer group definition, enabled domains, and active benchmark year. Used to keep everyone honest and aligned.

QBR (Quarterly Business Review)

A recurring forum where performance is reviewed and decisions are made. In this context, QBRs often include benchmark views for key towers or themes.

Resource Tower owner / Domain lead

The person accountable for a specific Resource Tower or domain such as End User, Network, Storage, Compute, or Security. Resource Tower owners use Resource Tower and infra benchmarks to understand where their area stands and what needs to change.

Steering committee / governance board

A cross functional group of leaders (IT, Finance, sometimes business) that oversee IT strategy, investments, and performance. Benchmarks are often used in these sessions as external context for major decisions.

TBM / ITFM Program Lead

The owner of the TBM and IT financial management program. This person defines how Benchmarking is used, approves structural configuration changes, and represents Benchmarking in governance forums.

TBM Program

The ongoing effort to use TBM practices and tools to manage technology cost, consumption, and value. Benchmarking is one component of this program, alongside Costing, Planning, and related governance.
