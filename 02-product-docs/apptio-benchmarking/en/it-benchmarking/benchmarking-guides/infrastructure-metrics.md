---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Interactive Benchmarking - Infrastructure Benchmark Metrics"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/infrastructure-metrics.html"
images:
  - "resources/images/it_benchmarking_images/double_image_adjusters_fig4.jpg"
  - "resources/images/it_benchmarking_images/influence_of_industry_adjuster_fig7.jpg"
  - "resources/images/it_benchmarking_images/influence_of_region_adjuster_fig8.jpg"
  - "resources/images/it_benchmarking_images/influence_of_scal_adjuster_fig9.jpg"
  - "resources/images/it_benchmarking_images/mainframe_mips_unit_cost_fig3.jpg"
  - "resources/images/it_benchmarking_images/scale_region_industry_influencers_fig2.jpg"
  - "resources/images/it_benchmarking_images/server_unit_as_box_plot_fig1.jpg"
  - "resources/images/it_benchmarking_images/single_point_comparison_fig6.jpg"
  - "resources/images/it_benchmarking_images/unit_cost_by_cost_pool_fig5.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Interactive Benchmarking - Infrastructure Benchmark Metrics

♦ Applies to: Interactive Benchmarking

This article describes the Interactive Benchmarking methodology as it applies to Infrastructure
Benchmarks and recommends how to leverage the features in Interactive Benchmarking. The focus of
this article is to explain how the current methodology differs from the methodology used in
Benchmarking v1.

**Background**

Prior to Interactive Benchmarking, the top two requests from Apptio customers were for:

- Additional details on benchmark data, such as sample size, top-quartile, and median, rather
  than a single data point
- A better understanding of benchmark data drivers

Based on this feedback, Apptio worked with benchmark providers to improve benchmark data
fidelity. With the release of Apptio Interactive Benchmarking, the following changes were
incorporated:

- Benchmark data in the form of a distribution, with sample size, shown by quartiles, using a
  standard statistical box plot representation.
- Key influencers identified for each metric type. For example, the Industry and Infrastructure
  metrics have their own characteristics and therefore their own unique influencers.
- Improved fidelity of scale using a power function for Infrastructure metrics.

In addition, Interactive Benchmarking provides three levels of metrics with the following levels
of granularity:

- **Industry Benchmarks**  – Industry benchmark metrics provide five high-level
  metrics for organization financials, such as “IT Spend as a % of Org Revenue,” that help you compare
  your overall IT performance and efficiency with peers.
- **IT OpEx Benchmarks**  - The IT OpEx benchmark metrics provide a high-level
  directional guidance on your organization’s OpEx characteristics.
- **Infrastructure Benchmarks**  – Infrastructure benchmark metrics include peer
  benchmark metrics at the most granular level, which allow you to compare your sub-tower unit costs
  and FTE efficiencies with peers.

Interactive Benchmarking provides distribution data with adjusters for all three levels of
metrics. The primary driver for Industry metrics is industry, with secondary influencers like region
and revenue. Infrastructure metrics, on the other hand, are significantly impacted by economies of
scale. Region and industry have a secondary influence. For more information on these metrics, see
the  [Benchmarking Knowledge Base](https://community.apptio.com/community/apptio/product-central/it-benchmarking "(Opens in a new tab or window)")  .

**Comparison**

The primary differences between Infrastructure metrics in Benchmarking v1 (2016) and
Infrastructure metrics in Interactive Benchmarking are:

- **Box plot-based distribution**  – In Interactive Benchmarking, sub-tower unit
  costs and FTE efficiency metrics are presented as full distribution data, in the form of box plots
  showing median, upper quartile, lower quartile, and mid-quartile benchmark data with information on
  sample size and the benchmark data provider (Figure 1).In contrast, Benchmarking v1 presents
  infrastructure benchmarks as single point data with no visibility into the sample distribution.

  ![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/server_unit_as_box_plot_fig1.jpg)

  Figure 1: Server unit cost benchmark data as a box plot
- **Additional adjusters**  – Scale, region, and industry adjusters are available
  in Interactive Benchmarking.
  - Scale adjusters enable you to analyze the influence of economy of scale on unit cost and FTE
    efficiency benchmark numbers.
  - Region and industry adjusters allow you to pick appropriate region and industry peer groups to
    understand their impact and compare your unit cost and FTE efficiency numbers.

    Only one of these
    adjusters can be selected at a time (Figure 2).

  In contrast, Benchmarking v1 pre-applied scale, region, and industry adjusters and presented
  them as a single benchmark metric. The actual extent of their impact was not exposed in the product.

  ![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/scale_region_industry_influencers_fig2.jpg)

  Figure 2: Scale, region, and industry adjusters for Infrastructure Benchmarks
- **Improved scale adjuster fidelity**  - In Interactive Benchmarking, scale
  adjusters are computed using a power function to improve fidelity and accuracy. The improved
  fidelity of scale for Mainframe MIPS unit cost is shown in Figure 3, in orange. Benchmarking v1,
  shown in blue, has a low fidelity step function.

  ![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/mainframe_mips_unit_cost_fig3.jpg)

  Figure 3: Scale adjuster

**Using Interactive Benchmarking features**

This section describes how to use Interactive Benchmarking, which emphasizes the comparison of
actuals against the entire distribution using the box plot. Adjusters that influence the costs are
scale, region, and industry (Figure 4).

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/double_image_adjusters_fig4.jpg)

Figure 4: Scale, region, and industry adjusters on the left, box plot on the right

**Compare actual costs to benchmark data**

Once you have filled out the Volume Input and  **Total annual cost**  fields,
you can evaluate how your actual unit costs compare against the distribution by using the box plot.
Compare your actuals against the median and see whether they fall in the inter-quartile range or are
an outlier. Then compare your actuals by cost driver break down and against the corresponding
benchmark numbers, as shown below. This calls out any significant difference in cost
characteristics.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/unit_cost_by_cost_pool_fig5.jpg)

Figure 5: Unit cost by Cost Pool drivers

**Single-point comparison**

For a single-point comparison, we recommend using the median as the basis. The table at the
bottom of the page (Figure 6) shows the difference between your actuals and the median. While
reducing comparisons to a single point provides an easy way to track data points, it distracts the
view from a peer distribution.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/single_point_comparison_fig6.jpg)

Figure 6: Single-point comparison of unit cost with benchmark median

**Impact of influencers on the metrics**

To understand the impact of scale, region, industry, click the charts on the left to see their
influence on the box plot.

Figure 7 and Figure 8 show industry and region, respectively. To see the impact of industry or
region on the benchmark metric, click one of industry groups or regions.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/influence_of_industry_adjuster_fig7.jpg)

Figure 7: Influence of the industry adjuster on unit cost benchmark data

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/influence_of_region_adjuster_fig8.jpg)

Figure 8: Influence of the region adjuster on unit cost benchmark data

**Impact of economies of scale**

The scale chart in Figure 9 shows economies of scale. At lower volumes, the benchmark unit costs
have high variance. As volume numbers increase, benchmark unit costs decline and stabilize after
reaching a certain threshold. This indicates that, due to economies of scale, unit costs are
significantly higher at low volumes. Click a scale influencer chart to see the scale impact in a box
plot context.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/influence_of_scal_adjuster_fig9.jpg)

*Figure 9: Influence of the scale adjuster on unit cost benchmark data*

**Conclusion**

Interactive Benchmarking has enhanced capabilities that provide richer and more accurate
benchmark data. To learn more about benchmark data or functionalities in Interactive Benchmarking,
go to the  [Benchmarking Knowledge Base](https://community.apptio.com/community/apptio/product-central/it-benchmarking "(Opens in a new tab or window)")  .
