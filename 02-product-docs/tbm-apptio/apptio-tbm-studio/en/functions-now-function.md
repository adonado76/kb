---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Now function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Now function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/now.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Now function

The Now( ) function returns the current date and time as a UNIX time stamp based on the server time. The time is based on the time the function is executed. The result is cached on disk, across restarts, etc. It is updated only when a full recalculation is performed.

## Syntax

Now()

## Behavior

- Returns the server’s current date and time as a UNIX timestamp when the function is evaluated.
- Used in formulas that require the current system date, such as calculating time elapsed or filtering by recent activity.

## Parameters

None

## Return type

Date

## Example

- Returns the current system timestamp, such as for comparisons with another date field: Now()
- Calculates the number of periods that have passed since the value in the {Start Date} column.: Months(Now()) - Months({Start Date})

- This function does not accept any arguments.
- The Now function cannot be used in transform tables because it will not update. If a Now function was added to a Release 8 transform table, it must be removed.
