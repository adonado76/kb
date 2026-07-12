---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Permission Best Practices"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
  - "Permission Best Practices"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/permission-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Permission Best Practices

Permission Design Patterns

Pattern 1: Broad Access with RLS Filtering

- Set report permissions to Everyone
- Use RLS to filter sensitive data by user
- Simplifies permission management while maintaining data security

Pattern 2: Role-Segmented Reports

- Create separate reports for each audience
- Configure each report for specific roles
- Provides tailored experiences but increases maintenance

Pattern 3: Single Report with Component Visibility

- Create one report serving multiple audiences
- Use component visibility to show/hide elements by role
- Reduces report count while providing role-appropriate views

Pattern 4: Collection-Based Organization

- Group reports by audience in collections
- Configure collection-level permissions
- Reports inherit from collection, reducing individual configuration

Least Privilege Principle

Apply the principle of least privilege when configuring report permissions:

1. Start restrictive: Begin with limited access and expand as needed
1. Use specific roles: Avoid granting Everyone access unless truly appropriate
1. Layer security: Combine report permissions with RLS for sensitive data
1. Regular review: Periodically audit who has access to sensitive reports
