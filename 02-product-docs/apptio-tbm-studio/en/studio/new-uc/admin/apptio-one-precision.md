---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "ApptioOne Precision"
breadcrumb:
  - "TBM Studio"
  - "Administration"
source_path: "studio/new-uc/admin/apptio-one-precision.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioOne Precision

Apptio uses the [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754 "(Opens in a new tab or window)") specification for [double precision floating point](https://en.wikipedia.org/wiki/Double-precision_floating-point_format "(Opens in a new tab or window)") numbers to represent numeric values.

This standard provides approximately 17 - log10(N) digits of precision (where N is the number of
values being summed) for most operations, and as little as 15 digits of precision for certain other
operations. As such while Apptio retains and will display numbers beyond 15 digits, these numbers
may change between builds or between calculations on the same build / configuration / data.

When numbers are rounded, Apptio uses the [round half away from zero](https://en.wikipedia.org/wiki/Rounding#Rounding_half_away_from_zero "(Opens in a new tab or window)") tie-breaking rule (a.k.a. "commercial
rounding").

When Apptio sums values it uses the [Kahan
Summation algorithm](https://en.wikipedia.org/wiki/Kahan_summation_algorithm "(Opens in a new tab or window)") to efficiently provide the most accurate sum possible.

It should also be noted that Apptio adds a fudge amount (0.00000001) to all numbers displayed via
Round() or NumberFormat(). This is done to control rounding of floating point numbers.

As such numbers in Apptio are accurate to the lesser of:

- 15 significant digits (digits before and after the decimal point) or
- 7 decimal places (digits after the decimal point)

Apptio by default displays numbers with 3 decimals.
