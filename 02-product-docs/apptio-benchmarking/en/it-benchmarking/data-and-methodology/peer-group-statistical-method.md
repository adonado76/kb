---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Peer group and statistical methods"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Data and Methodology Reference"
source_path: "it-benchmarking/data-and-methodology/peer-group-statistical-method.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Peer group and statistical methods

Benchmarks do not show individual organizations. They show what the distribution of peers looks
like.

## Peer group construction

A peer group is typically defined by:

- Industry
- Size band (usually revenue)
- Region or geography

Rules applied in the background:

- Minimum sample sizes before a metric is reported
- Exclusion or trimming of extreme outliers in some datasets
- Anonymization that prevents identifying individual contributors

## Percentiles and quartiles

Common statistics:

- Median – the 50th percentile
- Lower quartile – the 25th percentile
- Upper quartile – the 75th percentile
- Minimum and maximum, sometimes with outliers trimmed

Charts usually represent:

- Median as a line or dot
- Interquartile range as a band or box
- Your organization as a separate marker

Interpreting:

- If you are near median, you are typical
- Inside the band, you are within a normal range
- Outside the band, you are structurally different and should know why

  ![Interactive Benchmarking box plot](../../resources/images/it%20benchmarking_images/indistry-specific-distribution.png)

## Archetypes

Archetypes are patterns derived by clustering organizations based on their spend structure.

Types supported with Interactive Benchmarking data:

- **Hardware Technology-centric:** A Technology operating model where delivery relies heavily
  on owned or directly managed infrastructure. Typical characteristics include:
  - Larger on-prem or colocation footprint, more physical infrastructure to run.
  - More spend on infrastructure platforms and underlying tech stacks.
  - Often more internally managed operations (or at least hardware ownership), even if some labor is
    outsourced.
- **Software Technology-centric:** A Technology operating model where delivery relies heavily
  on software platforms, tooling, and licenses rather than owned hardware. Typical characteristics include:
  - Higher use of SaaS, platform subscriptions, automation tooling, and enterprise software
    stacks.
  - Infrastructure may be abstracted (cloud or managed), shifting emphasis away from hardware
    ownership.
  - More spend on security, observability, ITSM, collaboration, developer platforms, and enterprise
    apps.
- **Vendor-centric:** A Technology operating model where a large portion of work is performed
  by third parties. Typical characteristics include:
  - Heavy managed services, systems integrators, outsourcing partners, and contractors.
  - Internal teams focus more on governance, architecture, vendor management, and product
    ownership.
  - Delivery capacity is scaled by vendors more than hiring.
- **People-centric:** A Technology operating model where capability is delivered primarily by
  internal employees. Typical characteristics include:
  - Larger in-house engineering and operations teams.
  - Strong internal ownership of delivery and run activities.
  - Vendors may exist, but internal teams do most of the work.

Use cases:

- Understanding which broad pattern your organization resembles.
- Explaining that you look different from the median because you intentionally follow a different
  archetype.

![Archetype radar charts appearing in the “Industry & OpEx Benchmarks” report in Costing.](../../resources/images/it%20benchmarking_images/archetype-radar-chart.png)
