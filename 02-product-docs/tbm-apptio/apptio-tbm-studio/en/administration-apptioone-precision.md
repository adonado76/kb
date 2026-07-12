---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "ApptioOne Precision"
breadcrumb:
  - "Administration"
  - "ApptioOne Precision"
source_path: "SSWRJM/studio/new-uc/admin/apptio-one-precision.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# ApptioOne Precision

Apptio uses the IEEE 754 specification for double precision floating point numbers to represent numeric values.

This standard provides approximately 17 - log10(N) digits of precision (where N is the number of values being summed) for most operations, and as little as 15 digits of precision for certain other operations. As such while Apptio retains and will display numbers beyond 15 digits, these numbers may change between builds or between calculations on the same build / configuration / data.

When numbers are rounded, Apptio uses the round half away from zero tie-breaking rule (a.k.a. "commercial rounding").

When Apptio sums values it uses the Kahan Summation algorithm to efficiently provide the most accurate sum possible.

It should also be noted that Apptio adds a fudge amount (0.00000001) to all numbers displayed via Round() or NumberFormat(). This is done to control rounding of floating point numbers.

- 15 significant digits (digits before and after the decimal point) or
- 7 decimal places (digits after the decimal point)

Apptio by default displays numbers with 3 decimals.
