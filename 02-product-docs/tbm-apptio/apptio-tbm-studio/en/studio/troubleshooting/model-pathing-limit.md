---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Model Pathing Limit"
breadcrumb: []
source_path: "studio/troubleshooting/model-pathing-limit.html"
images:
  - "resources/images/studio_images/troubleshooting/modelpath-1.png"
  - "resources/images/studio_images/troubleshooting/modelpath-10.png"
  - "resources/images/studio_images/troubleshooting/modelpath-11.png"
  - "resources/images/studio_images/troubleshooting/modelpath-2.png"
  - "resources/images/studio_images/troubleshooting/modelpath-3.png"
  - "resources/images/studio_images/troubleshooting/modelpath-4.png"
  - "resources/images/studio_images/troubleshooting/modelpath-5.png"
  - "resources/images/studio_images/troubleshooting/modelpath-6.png"
  - "resources/images/studio_images/troubleshooting/modelpath-7.png"
  - "resources/images/studio_images/troubleshooting/modelpath-8.png"
  - "resources/images/studio_images/troubleshooting/modelpath-9.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Model Pathing Limit

The Model Pathing Limiter prevents the creation and computation of models that have a
very large number of paths. The number of paths in a model will start to grow exponentially after a
certain point and start to have extremely degraded performance and calculation time.

![model path](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-1.png)

A path consists of the route units can take in a model from the bottom (usually cost source) to
any top object. The number of paths is all the possible permutations the units can take throughout a
model. As objects and allocations increase, the number of paths will start to increase
exponentially.

## Understanding Model Paths

The following model has a total of 15 paths from Level 5 (top) to Object Base (bottom). The model
was built to highlight the number of paths. Currently, there is no way to show this number in the
model.

![model path](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-2.png)

Adding an allocation line between Level 3C and Level 5 will add 3 additional paths to the model
because there are 3 paths up to Level 3C. If you visually trace the routes from Object Base to Level
3C, there are 3 possible routes.

![model path](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-3.png)

The performance review component will output a table that will indicate the number of paths and
will help identify the problematic areas.

In the following model, there are 60 total paths to the top.

![model path](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-4.png)

The following figure shows the model paths report for this model.

![model path table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-5.png)

To get the total paths to a given object, filter by that object in the To Object category, and
then sum the Paths To Bottom. It will match the preceding model (60).

![model path table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-6.png)

The Quantity column is the number of allocations between To Object and From Object. The ideal
place to start investigating where allocations can be removed or combined is the highest Quantity
number the lowest down in the model or in the table. For this model, it would be the pair of Level
1A and Object Base. There are more allocations between Level 5 and Level 3C, but being at the top of
the model, they are less impactful.

![model path table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-7.png)

![model path table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-8.png)

There are more lines going from Level 3C to Level 5, but they are farther up the model. The
allocations from Object Base to Level 1A generate 3 paths for every path above them. Therefore,
reducing the paths lower down has a greater impact. Removing one of these allocations reduces the
count by 12 (20%).

![model path table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-9.png)

Removing a line from Level 3C to Level 5 reduces the count by 10.

![model path table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-10.png)

Doing both results in a reduction of 20.

![model path table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-11.png)

To summarize, the number of paths in a model will start to increase at an exponential rate as
more objects and allocations are added. Specifically, when more than one outbound allocation is
added from an object, the overall number of paths in the model will increase. As the number of
objects with more than 1 outbound path increases, the number of paths will increase. The only way to
reduce the number of paths in a model is to reduce the number of allocations that exist in a model.
To get help to reduce the number of allocations in your model, reach out to your CSM.
