---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a chart"
breadcrumb: []
source_path: "reports/add-a-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a chart

Applies to: TBM Studio 12.0 and later

When you first add a chart, the format defaults to a horizontal bar chart like the one shown in
the following image. After you create the initial chart, you can change the type of chart.

![](../../resources/images/studio_images/studioimages/studio/stu521.png)

## Add a chart to a report

1. Display the report.
2. On the Report tab, click the Chart icon. The Ad Hoc Component Configuration
   panel is displayed as shown in the following image. Its appearance will vary depending on your data
   sets.

   ![](../../resources/images/studio_images/studioimages/studio/stu522.png)
3. Use the Ad Hoc Component Configuration panel to build the chart.
4. You build charts by opening the Tables, Calculations, Time, and other
   perspectives in the Project Explorer panel and dragging fields into the four areas of the
   Component Configuration panel.

## Change the chart type

By default, the application builds a horizontal bar chart. You can change the type of chart by
selecting the chart, selecting the Ad Hoc tab, and then selecting one of the chart types in
the Visualize section shown in the following image:

![](../../resources/images/studio_images/studioimages/studio/stu618.png)

## X and Y axis labels shortened

The labels displayed on the x and y axes have a maximum length of 20 characters. If a label
exceeds this length, characters are removed from the middle of the label. For example, assume you
have the following series of labels:

> aaaa bbbb cccc dddd eeee ffff 0001
>
> aaaa bbbb cccc dddd eeee ffff 0002
>
> aaaa bbbb cccc dddd eeee ffff 0003
>
> aaaa bbbb cccc dddd eeee ffff 0004
>
> aaaa bbbb cccc dddd eeee ffff 0005

If you use these in a chart, they will appear as follows:

![](../../resources/images/studio_images/studioimages/reports/rep199.png)

## Build an example chart

In this example, we will build the bar chart shown in the following image. It is based on Data
Center data.

![](../../resources/images/studio_images/studioimages/studio/stu524.png)

To build the chart:

1. Click Chart on the Report tab.
2. In the Component Configuration panel, select Data Centers as the modeled
   table.
3. Click the Tables perspective, open the Data Centers table, and drag Data Center
   into the Legend area.
4. Click the Calculations perspective and drag Cost into the Values area.
5. Select the Time perspective and drag Quarters into the Axis area. The **Ad Hoc
   Component Configuration** dialog should now look like the following image:

   ![](../../resources/images/studio_images/studioimages/studio/stu525.png)
6. To change to the vertical bars, select the Ad Hoc tab and then select the Column
   icon.
