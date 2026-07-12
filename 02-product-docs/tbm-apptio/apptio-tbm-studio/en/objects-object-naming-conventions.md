---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Object Naming Conventions"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Model Objects"
  - "Object Naming Conventions"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/object-naming-convention.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Object Naming Conventions

Consistent naming improves model maintainability and user comprehension.

Recommended Naming Patterns

| Pattern | Format | Example |
| --- | --- | --- |
| Pattern | Format | Example |
| Cost Sources | [Type] [Period/Qualifier] | Cost Source Actuals, Cost Source Budget |
| Cost Pools | [Category] [Qualifier] | Labor Actuals, Facilities Actuals, Fixed Assets |
| Infrastructure | [Resource Type] | Servers, Storage, Network, Data Centers |
| Services | [Service Category] | Technology Services, Business Applications |
| Consumers | [Consumer Type] | Business Units, Departments, Customers |

Naming Best Practices

- Use descriptive names that indicate the object’s role in the model
- Include “Actuals,” “Budget,” or “Forecast” qualifier when objects are metric-specific
- Avoid special characters that may cause issues in formulas or reports
- Keep names concise while remaining meaningful
- Document object purpose in the Description field

Note: Object names appear in model reports and are visible to end users. Choose names that make sense to your stakeholders.

Common Issues

| Issue | Cause | Resolution |
| --- | --- | --- |
| Issue | Cause | Resolution |
| Model object not visible | Model step not added to table | Add Model step to table transform |
| Cannot create allocation | Tables not checked out | Check out both source and target |
| No data in model object | Transform errors or missing period | Verify Data Studio transform succeeds |
| Duplicate identifier values | Non-unique identifier configuration | Add columns to identifier for uniqueness |

→ See Common Issues for detailed troubleshooting
