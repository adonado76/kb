---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Guide to Commitment Management FAQ"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Guide to Commitment Management"
source_path: "product/guide_to_commitment_management_faq.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Guide to Commitment Management FAQ

## Commitment Manager

## Commitment Portfolio

**What is the difference between units and counts?**

**Counts** refers to the number of instances in a reservation, while **Units** refers to
normalized instance hours. This is relevant for RIs that applied to multiple instance sizes within a
family. This also helps you decide on the overall size of an RI, so that a reservation of 5
instances of m4.large (Count of 5, Units of 20) not appear larger than a reservation of instances of
4 m4.16xlarge (Count of 4, Units of 512).

**Why does my savings decrease when I look at Adjusted cost?**

Custom pricing often shifts the savings from an RI to custom pricing. To use a simple example, if
an instance cost $1/hour and the reservation costs $0.80/hour, a fully-utilized reservation of 10
instances would provide $48 of savings per day (10 x 24 x $0.2).

If you have a custom pricing agreement that gives you 10% discount for compute instances, your
savings for this would effectively drop to $43.20 per day (10 x 24 x $0.18).

**Why does savings/utilization change when I select a view?**

The portfolio supports account group based views. However, when you select a view, filter to both
where a reservation is owned as well as where a reservation is applied. If your team purchases RIs
within a linked account and want to see how much of the RI was consumed by your team, you can do
that with a view.

To view RIs owned in a particular account, use the **Account** filter on the main page.

**In Azure reserved instances, does the savings rate percent and savings over term KPIs
incorporate custom Azure rates?**

If you have custom pricing calibrated in the application, you can also tease your savings net of
custom pricing discounts.

**My Commitment portfolio is missing commitments, where are they?**

Cloudability commitments can only see commitments that the user account can see. Using AWS as an
example, a consolidated billing parent account cannot see the activity of the child account that
occurred before it entered into the consolidated billing relationship. This means that the parent
account cannot see commitments belonging to the child that were purchased before the consolidated
billing relationship began.

The suggested workaround is to add an IAM credential for the child account to Cloudability, in
addition to the consolidated billing parent account. Cloudability Commitments will then be able to
see the commitments that were purchased by the child account. Cloudability will automatically
de-duplicate any overlapping data.

## Commitment Recommendations

- **The commit value in savings plan is on higher end when compared to RI for EC2. Do you recommend
  to buy both?**

  In Cloudability , It is possible that the commitment amount in a saving plan is higher than the
  Reserved instance for AWS EC2. The reserved instances provide a discount when you reserve a certain
  amount of computing power (measured per hour) for a one- or three-year term while savings plans
  provide a discount when you commit to spending a certain amount (measured in dollars per hour) for a
  one-or three-year period. The decision to purchase a resource or spend based commitment is up the
  FinOps leader in the organization. Eligible usage may be covered by multiple commitment types.
  Currently, we provide these recommendations in a vacuum from one another. For example, it is not
  recommended that all reserved instances and savings plans for AWS EC2 be purchased.
- **What is the best strategy to use commitments? What are best practices? Are you expecting to
  consider and act on all the recommendations at once?**

  The strategy chosen when using commitment-based discounts to save on cloud spend will vary
  depending on the organization, vendor, and commitment type. There is no universally best approach.
  Since commitments usually involve one- or three-year contracts, it is crucial to consider future
  plans carefully. Generally, it is advisable to make smaller, frequent purchases over time until the
  desired coverage percentage is achieved. Once this threshold is reached, additional commitments may
  be purchased as usage grows or as existing commitments expire. It is also important not to renew
  commitments if a decrease in usage is anticipated.

  In Cloudability's support for commitments, the commitment recommendations provide what
  commitments should be purchased to maximize net savings, given the selected usage range. Individual
  recommendations are provided for each permutation of the criteria necessary for each commitment type
  where coverage usage is detected. In affect, Cloudability Commitment Recommendations provide you the
  optimal commitment. Organizations should strive to this coverage level to achieve optimal savings,
  however, as best practices call for small incremental purchases, the optimal recommendation should
  rarely be acted upon directly.

## GCP Specific FAQ

**How far back can I go in historical usage for analysis?**

A maximum of 2 months: The entire previous months usage, up until the previous day of the current
month.

**What dimensions can I use to filter the usage for analysis?**

You can use any configured Cloudability dimension: Tags & Labels, Account Groups, or Business
Mappings. Some dimensions may not be available if the data variability is high – for example:
“server name”. Only dimensions with a low-moderate amount of variability will be available, for
example: “environment: production/staging”, “cost center: abc123”.

**How many dimensions can I use to filter my usage for analysis?**

You can select up to 10 Cloudability dimensions to apply to your usage.

**When will the selected dimensions be applied to my usage?**

Dimensions are applied when the next billing data ingestion occurs. It can take up to a maximum
of 24 hrs for the dimensions to be applied to your usage, and be available to be used as filters.
When GCP processing starts, it will take the currently configured preferences at that point in time,
and apply them.

**Can I change my selected dimensions multiple times?**

Yes, you can change the dimensions multiple times. When the billing data ingestion occurs, it
will take the currently configured dimensions and apply them to the data.

**Can different users have different dimensions configured for their usage?**

No, the dimensions are configured for the entire organization.

**How is the usage on the graphs displayed?**

The graphs show hourly data, with multiple hours being averaged into a single point if required
to fit into the graph.

**How is the default recommendation calculated?**

This is the propriety Cloudability algorithm which looks to maximize savings while balancing
risk.

**Are SUDs incorporated into the recommendation?**

Yes, if a resource received a SUD previously, the Cloudability recommendation savings will show
the increase from the SUD rate, not the on-demand rate.

**The SUD discount level changes throughout a month, what SUD discount level is used?**

The average of the entire previous months discount is used and applied to the modelled usage for
any resource that received a discount.

**How are** Cloudability **'s recommendations different from the GCP recommendations?**

There are 5 features that will result in different results from the native GCP recommendations:

1. **Included data:** Cloudability includes any resource running for any amount of time, it does
   not need to be running consistently for 30 days/1 mont
2. **Usage period:** selecting a specific usage period
3. **Filtering the data:** Cloudability allows you to remove usage from analysis at a very
   granular level
4. **SUDs:** Cloudability incorporates SUD discounts in the calculations if they were previously
   received
5. **Risk:** Cloudability users can analyze different commitment levels based on risk

**How are values in the console rounded** ?

Values are rounded to the closest whole number.

**Parent topic:** [Guide to Commitment Management](../product/guide_to_commitment_management.html)
