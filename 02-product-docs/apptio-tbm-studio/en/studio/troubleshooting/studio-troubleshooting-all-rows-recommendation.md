---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "All Rows Recommendation"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-all-rows-recommendation.html"
images:
  - "resources/images/studio_images/all-rows-recommdentation-1.png"
  - "resources/images/studio_images/all-rows-recommdentation-2.png"
  - "resources/images/studio_images/all-rows-recommdentation-3.png"
  - "resources/images/studio_images/all-rows-recommdentation-4.png"
  - "resources/images/studio_images/all-rows-recommdentation-5.png"
  - "resources/images/studio_images/all-rows-recommdentation.png"
  - "resources/images/studio_images/arr-1.jpg"
  - "resources/images/studio_images/arr-2.jpg"
  - "resources/images/studio_images/arr-3.jpg"
  - "resources/images/studio_images/arr-4.jpg"
  - "resources/images/studio_images/arr-5.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# All Rows Recommendation

This feature simplifies the process by providing step-by-step guidance based on expert
recommendations, ensuring faster calculation times and improved performance. You can access
documents and automate configuration changes to streamline your workflow. The system will
automatically check in changes and mark issues as resolved.

Navigate to **TBM Studio** > **Recommendations** tab, and then select **Troubleshoot All
Identified Problems**.

![Troubleshoot All Identified Problems](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-1.jpg)

Switch to **Development** workspace and select **Next**.

![Recommendations Wizard](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-2.jpg)

Click **Next** icon.

![Next](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-3.jpg)

Select **Set Automatic !ALL\_ROWS\_Assignment** button.

![ALL ROWS](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-4.jpg)

Select **Next**, and then select **Checkin** in the last page.

![Checkin](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-5.jpg)

Enable the 'Automatically handle !ALL\_ROWS' option in [project setting](../admin/edit-project-settings.html "Applies to: TBM Studio 12.0 and later. Some settings are available in later versions of TBM Studio, as noted below."). With
this setting enabled the TBMA no longer needs to create perspectives to handle ALL\_ROWS. It adds and
removes allows where needed and hence it removes the need to check the all rows box on
perspectives.

## Old Method: Retrieving all rows in time based query

![Retrieving all rows in time based query](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation.png)

This option can be configured when publishing a column to a perspective. It will add an ALL\_ROWS!
Item to a datapath, which will ensure when using a time aggregate such as =YearToDate() or Annual(),
that all the rows in the table are included in the computation. In data that varies over time you
will need to use ALL\_ROWS to ensure the correct information is being calculated. This is not always
included for performance reasons.

Assuming you have data that is structured like this.

![row recommendation](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-1.png)

The =Annual() amount for A and B is 12, and C is 1. However if you ran this function in months
Feb-December, you would only have Identifiers A and B in your table, see example below.

![Row Recommendations 2](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-2.png)

Since identifier C is not present in Feb-December data, those rows are not present in the current
month table, which results in the Annual Calculation showing the incorrect overall total. To remedy
this issue you would create a perspective of the column and check the “Show all rows in time-based
query”

![publish field](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-3.png)

Placing this new perspective into the configuration results in row C being shown, and taking into
account for the total.

![row recommendations](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-4.png)

When using “Time” in Columns, ALL\_ROWS is not needed, this is because the time buckets build a
different data structure called a TREND\_APPEND, that grabs the data from each month and appends it
together. One is not necessarily better than the other, it comes down to which specific reporting
view is trying to be achieved. Below you can see the 2 tables, which show the same data, but have
different datapaths, and slightly different naming/formatting.

![row recommendations](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-5.png)

## Conclusion

- ALL\_ROWS is not needed and won’t be added to datapaths that are using the time buckets
  (TREND\_APPEND)
- ALL\_ROWS is not needed if time aggregates are not being used.
- ALL\_ROWS is needed if the underlying data varies over time, and time aggregates are being
  used.
