---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Segregation of duties and recommended practices"
breadcrumb:
  - "Getting started"
  - "User Roles and Permissions"
  - "Segregation of duties and recommended practices"
source_path: "SSV8ML/boit/billing/getting-started/duty-segregation.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Segregation of duties and recommended practices

*When setting up roles and permissions, consider these practices:*

- Separate configuration from consumption Limit TBM Studio access to Admins, Analysts, and other personas who understand the impact of model changes. Keep Service or Product Owners, Senior Leaders, and Consumers in the front-end reports only.
- Restrict sensitive views Limit access to detailed cost and transfer-pricing views to roles that must see them. Use separate reports or filters for views that include legal entity tax, intercompany charges, or sensitive cost components.
- Use role-based patterns where possible Define standard permission sets that map to Admin, Analyst, Service or Product Owner, and Consumer roles. Avoid custom one-off permissions where a role-based pattern will work.
- Align with Finance and Security Involve Finance when defining who can see journal-level detail, internal revenue, or margin information. Align with the organization’s identity and access management policies for authentication and single sign-on.
