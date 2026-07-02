---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Prerequisites"
breadcrumb:
  - "Benchmarking"
  - "Quickstart"
source_path: "it-benchmarking/quick-start/prerequisites.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Prerequisites

- **Before you start** 
  - Interactive Benchmarking must be provisioned in Frontdoor to your organization. If you are
    unsure or do not see an “Interactive Benchmarking” button in your Frontdoor environment, please
    inquire with your IBM Apptio point of contact for assistance.
  - If you plan to integrate with Costing, the relevant Costing project must exist and be populated
    with at least one full fiscal year of data
- **You need** 
  - Access to the **Interactive Benchmarking** application
  - Access to the **Costing** project that will feed benchmark-enabled reports (if applicable).

  Note: If you cannot see Benchmarking or cannot open the relevant Costing project, you will not
  get far. Access needs to be fixed.
- **Minimum data to make this worth doing** 
  - Organizational profile data
    - Annual revenue for the IT org scope you are benchmarking
    - Headcount or FTE count for the same scope.
    - Industry and region.
  - IT cost data
    - Annual IT spend by TBM Cost Pool.
    - Annual IT spend by TBM Resource Tower.
    - Optional but recommended: Sub-Tower level allocation for infrastructure.
  - Infrastructure volume data (only if you plan to use infra benchmarks immediately)
    - Number of servers, TB of storage, network devices or ports, and similar metrics.
    - Ideally, FTE counts for the main infrastructure functions.

Remember, you can start with Industry and IT OpEx benchmarks without infra volumes, then add
infra later.
