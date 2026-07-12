---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "getting_started_with_tbm_studio"
title: "ApptioOne Precision"
breadcrumb: []
source_path: "getting_started_with_tbm_studio/apptio-one-precision.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioOne Precision

Apptio uses the [https://en.wikipedia.org/wiki/IEEE\_754](https://en.wikipedia.org/wiki/IEEE_754 "(Opens in a new tab or window)") specification for [https://en.wikipedia.org/wiki/Double-precision\_floating-point\_format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format "(Opens in a new tab or window)") numbers to represent numeric values.

This standard provides around 17 - log10(N) digits of precision (where N is the number of values
that are summed) for most operations, and 15 digits of precision for other operations. While Apptio
retains and displays numbers beyond 15 digits, these numbers can change between builds or
calculations on the same build, configuration, or data.

When numbers are rounded, Apptio uses the [round half to even](https://en.wikipedia.org/wiki/Rounding#Round_half_to_even "(Opens in a new tab or window)") tie-breaking rule (also known as "bankers rounding") which is the default
for IEEE 754.

When Apptio sums values it uses the [Kahan
Summation algorithm](https://en.wikipedia.org/wiki/Kahan_summation_algorithm "(Opens in a new tab or window)") to efficiently provide the most accurate sum possible.

Note that Apptio adds a fudge amount (0.00000001) to all numbers displayed as a Round() or
NumberFormat(), to control rounding of floating point numbers.

As such numbers in Apptio are accurate to the lesser of:

- 15 significant digits (digits before and after the decimal point) or
- 7 decimal places (digits after the decimal point)

Apptio by default displays numbers with 3 decimals.

## Additional Information

See Apptio's help documentation about [About weighting and negative numbers](../model_studio/about-weighting-and-negative-numbers.html "◆ Applies to: TBM Studio 11.8.3.1 and later; TBM Studio 12.0 and later. The purpose of a weighting is to allocate the source number where the sum is the same in the target.").
