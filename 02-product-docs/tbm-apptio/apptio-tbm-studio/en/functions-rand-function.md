---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Rand function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Rand function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/rand.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Rand function

*Generates a random decimal number between 0.0 (inclusive) and 1.0 (exclusive).*

## Syntax

```
Rand()
```

## Parameters

None

## Behavior

Each time the function is evaluated, it produces a new pseudo-random number. Returns a floating-point number greater than or equal to 0.0 and less than 1.0.

## Return type

Number

## Example

Rand()

- 0.354
- 0.515
- 0.034

Rand() * 100 : Generates a random percentage between 0 and 100.

Because this function returns a different result each time it is recalculated, results may vary across evaluations.
