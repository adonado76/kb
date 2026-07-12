---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Formulas Quick Reference"
breadcrumb:
  - "Reference"
  - "Data Studio Reference"
  - "Formulas Quick Reference"
source_path: "SSWRJM/studio/new-uc/reference/formulas-quick-reference.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Formulas Quick Reference

For complete formula and function documentation, see Section 5.4 Formulas & Functions. Adding Transform Steps

Formula Syntax:

- Begin with = (required)
- Reference columns using curly brackets: {Column Name}
- Use standard operators: +, -, *, /

Common Formula Patterns:

| Pattern | Formula Example |
| --- | --- |
| Pattern | Formula Example |
| Concatenate | ="prefix-"&{Column} |
| Conditional | =If({Type}="A", {Value}*2, {Value}) |
| Lookup | =Lookup({Key}, Table, {SourceKey}, {ReturnColumn}) |
| Number format | =NumberFormat({Column},"#,###") |
| Type conversion (Label to Numeric) | =Value({Column}) |
| Type conversion (Numeric to Label) | =NumberFormat({Column},"#,###") |
| Date format | =DateFormat({Column},"yyyy-MM-dd") |
