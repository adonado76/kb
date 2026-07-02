---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Complete the Cost Data Tab"
breadcrumb: []
source_path: "it-benchmarking/configuration/interactive-benchmarking/cost-data.html"
images:
  - "resources/images/it_benchmarking_images/interactive-1.jpg"
  - "resources/images/it_benchmarking_images/interactive-10.jpg"
  - "resources/images/it_benchmarking_images/interactive-11.jpg"
  - "resources/images/it_benchmarking_images/interactive-2.jpg"
  - "resources/images/it_benchmarking_images/interactive-3.jpg"
  - "resources/images/it_benchmarking_images/interactive-4.jpg"
  - "resources/images/it_benchmarking_images/interactive-5.jpg"
  - "resources/images/it_benchmarking_images/interactive-6.jpg"
  - "resources/images/it_benchmarking_images/interactive-7.jpg"
  - "resources/images/it_benchmarking_images/interactive-8.jpg"
  - "resources/images/it_benchmarking_images/interactive-9.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Complete the Cost Data Tab

The Cost Data tab is for manual entry of Cost Transparency model information.

There are 3 sections in the Cost Data Tab:

- Annual IT Cost Data
- Annual Cost Pool Data
- Annual IT Resource Tower/Sub-Tower Data

**Annual IT Cost Data**

Benchmarking calculates values based on the Annual Cost metric. For additional details, refer to
the metric formula itself found in the Metrics tab. The formula calculates the prior rolling 12
months. When manually entering data into Interactive Benchmarking, select the month after the final
month representing the end of the annual period for the comparisons you want.

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-1.jpg)

For example, selecting Jan FY17 will display the value from the prior Jan FY16-Dec FY16.
Selecting Jun FY 17 will display the annual value of the prior Jun FY16-MayFY17.

Next, filter for ”annual” in the Metrics search. Select  **Annual Cost**  and
then select  **Cost Source**  from the Properties menu as shown below in Fig. 1.

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-2.jpg)

(Fig. 1)

After selecting  **Cost Source**  , confirm the date and note the annual cost
column total (Fig. 2) and enter this value in the Annual Cost entry in Interactive Benchmarking
(Fig. 3):

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-3.jpg)

(Fig. 2)

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-4.jpg)

(Fig. 3)

Repeat this process for Annual Depreciation by selecting the  **Annual Cost** metric and the  **Fixed Asset Ledger**  object. Copy the **Annual Cost**  column total from the Cost Transparency model into the  **Annual
Depreciation**  field in Interactive Benchmarking.

Lastly, repeat this process for Annual CapEx by selecting the  **Annual CapEx** metric in the Cost Transparency model, the  **Cost Source**  object
in the Properties section and noting the Annual CapEx total.

**Annual Cost Pool Data**

The Cost Pool values are also available in the same Metrics tab in Cost Transparency. Confirm
the  **Annual Cost**  metric is selected and  **Cost Source** 
is selected in the Properties. Next, right-click and show/hide columns to show the Cost Source
Master Data Cost Pool column (see Fig. 4).

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-5.jpg)

(Fig 4)

With the Cost Pool column visible, filter by each Cost Pool and note the  **Annual Cost** column total. Copy this value into Interactive Benchmarking.

For example, for Hardware, filter for Hardware and copy the Annual Cost column total from Cost
Transparency into Interactive Benchmarking (Fig. 5).

![img6](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-6.jpg)

(Fig. 5)

Continue this process for each ATUM ™ Cost Pool.

**Annual IT Resource Tower/Sub-Tower Data**

This process is identical to the Cost Pool process but instead of selecting Annual Cost at the
Cost Source and bringing in the Cost Pool column, select the  **IT Resource Tower** object and select the  **Tower**  and  **Sub-Tower** columns.

Switch to Studio mode and navigate to the  **Metrics**  tab. Select the
 **Annual Cost**  metric. Next, select the  **IT Resource Tower** object in order to look at cost for each of the IT Resource Tower and Sub-Towers (see
Fig. 6).

![img5](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-7.jpg)

(Fig. 6)

From this screen, right-click and select  **Show/Hide Columns**  (see Fig.
7).

![img4](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-8.jpg)

(Fig. 7)

Select the  **IT Resource Tower**  and  **Sub Tower** 
columns from the dialog box, and then click OK (see Fig. 8).

![img3](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-9.jpg)

(Fig. 8)

Once you have selected the columns, filter for the  **IT Resource Tower** 
and  **Sub-Tower**  combination to find the Annual Cost (see Fig. 9).

![img2](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-10.jpg)

(Fig. 9)

Copy the value into the interactive benchmark data entry screen (see Fig. 10).

![img1](../../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/interactive-11.jpg)

(Fig. 10)

Complete this process for each IT Resource Tower and Sub-Tower by filtering for each respective
value in the Cost Transparency Metric tab.
