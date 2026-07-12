---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "CapFirstLetter function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "CapFirstLetter function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/capfirstletter.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# CapFirstLetter function

*Capitalizes the first letter of each word in the string argument, and makes all other letters lowercase.*

## Syntax

CapFirstLetter(text)

## Parameters

text : A string value or an expression that evaluates to a string. This can include static text, column references, or other string-producing formulas. Optional

## Behavior

- Each word in the input string will have its first character converted to uppercase.
- All other characters in each word will be converted to lowercase.
- Words are typically separated by spaces or punctuation.

## Return type

String

## Example

- CapFirstLetter("hello world") : Returns "Hello World"
- CapFirstLetter(User Name) : Capitalizes the first letter of each word in the UserName field.
- CapFirstLetter("tHiS is a tEsT") : Returns "This Is A Test".
