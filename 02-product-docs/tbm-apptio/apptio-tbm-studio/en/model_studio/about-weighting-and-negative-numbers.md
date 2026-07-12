---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "model_studio"
title: "About weighting and negative numbers"
breadcrumb: []
source_path: "model_studio/about-weighting-and-negative-numbers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# About weighting and negative numbers

◆ Applies to: TBM Studio 11.8.3.1 and later; TBM Studio 12.0 and later. The purpose of a
weighting is to allocate the source number where the sum is the same in the
target.

Weighting by negative numbers can result in unexpected outcomes. In Apptio TBM Studio, version
12, Apptio sets defaults to not allocate when negative weightings are in use. The reasons for
setting this default are described in this article, along with examples of scenarios where it might
be legitimate to weight by negative values, the risks inherent in activating this capability, and
ways to address these allocations safely.

## Why negative weighting is not on by default

When an allocation is created that attempts to weight by a set of values, which includes negative
numbers, several issues can occur. We discuss a few of the common issues here and we emphasize the
importance of understanding the risks.

For your reference, the spreadsheet used to support these examples is attached at the end of this
article in the ATTACHMENTS section.

## Example

First, to accentuate how things can go wrong in a highly visual way, suppose that you have an
allocation that weights by positive and negative numbers, but where one of the weighting values is
small relative to the others. In this example, $100 is allocated to three rows in the target, but
with one large positive, one large negative, and one small positive weighting. Notice the extreme
results in the receiving rows in the following table.

![](../../resources/images/studio_images/studioimages/studio_diagram_net%20positive%20weighting%20with%20extremes.png)

Because division by zero is a logical impossibility, [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754 "(Opens in a new tab or window)")
(Standard for Floating-Point Arithmetic) defines limits for the representation of zeros, which are
effectively tiny positive or negative numbers. Apptio software, like any software, adheres to this
principle, and therefore, the tiny positive number in this example is there even when Apptio's UI
might show a value of 0. Thus, with negative weightings activated, it's possible to see a sudden
explosion of values in downstream objects being allocated to.

## More common examples

In the following weighting tables, we see three examples: a net positive example, a net zero
example, and a net negative example. In each example, notice that values in the target, while
summing to the original value, create the inflation or deflation of value in the individual target
rows.

![](../../resources/images/studio_images/studioimages/studio_weighted%20value_examples.png)

## An insidious example

The following weighting table is another net positive example but one that is subtle, and
therefore, might go unnoticed. In this example, the net value of the target rows isn't very
different than in a larger set of allocations where it couldn't be missed. In this case, the values
in downstream objects might be subtly skewed in a way that yields numbers that are inaccurate.

![](../../resources/images/studio_images/studioimages/studio_diagram_net%20positive%20weighting.png)

## Situations that may call for negative weightings

Debit/credit scenarios
:   One common situation is where there are debits and credits in a general ledger or invoice. For
    example, a vendor's invoice might include both credits and debits to an account, such as in cloud
    services invoices. When this occurs, you may want to weight by negative numbers (credits).

Re-class of labor hours
:   Another situation where negative weightings are appropriate is the reclassification of labor
    hours. For example, in one month, someone submits time against Project A, then later, they realize
    that they intended to submit time against Project B instead. So, next month, they "credit" hours to
    Project A by submitting a negative number.

## Options for negative weightings

Use negative weightings selectively with a formula
:   The following formula can be used as part of an advanced formulaic allocation to selectively
    enable negative weightings. Notice that this does not prevent the possibility of issues like those
    described earlier in this article, it simply limits your exposure to them. Using a formula is
    preferred to enabling negative allocations for the entire environment because it mitigates the risk
    of unexpected results occurring where we do not anticipate needing negative
    weightings.

    ```
    =SOURCE *
            ({Table.Weighting}/~{Table.Weighting})
    ```

    Where the following applies to the set
    of rows that are associated by way of a Data Relationship (v12) or key (r11).

    - SOURCE is the source value that is being allocated via the
      relationship.
    - ~ is the rollup operator that sums the values in the weighting column for
      the given relationship.
    - The Table.Column (or metric) should always be identical in the numerator
      and denominator of the formula. Otherwise, you are not creating a valid ratio.

The main value of using this formula is to allow you to selectively enable negative weightings
for a specific allocation. This helps insulate you from the risks outlined at the beginning of this
article.

## Segregate negative source values and weight by absolute values

Another strategy for dealing with negative values is to segregate them in the source and use the
absolute value to weight. In the following example of an invoice with credits, the total (including
the credits) is installed in the General Ledger as a single line item with the sum of $100. It's
then allocated to the Vendors object (to support out-of-the-box reporting) weighting by the values
in the invoice. Because the invoice includes credits, we get incorrect numbers in the target.

![](../../resources/images/studio_images/studioimages/studio_diagram_cost%20line%20item%20to%20vendors.png)

If instead we segregate the credits in the General Ledger/cost source and insure that the data
relationship/key preserves the segregation, we can then use the absolute value of the invoice
including credits:

![](../../resources/images/studio_images/studioimages/studio_disagram_first%20gl%20line%20item.png)

This results in accurate numbers in the target.

## Example 1: A data issue

In this section, we provide a simple, real-world scenario wherein a negative weighting prevents
an allocation. This is also an example of a situation where negative weighting was not intentional.
In this case, a formula based on data flowing into the system went awry and created a couple of
negative values unintentionally.

Here, we see an allocation from Cost Source to Fixed Asset Ledger that isn't functioning, and the
user is aware of that.

![](../../resources/images/studio_images/studioimages/studio_diagram_cost%20source%20and%20allocations.png)

When the allocation is examined more closely, the issue isn't obvious.

![](../../resources/images/studio_images/studioimages/studio_allocation_destination.png)

However, when we sort Cost Pool Weight in ascending order, we see two small negative values:

![](../../resources/images/studio_images/studioimages/studio_data-issue_cost-pool-weight.png)

Note: Because it isn't always obvious, it's recommended to check weighting columns by sorting in
ascending order if you find an allocation that appears to be correctly configured.

In this case, the Cost Pool Weight was derived using a formula (shown below). The mix of
positives and negatives was coming from two different appended data sources as part of allocation
automation. However, a mix of positives and negatives was not anticipated and so the issue didn't
appear until uploads included negative depreciation values. In this case, the solution was to fix
the data.

![](../../resources/images/studio_images/studioimages/studio_formulas_cost%20per%20weight.png)

## Example 2: Use the weighting formula in an allocation to represent credits

Sometimes a company has general ledger entries that contain invoice credits they want to show in
reporting. Where they may want to display credits may vary, but in this example, we show the credits
in a target object to which the general ledger source allocates. The raw data is for three cost
centers: CC1, CC2, and CC3. CC1 has only debits, but CC2 and CC3 have a mix of debits and
credits.

![](../../resources/images/studio_images/studioimages/studio_gl%20with%20credits_source%20record.png)

The general ledger with the Credits table has a driver based on the Value column, and the object
identifier for the table is Cost Center. This results in net values for CC1, CC2, and CC3 of $900,
$0, and $400 respectively.

![](../../resources/images/studio_images/studioimages/studio_gl%20with%20credits_cost%20center.png)

No dollars are allocating:

![](../../resources/images/studio_images/studioimages/studio_cost-metric_gl-with-credits.png)

In this example, our target object's raw data is identical to our source and uses the UID as the
object identifier. This isn't unusual in real scenarios where a company has either general ledger
(GL) line items that they know sum to the values of an invoice, or they append the invoice detail to
the GL, replacing the original GL line items. We apply the weighting formula. CC1 and CC3 receive
the expected values, but because CC2 was net zero in GL with Credits, we get nothing in those
rows:

![](../../resources/images/studio_images/studioimages/studio_gl%20with%20credits_destination.png)

The formula worked: negative weightings were activated, and when the numbers didn't net to zero,
we got the expected results. However, in the case where a debit and credit summed to zero in the
source, the system didn't allocate. So, we didn't get any values in the target.

In the next example, we address both the negative weighting and the net zero in the source.

## Example 3: Using the segregation of positives and negatives in an allocation to represent credits

In this example, our goal is the same as in our last example. We are using the same raw data for
the GL. However, instead of using the weighting formula, we segregate the negative and positive
values in the source and the target so that we can use the absolute value of the Value column to
weight, and thereby get exactly what we want in the target. Also, our target object's backing data
does not include the source granularity, so it must be modified to support the display of credits
and to segregate negatives and positives.

Once again, the raw data is for three cost centers: CC1, CC2, and CC3. CC1 has only debits, but
CC2 and CC3 have a mix of debits and credits.

![](../../resources/images/studio_images/studioimages/studio_gl%20with%20credits_delimited%20data%20import%20options.png)

As in our last example, the object identifier for the table was Cost Center, and the data
relationship is based on Cost Center. Therefore, we want to add granularity where negatives exist.
We could use the UID column within the raw data but that would increase our model granularity
unnecessarily. This could have negative performance impacts in a large project. So instead, we add a
formula column called CC Credits and Debits as shown below. We also add a formula column called CC
Negatives.

![](../../resources/images/studio_images/studioimages/studio_weighting_gl%20with%20credits.png)

We modify the object identifier to use the new formula column:

![](../../resources/images/studio_images/studioimages/studio_gl%20with%20credits_new%20object%20identifier.png)

Next, we look at our target table:

![](../../resources/images/studio_images/studioimages/studio_steps_table.png)

In order to keep negative and positive values segregated and to get the correct numbers in the
target, we must add granularity to this table. To do that, we add the following formula columns:

- CC Negatives - Sums the CC Negatives in the source object based on the Cost Center in the
  target.
- Type Helper - If CC Negatives indicates there are credits in a Cost Center, then the value is
  Debit,Credit. Otherwise, it's Debit.
- Type - Splits out rows based on the value of the Type Helper.
- CC Credits and Debits - Merges Cost Center and Type data to form the new object identifier and
  data relationship column.
- Weight - Sums the values in the source based on CC Credits and Debits and takes the absolute
  value.

![](../../resources/images/studio_images/studioimages/studio_diagram_target%20object.png)

Next, we configure the object identifier:

![](../../resources/images/studio_images/studioimages/studio_diagram_credits%20and%20debits.png)

Finally, we configure the allocation:

![](../../resources/images/studio_images/studioimages/studio_gl%20with%20credits_target%20object.png)

This allows us to display the credits accurately in reporting based on the target object with the
lowest possible increase in the granularity of our model.
