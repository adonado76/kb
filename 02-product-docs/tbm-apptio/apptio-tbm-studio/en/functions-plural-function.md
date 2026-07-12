---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Plural function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Plural function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/plural.html"
images:
  - "03-media/apptio-tbm-studio/stu689.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Plural function

*eturns the plural form of a given singular noun based on a count. This is useful for dynamically generating grammatically correct labels or display strings.*

## Syntax

Plural(noun,count)

## Arguments

noun : The singular form of a noun to pluralize (e.g., "server", "data center"). Compound nouns and multi-word phrases are supported. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

count : A numeric expression used to determine whether to pluralize the noun. If the value is greater than 1, the noun is pluralized. If omitted, the noun is always pluralized. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Optional

## Return type

String

## Example

- Plural("server", 2) : Returns "servers" because the count is greater than one.
- Plural("network", {Network Count}) : Returns "network" or "networks" based on the value in {NetworkCount}.
- Plural("operating system") : Returns "operating systems" since no count is specified (always plural).

- This function does not automatically convert output to lowercase. To do so, wrap it in the Lower function (e.g., Lower(Plural(...))).
- Best used in label-type columns or formatted output expressions where grammatical accuracy matters.
- Irregular nouns are not supported—standard pluralization rules apply.
