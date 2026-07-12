---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Integration Patterns"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Data Architecture"
source_path: "studio/new-uc/concepts-architecture/data-architecture/data-integrations-patterns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Integration Patterns

Data can enter TBM Studio through several integration methods. The right choice depends on your
data volume, update frequency, technical capabilities, and governance requirements.

## File-Based Integration

File upload is the most common and straightforward way to load data into TBM Studio.

**Manual File Upload**

Users create a table in Data Studio and upload a CSV or Excel file through the browser-based
interface. The platform parses the file, detects the schema, and loads the data into the transform pipeline.

- **Best for:** Initial data loads, one-time reference data, or ad-hoc updates.
- **Supported formats:** CSV, TSV, XLS, XLSX. Delimiters supported include comma, tab, pipe,
  tilde, colon, and semicolon.

Tip: File names must contain only one period (before the extension). For example,
example\_data.xlsx is valid, but example.data.xlsx will cause an upload error.

**Scheduled File Processing**

For recurring data loads, you configure the table’s refresh cycle (monthly versions, yearly
versions, etc.) and upload files on a regular schedule. TBM Studio tracks whether expected uploads
have occurred and can send email notifications when data is overdue.

- Best for: Monthly GL files, budget updates, or any data that changes on a predictable cycle.

**File Format Considerations**

TBM Studio uses an enhanced Excel parser (automatically enabled for new customers as of release
12.11.16) that reads raw numerical values directly, bypassing Excel formatting. This ensures
improved numerical precision and consistent date/time handling through epoch format conversion. Be
aware that Excel files containing special formatting or macros may not upload correctly—formatting
should be applied through transform steps after upload.

## API-Based Integration

The Apptio Platform API provides a programmatic alternative to manual file uploads. You can
automate data uploads and downloads using simple HTTP commands integrated into any job scheduler or
application.

The API uses a URL-based interface:

- **Upload:** POST data to a URL specifying the domain, project, table, time period, and action
  (Append or Overwrite).
- **Download:** GET data from tables or report components in Excel or TSV format.

Benefits of API integration include ease of implementation (no software to install),
compatibility with all corporate data systems, and automation through job schedulers.

Note:

**When to Use API vs. Files**

Use the API when you need automated, repeatable data loads that integrate with existing ETL
pipelines or job schedulers. Use manual file uploads for ad-hoc data loads or when the data source
does not support automated extraction.

## DataLink Connections

DataLink (Classic) provides a managed connector framework for importing data from external
databases and applications without requiring custom scripting. It includes a separate agent that can
be installed on-premises to access internal data sources.

DataLink supports:

- Direct database connections for pulling data from enterprise systems
- Schedule-by-time or schedule-by-event execution
- Integration with ServiceNow and other ITSM platforms for pushing TCO data

DataLink is particularly useful for organizations that want a no-code approach to data
integration or need to pull data from systems that are behind firewalls.

## Editable Tables as an Integration Pattern

For small volumes of reference data or classification mappings, editable tables serve as a
lightweight integration method. Users enter data directly through the report interface, and the data
feeds into the transform pipeline and cost model through the publish mechanism.

- Best for: Cost-center attributes, labor mappings, budget annotations, and other data where human
  judgment is the primary source.

## Integration Decision Guide

Use this guide to select the right integration approach:

|  |  |  |
| --- | --- | --- |
| **Scenario** | **Recommended Approach** | **Key Consideration** |
| One-time or ad-hoc data load | Manual file upload | Simple, no setup required |
| Regular scheduled data (monthly GL) | Automated file upload or API | Configure refresh cycle and freshness monitoring |
| Automated ETL pipeline integration | Platform API | HTTP-based; integrates with job schedulers |
| On-premises database access | DataLink (Classic) | Requires on-prem agent installation |
| ITSM integration (e.g., ServiceNow) | DataLink connector | Pre-built connector for TCO data egress |
| Small reference data or classifications | Editable tables | Human-entered; publish feeds pipeline |
| Export model data to external BI tools | Published Tables | Stable API endpoint; schema-controlled |
