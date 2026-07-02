---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Explore costs with Benchmarking"
breadcrumb: []
source_path: "it-benchmarking/start-here/explore-costs.html"
images:
  - "resources/images/it_benchmarking_images/explore-costs-1.jpg"
  - "resources/images/it_benchmarking_images/explore-costs-2.jpg"
  - "resources/images/it_benchmarking_images/explore-costs-3.jpg"
  - "resources/images/it_benchmarking_images/explore-costs-4.jpg"
  - "resources/images/it_benchmarking_images/explore-costs-5.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Explore costs with Benchmarking

♦ Applies to projects running Benchmarking and ATUM v2 or higher.

**Introduction**

With Benchmarking , you can explore an organization's costs, and how these costs compare to a
peer benchmark. If a cost is above or below the benchmark, how does one explore the cost drivers and
identify the cost inputs? Benchmarking provides several ways to explore and identify the cost
drivers in a defensible manner.

**Review and trace IT costs**

To review and trace IT costs in Cost Transparency when comparing against a benchmark, follow
these steps:

1. Compare the organizational cost to a benchmark to identify values that are above or below the
   benchmark.
2. Select cost pools to narrow the area of focus.
3. Select details and inspect trend for significant changes.
4. Review transaction-level detail.

**1. Compare organizational cost to benchmark**

The first step is to compare organizational costs to a benchmark to identify those costs that
are above or below the benchmark. This will help to determine where to focus your time and effort.

Starting with compute in the following example, we can see that the unit cost is above the
benchmark for servers and significantly below the benchmark for Unix. Frequently, when one sub-tower
is below and another is higher within an IT Resource Tower, it suggests that an allocation strategy
might be the root cause or some form of bundled charge that impacts multiple sub-towers is only
being sent to one sub-tower instead of being allocated to both.

![apex](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/explore-costs-1.jpg)

**2. Select cost pools to narrow the area of focus**

Now that we have identified the sub-tower(s) for additional analysis, the next step is to select
the composition view to see which cost pool(s) are outside of the typical benchmark range. The
composition view is available directly from the Compute benchmarking report, or by selecting the IT
Resource Sub-Tower to navigate to the detailed sub-tower benchmarking view. For this example, the
click path is to select the IT Resource Sub-Tower.

In this example, within the cost pool distribution, there are two areas that have a larger delta
to the benchmark. We will investigate hardware and software next.

![apex](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/explore-costs-2.jpg)

**3. Select details and inspect trend for significant changes**

The next step is to examine trended data in the detail view to determine if there are any
significant changes in the trailing months that would impact cost. A sudden change in a given month
would indicate a significant allocation or data change that might adversely impact the unit cost
calculation. In this example, a review of the data trended over time shows a decline in unit cost,
but no large changes.

![apex](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/explore-costs-3.jpg)

Selecting the transaction view provides a month-over-month detail of costs by cost pool with the
ability to select and drill down into the transaction level detail of that cost pool or sub-cost
pool.

![apex](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/explore-costs-4.jpg)

**4. Review transaction-level detail**

Because the hardware and software cost pools show the largest delta from the benchmark,
selecting either of these areas will provide insight into the specific cost drivers.

![apex](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/explore-costs-5.jpg)

By examining the hardware costs, the larger costs appear to be a server maintenance and repair
line item and depreciation. This indicates a need for some additional analysis. Does the server
maintenance and repair line item represent only costs associated with Windows or Linux servers, or
does it include additional services or services related to other resource towers? The second largest
cost is depreciation. Similarly, does this deprecation cost incorporate just server cost, or does it
include other depreciation costs, such as desktops, network equipment, or other items?

**Conclusion**

By becoming armed with a detailed analysis and eliminating significant changes to the allocation
strategy, the user can review the line item detail with data owners to trace, identify, and
understand underlying cost drivers. This amount of detail ensures a level of confidence in the cost
data and also provides defensible, benchmarked costs.
