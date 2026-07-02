---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Assign cost pools with machine learning"
breadcrumb: []
source_path: "data_studio/assigncostpools.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Assign cost pools with machine learning

Applies to: TBM Studio 12.7 and later. TBM Studio 12.7 and later can use machine
learning to speed up Costing Standard configuration. Previously, mapping accounts to cost pools
required manually creating mapping files with one-by-one assignment to reach the taxonomy-standard
cost pools. Now, machine learning maps the majority of accounts for you in milliseconds.

Watch this demo video from Apptio Education Services: [Machine Learning in
12.7](https://community.apptio.com/videos/2375 "(Opens in a new tab or window)"). Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

Apptio collects information and develops prediction models. As more data is classified, these
models learn over time.

Here is an overview of how machine learning in Apptio works.

1. The existing information Apptio has is classified to the desired outcome, such as cost pool, and
   is put into the training service (hosted in AWS).
2. Apptio identifies appropriate algorithms, determines the best parameters, and establishes a
   prediction model. The model is published to the catalog.
3. You can then access that model, apply it to your data, and review the results directly within
   Apptio. When the predictions have been reviewed as part of your configuration process, the
   now-classified data will be sent to our training service.
4. The new data triggers the training service to anonymize and generate a new model. Apptio tracks
   and adjusts the models over time to improve the quality and quantity of our predictions.
5. When a model meets our quality review, it is published in the catalog.
6. You can update to the latest model as desired.

Here is a diagram of the process:

![](../../resources/images/studio_images/studioimages/studio_diagram_download%20model.png)

SEE ALSO:

- [Map Columns](mapcolumns.htm "(Opens in a new tab or window)")
- [Configure machine
  learning for cost pools](configuremachinelearning.htm "(Opens in a new tab or window)")
- [Frequently asked questions about
  Map Columns](faqmapcolumns.htm "(Opens in a new tab or window)")
