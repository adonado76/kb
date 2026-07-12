---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Resource Recommendations"
breadcrumb:
  - "Governance"
  - "Resource Recommendations"
source_path: "SSVCLNQ/admin/governance-resource-recommendations.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Resource Recommendations

Governance provides recommendations for new EC2 and RDS resources being deployed when a similar configuration (matching CPU and Memory requirements) is available at a lower cost. Recommendations are posted as comments on the pull request (PR).

If Governance does not identify a more cost-effective resource, no recommendation will be posted.

Example: Upgrade RDS instance from db.m5.8xlarge to db.m6g.8xlarge to save costs while maintaining performance.
