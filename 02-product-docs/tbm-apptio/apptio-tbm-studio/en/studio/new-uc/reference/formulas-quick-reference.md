---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Formulas Quick Reference"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Data Studio Reference"
source_path: "studio/new-uc/reference/formulas-quick-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Formulas Quick Reference

For complete formula and function documentation, see Section 5.4 Formulas & Functions. Adding
Transform Steps

**Formula Syntax:**

- Begin with = (required)
- Reference columns using curly brackets: {Column Name}
- Use standard operators: +, -, \*, /

**Common Formula Patterns:**

|  |  |
| --- | --- |
| **Pattern** | **Formula Example** |
| Concatenate | ="prefix-"&{Column} |
| Conditional | =If({Type}="A", {Value}\*2, {Value}) |
| Lookup | =Lookup({Key}, Table, {SourceKey}, {ReturnColumn}) |
| Number format | =NumberFormat({Column},"#,###") |
| Type conversion (Label to Numeric) | =Value({Column}) |
| Type conversion (Numeric to Label) | =NumberFormat({Column},"#,###") |
| Date format | =DateFormat({Column},"yyyy-MM-dd") |

**Parent topic:** [Data Studio Reference](../../../studio/new-uc/reference/data-studio-reference.html)
