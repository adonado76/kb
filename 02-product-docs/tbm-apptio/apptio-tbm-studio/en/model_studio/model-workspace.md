---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "model_studio"
title: "The model edit workspace"
breadcrumb: []
source_path: "model_studio/model-workspace.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# The model edit workspace

Applies to: TBM Studio 12.0 and later

Use the model edit workspace to add drivers to a table and to allocate values from the table to
other tables. To display the workspace, click the Model step in the transform for a table. An
example of the workspace is shown in the following image:

![](../../resources/images/studio_images/studioimages/studio/stu539.png)

Watch this demo video from Apptio Education Services: [View Cost Allocation
Strategies (2 mins.)](https://community.apptio.com/videos/1829 "(Opens in a new tab or window)") Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## Drivers

In the edit workspace, the table you are editing is displayed in the center column. In Figure A,
the table is Services. The unit and allocation drivers are displayed in the left column.

- In the preceding image, there is a unit driver called Driver XYZ.
- The titles of the allocation drivers are in parentheses. This is because they are using the
  default names for the tables. If you change the default name, the parentheses are not displayed. In
  Figure A, there are two allocation drivers: Servers and Support. To navigate to an
  allocation driver, click the arrow at the left edge of the driver box.

## Allocations

The target allocation tables are displayed in the right column. Value from the table being edited
can be allocated to one or more other tables. In the preceding image, the Services value is
being allocated to the Business Units table.

## Config Only View

If you are editing a table which is modeled, you can use the "Config Only" view to make things
snappier. This allows you to more rapidly edit the config without as many delays related to the
system updating views. Bear in mind this is toggled on a per-object basis.

Config Only mode is accessible via the "View" drop down menu in the ribbon as follows:

![](../../resources/images/studio_images/model-workspace-1.png)

When this is turned on you will not see numbers in the model view:

![](../../resources/images/studio_images/mw-2.png)

To turn off Config Only View select "Show Document" in the same drop down:

![](../../resources/images/studio_images/mw-3.png)
