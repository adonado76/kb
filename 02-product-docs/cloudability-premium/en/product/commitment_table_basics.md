---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Commitment Table Basics"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Understanding Commitment Management Basics in Cloudability"
source_path: "product/commitment_table_basics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Commitment Table Basics

## Purpose

The purpose of this document is to introduce how meta data is displayed across the commitment
pages expectation and explain the data shown in Cloudability’s commitment tables and how to read,
filter, and export it consistently across pages (Manager, Portfolio, Recommendations). This is a
practical reference for columns, sorting, and interpretation.

## Information Architecture

Metadata for commitments, recommendations, and groups appears in three UI patterns across the
app:

**Table** — A tabular grid with columns and column groups (headers) that organize related
fields for easy comparison.

**Details Panel (Right Drawer)** — A slide out panel that displays field level properties and
contextual actions for the selected row or card.

**Summary Card** — A page level card that surfaces key metrics or attributes relevant to the
current view (commonly used on the Recommendations page).

Why this is important: Standardized display patterns make information scannable, align Help
Center terminology with the product UI, and ensure consistent reporting and analysis across
providers.

## Where You’ll See UI Components

**Commitment Manager** — Aggregate level overview with a time series chart of commitment costs
and savings. In the future, we will add a Monthly Rollup table to summarize the periodized costs
shown in the chart.

**Commitment Portfolio** — A tabular inventory of commitments. Each row includes a Details
action (right aligned) that opens the Details Panel (Right Drawer) to show fields not present in the
table.

**Commitment Recommendations** — A summary view that mirrors Portfolio interactions. The
Details action opens a dedicated Details Page (instead of the drawer). A Summary Card highlights
recommendation assumptions (term, scope, sharing, payment) and modeled KPIs such as cost and net
savings.

Why this is important: We're defining consistent naming for these UI components (Table, Details
Panel, Summary Card, Details Page) to more effectively explain concepts later in this documentation.

## Data Reference

The following table provides a reference for each field shown across the commitment pages.

*Commitment Details*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Field** | **AWS** | **GCP** | **AZURE** | **Notes** |
| Commitment ID | ID | ID | — | Unique identifier for the commitment record. |
| Category | Category | Category | — | Vendor agnostic category (e.g., Resource vs. Spend). |
| Service | Service | Service | — | Service or Product family (e.g., EC2, GCE, RDS). |
| Region | Region / Availability Zone | Region | — | Location of a resource. |
| Term | Term | Term | — | Typically, 1 or 3year. |
| Payment Option / Billing Frequency | Payment Option | — | — | AWS: No/Partial/All Upfront. GCP: effectively no upfront for most commitments. |
| Upfront Cost | Upfront Cost | — | — | Recognized by basis (cash vs. adjusted). |
| Hourly Commitment Amount | Hourly Amount | Hourly Amount | — | Contextual to the commitment e.g., GCP Resource CUDs show vCPU/Memory/SSD/GPU quantities; AWS EC2 RI shows count/quantity. |
| Commitment List Discount Rate | — | List Savings Rate | — | Published discount rate for the item. |
| OS | OS | — | — | Applicable to some compute commitments. |
| Tenancy | Tenancy | — | — | Dedicated vs. shared tenancy (AWS). |
| Class | Class | — | — | Standard vs. convertible (where applicable). |
| Sharing | ISF | — | — | Instance Size Flexibility / sharing indicator (AWS). |
| Units (deprecated) | Units | — | — | No longer required. |
| Region Sharing Bool | MultAZ | — | — | Indicates multiAZ/region sharing behavior (AWS). |
| Engine Type | Engine Type | — | — | Applicable to certain database/search products. |

*Account & Ownership*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Field** | **AWS** | **GCP** | **AZURE** | **Notes** |
| Payer Account Name | Payer Account | Billing Account | — | Invoice owner / billing context. |
| Payer Account ID | — | Billing Account ID | — | Identifier for the billing account (GCP). |
| Linked Account Name | Linked Account | Project | — | Consuming account/project. |
| Linked Account ID | — | Project ID | — | Identifier for the project (GCP). |

*Performance (NonKPI Fields)*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Field** | **AWS** | **GCP** | **AZURE** | **Notes** |
| [Reported] Commitment Cost | Cost | Cost | — | Sum cost of commitments within the selected scope/period. |
| [Paid] Commitment Cost | Paid Cost | Paid Cost | — | Recognized per basis (cash vs. adjusted). |
| [Lifetime] Commitment Cost | Lifetime Cost | Lifetime Cost | — | Cumulative cost over the commitment’s life. |
| Reported Commitment Net Savings | Net Savings | Lifetime Net Savings | — | May differ in naming; reflects period vs. lifetime on GCP. |
| Reported Commitment Savings Rate | Savings Rate | Savings Rate | — | Current savings rate for the row’s scope (not a portfolio KPI). |
| Reported Commitment Utilization | Utilization | Utilization | — | Blended utilization for the row (not a portfolio KPI). |
| [Remaining] Commitment Cost | Remaining Cost | Remaining Cost | — | Forward exposure until expiration. |
| Reported Unrealized Net Savings | Unrealized Net Savings | — | — | Potential savings not yet realized due to under utilization. |
| Hourly OnDemand Commitment | — | OnDemand commitment | — | GCP reference value for comparison (where available). |
| Hourly Net Savings | — | Net Savings (Hourly) | — | Where exposed at hourly granularity. |
| Breakeven | — | Breakeven (Months) | — | Months to break even given current usage. |

*SubQuantities (GCP Resource CUDs)*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Field** | **AWS** | **GCP** | **AZURE** | **Notes** |
| Hourly Commitment Amount — Cores | — | Hourly Commitment Amount (Cores) | — | vCPU quantity committed. |
| Utilization — Cores | — | Utilization (Cores) | — | vCPU utilization of the committed quantity. |
| Hourly Commitment Amount — Memory | — | Hourly Commitment Amount (Memory) | — | Memory (GiB) quantity committed. |
| Utilization — Memory | — | Utilization (Memory) | — | Memory utilization of the committed quantity. |
| Hourly Commitment Amount — SSD | — | Hourly Commitment Amount (SSD) | — | SSD quantity committed. |
| Hourly Commitment Amount — GPU | — | Hourly Commitment Amount (GPU) | — | GPU quantity committed. |

*Recommendation Details (Where Applicable)*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Field** | **AWS** | **GCP** | **AZURE** | **Notes** |
| Recommendation SubType | Instance Family / Node / Instance Type | Machine Type | — | Proposed shape/family for the recommendation. |
| Monthly Recommendation SUD Credit | — | Recommendation Sustained Use Discount Credit (Estimated Monthly) | — | GCP specific estimate. |
| Lifetime Recommendation SUD Credit | — | Recommendation Sustained Use Discount Credit (Estimated Lifetime) | — | GCP specific estimate. |

*Status & UI*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Field** | **AWS** | **GCP** | **AZURE** | **Notes** |
| State | State | — | — | Current state (active, retired, etc.). |
| Start Date | Start Date | — | — | Effective start. |
| End Date | Expiration | — | — | Effective end / expiration. |
| Details Button | Details Icon | Details Icon | — | UI control to open the drawer/details page. |
| Total Number of Commitments | Commitments | — | — | Label above the table next to the export icon (UI label). |

## Working With the Table

**Filter Bar** — Manual filter across meta data by using the common filter toolbar.

**Filter Hyperlink** — Hyperlinked cells in the table are immediately available to filter as
'equals'. Select a hyperlink to filter the table by this value. The filter chip will appear in the
filters toolbar above.

**Show/Hide Columns** — Use the Show/hide columns bar on the right side of the table to select
which columns you wish to view. (Coming soon)

**Sort & MultiSort** — Click a header to sort descending. Click again to sort ascending.
Click a third time to return to the default state.

**Export** — The export button provides a CSV of the data in the table in a what you see is
what you get format. Note that all meta data is included in this export.

## Takeaway

Getting fluent in the tables, labels, and layouts used across Commitment Manager, Portfolio, and
Recommendations is foundational. With a consistent vocabulary (Table, Details Panel, Summary Card,
Details Page) and a clear mapping of field names across providers, you’ll:

- Read rows in context (scope, term, payment), avoiding misinterpretation.
- Trace ownership and sharing correctly (payer/billing account vs. linked account/project).
- Compare apples-to-apples across clouds using normalized fields.
- Move faster from what you see (table) to why it matters (details, sub quantities, performance
  fields) and what to do next (filters, export, and Recommendations).

With this foundational information, subsequent documentation will dive deeper into the
application and how it’s used to optimize cloud spend.

**Parent topic:** [Understanding Commitment Management Basics in Cloudability](../product/commitment_management_basics.html)
