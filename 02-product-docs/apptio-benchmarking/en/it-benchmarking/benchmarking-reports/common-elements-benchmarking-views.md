---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Common elements in Benchmarking views"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
source_path: "it-benchmarking/benchmarking-reports/common-elements-benchmarking-views.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Common elements in Benchmarking views

Once you understand the common pieces, every view gets easier.

**Filters and peer selection**   
Almost all Benchmarking views have filters or
segregated views for:

- Industry or sector
- Size band (usually revenue or headcount)
- Region or geography

You should always be able to fill in this sentence:   
“This chart compares us to
[industry], [region], [size band], for fiscal year [N].”

If you cannot, stop and fix the filters before you present anything.

**Benchmarks and positions**   
Benchmarks are usually shown as box plots:

- A central point or line for the median
- A band for the interquartile range (25th to 75th percentile)
- Sometimes whiskers or lines for minimum and maximum values
- A dashed line or special marker representing your organization

![Interactive Benchmarking box plot](../../resources/images/it%20benchmarking_images/interactive-benchmarking-box-plot.png)

  
Reading this:

- Median tells you “middle of the pack”
- The band tells you what “normal-ish” looks like
- Your marker tells you if you are low, typical, or high relative to peers

  
“High” is not automatically bad; it is just where you are.

**Drill and detail**  
Most Benchmark-enabled Costing reports support some version
of drilling:

- From total IT spend to spend by Resource Tower or Cost Pool
- From an outlier Resource Tower to Cost Pools, vendors, or services
- From a benchmark gap in Costing reports down to accounts or drivers

![Costing project’s Infrastructure Summary with drill to details for “Compute” Resource Tower.](../../resources/images/it%20benchmarking_images/drill-resourse-tower.png)

  
The general workflow is:

- Spot a gap in a benchmark view.
- Drill toward your internal data until you can see what drives it.
- Decide if it is a scope issue, a design choice, or an actual optimization opportunity.
