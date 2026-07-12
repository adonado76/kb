---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Amortization Methods"
breadcrumb:
  - "Planning"
  - "Contract Planning"
source_path: "it-planning/planning/ammortization-method.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Amortization Methods

Contract amortization is the process of distributing the cost of a contract across
multiple periods.

## Overview

Apptio Planning supports five amortization methods, each with specific use cases for handling
contract costs:

1. [Straight Line Even Periods](#amormeth__sleven)
2. [Straight Line Using Calendar Days](#amormeth__slcal)
3. [Straight Line Prorate First and Last](#amormeth__slfirst)
4. [Straight Line By Duration](#amormeth__sldur)
5. [Manual Amortization](#amormeth__slamor)

Apptio Planning also supports **contract extensions**, allowing costs to continue beyond
the original contract end date. Extensions can apply new rates and optionally compound over
time.

The use cases for each amortization Method is described below:

## 1. Straight Line Even Periods

Distributes the total contract cost evenly across all periods, regardless of the number of
days in each period. A period is considered full even if the contract only covers a single
day within it.

**Example:**

Contract Start Date: Jan 15, 2025

Contract End Date: June 15, 2025

Duration: 6 months

Amount: $6,000

**Without Extension:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 |  |  |  |  |  |  |

Jan-Jun = $6000 / 6 months = $1000

**With Extension through the end of the year:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 | $1,000 |

## 2. Straight Line Using Calendar Days

Distributes cost proportionally to the number of days in each month during the contract.
Periods with more days receive a larger share, with both the start and end dates counted.

**Example:**

Contract Start Date: Jan 15, 2025

Contract End Date: June 15, 2025

Duration: 152 days

Amount: $6,000

**Without Extension:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $671 | $1,105 | $1,224 | $1,184 | $1,224 | $592 |  |  |  |  |  |  |

Jan = $6000 \* 17 days / 152 days = $671

Feb = $6000 \* 28 days / 152 days = $1,105

Mar = $6000 \* 31 days / 152 days = $1,224

Apr = $6000 \* 30 days / 152 days = $1,184

May = $6000 \* 31 days / 152 days = $1,224

Jun = $6000 \* 15 days / 152 days = $592

**With Extension through the end of the year:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $671 | $1,105 | $1,224 | $1,184 | $1,224 | $1,184 | $1,224 | $1,224 | $1,184 | $1,224 | $1,184 | $1,224 |

Jan = $6000 \* 17 days / 152 days = $671

Feb = $6000 \* 28 days / 152 days = $1,105

Mar = $6000 \* 31 days / 152 days = $1,224

Apr = $6000 \* 30 days / 152 days = $1,184

May = $6000 \* 31 days / 152 days = $1,224

Jun = ($6000 \* 15 days / 152 days) + ($6000 \* 15 days / 152 days) = $1,184

Jul = $6000 \* 31 days / 152 days = $1,224

Aug = $6000 \* 31 days / 152 days = $1,224

Sep = $6000 \* 30 days / 152 days = $1,184

Oct = $6000 \* 31 days / 152 days = $1,224

Nov = $6000 \* 30 days / 152 days = $1,184

Dec = $6000 \* 31 days / 152 days = $1,224

## 3. Straight Line Prorate First and Last

Prorates the first and last periods of a contract by the number of days, then evenly
distributes the remaining cost across middle periods.

**Example:**

Contract Start Date: Jan 15, 2025

Contract End Date: June 15, 2025

Duration: 152 days

Amount: $6,000

**Without Extension:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $671 | $1,184 | $1,184 | $1,184 | $1,184 | $592 |  |  |  |  |  |  |

Jan = $6000 \* 17 days / 152 days = $671

Feb = $6000 - $671 - $592 / 4 months = $1,184

Mar = $6000 - $671 - $592 / 4 months = $1,184

Apr = $6000 - $671 - $592 / 4 months = $1,184

May = $6000 - $671 - $592 / 4 months = $1,184

Jun = $6000 \* 15 days / 152 days = $592

**With Extension through the end of the year:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $671 | $1,184 | $1,184 | $1,184 | $1,184 | $1,184 | $1,214 | $1,214 | $1,214 | $1,214 | $1,184 | $1,194 |

Original Contract: Jan 15 – June 15, 2025

First Extension: Jun 16 – Nov 15, 2025

Second Extension: Nov 16, 2025 – April 16, 2026

Jan = $6000 \* 17 days / 152 days = $671

Feb = $6000 - $671 - $592 / 4 months = $1,184

Mar = $6000 - $671 - $592 / 4 months = $1,184

Apr = $6000 - $671 - $592 / 4 months = $1,184

May = $6000 - $671 - $592 / 4 months = $1,184

Jun = ($6000 \* 15 days / 152 days) + ($6000 \* 15 days / 152 days) = $1,184

Jul = $6000 - $671 - $592 / 4 months = $1,184

Aug = $6000 - $671 - $592 / 4 months = $1,184

Sep = $6000 - $671 - $592 / 4 months = $1,184

Oct = $6000 - $671 - $592 / 4 months = $1,184

Nov = ($6000 \* 15 days / 152 days) + ($6000 \* 15 days / 152 days) = $1,184

Dec = $6000 - $592 - $631 / 4 months = $1,194

## 4. Straight Line By Duration

Checks whether the contract start and end dates fully cover the periods they fall in. If
both are complete periods, the cost is divided evenly across all periods. If the start or
end date does not cover the final period fully, the last period is assigned 0, and the cost
is distributed evenly across the remaining periods.

**Example:**

Contract Start Date: Jan 15, 2025

Contract End Date: June 15, 2025

Duration: 152 days = 5 months

Amount: $6,000

**Without Extension:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $1,200 | $1,200 | $1,200 | $1,200 | $1,200 |  |  |  |  |  |  |  |

Jan-May = $6000 / 5 months = $1,200

**With Extension through the end of the year:**

|  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Jan** | **Feb** | **Mar** | **Apr** | **May** | **Jun** | **Jul** | **Aug** | **Sep** | **Oct** | **Nov** | **Dec** |
| $1,200 | $1,200 | $1,200 | $1,200 | $1,200 | $1,200 | $1,200 | $1,200 | $1,200 | $1,200 | $1,200 | $1,200 |

Jan-Dec = $6000 / 5 months = $1,200

## 5. Manual Amortization

Allows users to directly enter amortization amounts for each period, rather than relying on
system-calculated methods. This provides full flexibility to define exactly how costs should
be distributed across periods.

If **Auto-Update Contract Total** is enabled in the Company Profile, the Amount column
will automatically sum the total based on the amortization amounts entered for each period.
