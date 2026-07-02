---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Resource Recommendations"
breadcrumb:
  - "Cloudability Premium"
  - "Governance"
source_path: "admin/governance-resource-recommendations.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Resource Recommendations

Governance provides recommendations for new EC2 and RDS resources being deployed when a similar
configuration (matching CPU and Memory requirements) is available at a lower cost. Recommendations
are posted as comments on the pull request (PR).

**If Governance does not identify a more cost-effective resource, no recommendation will be
posted.**

**Example:** Upgrade RDS instance from db.m5.8xlarge to db.m6g.8xlarge to save costs while
maintaining performance.
