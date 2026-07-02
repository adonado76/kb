---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Depreciation Methods"
breadcrumb:
  - "Planning"
  - "Asset Planning"
source_path: "it-planning/planning/depreciation-method.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Depreciation Methods

Apptio Planning supports multiple depreciation methods to help you accurately model how
fixed asset costs are expensed over time. Depreciation converts a capital expense (CapEx) into
operational expense (OpEx) over the useful life of the asset.

You can select from the following supported methods:

- [Straight Line](#deprecationmethod__SL)
- [Straight Line Using Calendar Days](#deprecationmethod__slcud)
- [Double Declining](#deprecationmethod__dd)
- [Declining Balance Even Periods](#deprecationmethod__dbep)
- [Declining Balance Using Calendar Days](#deprecationmethod__dbucd)
- [Manual Depreciation](#deprecationmethod__md)

## Straight Line

Evenly spreads the asset’s cost over its useful life.

**Formula:**

**Depreciation Amount** = (Purchase Price × (1 – Residual Value)) ÷ Asset Life

**Asset Life** = Duration in months

**Residual Value %** = The rate of the original asset cost that is expected to remain at
the end of its useful life.

**Example:**

Asset Price = $40,000

Asset Life = 12 months

Residual Value %: 0

**Monthly Depreciation** = 40,000 × (1 – 0) ÷ 12 = **$3,333**

## Straight Line Using Calendar Days

Applies straight-line depreciation but allocates the expense proportionally based on the
number of calendar days in each month.

If depreciation begins mid-month or spans months with different day counts (e.g., January
vs. February), each month receives a pro-rated amount based on actual elapsed days rather
than an even monthly split.

This method is commonly used when accounting policy requires greater accuracy for partial
periods.

## Double Declining

The double-declining balance method is an accelerated depreciation technique that records
higher depreciation expenses during the early years of an asset's life. It calculates
depreciation by multiplying the asset's beginning book value by double the straight-line
depreciation rate. This method is often used for assets that depreciate quickly or to lower
tax liability in the early years.

**Formula:**

**Depreciation Amount** = 2 × (1 ÷ Asset Life) × Beginning Period Book Value

**Asset Life** = Duration in months

**Residual Value %** = The rate of the original asset cost that is expected to remain at
the end of its useful life. The double declining balance calculation does not consider the
residual value in the depreciation of each period however, if the book value will fall below
the residual value, the last period will be adjusted so that it ends at the residual value.

**Beginning Period Book Value**(calculated monthly) = Purchase Amount – Accumulated
Depreciation to date

**Example:**

Asset Price = $40,000

Asset Life = 12 months

Residual Value % = 0

- **P1** = 2 × (1 ÷ 12) × (40,000 – 0) = **$6,667**

- **P2** = 2 × (1 ÷ 12) × (40,000 – 6,667) = **$5,556**

- **P3** = 2 × (1 ÷ 12) × (40,000 – 6,667 – 5,556) = **$4,955**

- **Etc.**

**Important:**Double Declining method recalculates Beginning Book Value **at the
beginning of each period** — not yearly. If you want to model a traditional Double
Declining method, use **Declining Balance with a 200% Balance Rate instead.**

## Declining Balance Even Periods

Flexible accelerated depreciation method that uses a **Balance Rate** you define (e.g.,
150%, 200%).

**Formula:**

**Depreciation Amount** = Beginning Period Book Value × [Balance Rate × ( 1 ÷ Asset
Life)]

**Beginning Period Book Value** (calculated annually) = Purchase Price – Accumulated
Depreciation to date

**Asset Life** = Duration in months

**Residual Value %** = The rate of the original asset cost that is expected to remain at
the end of its useful life. The double declining balance calculation does not consider the
residual value in the depreciation of each period however, if the book value will fall below
the residual value, the last period will be adjusted so that it ends at the residual value.

**Balance Rate %** = The rate to depreciate the asset.

If using Declining Balance with **Balance Rate = 200%**, this equals Double Declining
method. This is the recommended way to model standard Double Declining in Apptio.

**Example:**

**Asset Price:** $40,000

**Asset Life:**36 months

**Balance Rate %:** 200%

**Residual Value %:** 0

- **P1 - P12** = 40,000 × 200% × (1 ÷ 36) = **$2,220 per month**

- **Year 1 = $26,667**

- **P13 - P24** = (40,000 – 26,667) × 200% × (1 ÷ 36) = **$741 per month**

- **Year 2 = $8,889**

- **P25 - P36** = (40,000 – 26,667 – 8,889) × 200% × (1 ÷ 36) = **$247 per month**

- **Year 3 = $2,963**

## Declining Balance Using Calendar Days

This method applies the Declining Balance depreciation formula to calculate the total
depreciation for the year, but then allocates that depreciation across periods
proportionally based on the number of calendar days in each month.

It maintains the accelerated depreciation pattern (higher expense early in the asset’s
life), while improving period accuracy by weighting each month according to its actual
number of days.

## Manual Depreciation

Allows users to directly enter depreciation amounts for each period, rather than relying on
system-calculated methods. This provides full flexibility to define exactly how costs should
be distributed across periods.
