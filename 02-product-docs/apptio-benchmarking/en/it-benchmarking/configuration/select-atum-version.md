---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Costing Standard Integration"
breadcrumb: []
source_path: "it-benchmarking/configuration/select-atum-version.html"
images:
  - "resources/images/it_benchmarking_images/frontdoor.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_1.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_10.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_11.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_12.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_13.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_14.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_17.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_19.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_2.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_20.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_22.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_4.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_5.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_6.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_9.jpg"
  - "resources/images/it_benchmarking_images/settingsadvanced.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Costing Standard Integration

This document provides information on (1) selecting an ATUM version for Interactive Benchmarking
(2) walking through settings to fetch actuals from the Costing Standard Application. The 1st section
of the document focuses on Costing Standard in R12 and the 2nd section calls out fetching actuals
from an R11 Costing Standard Project. The 3rd section calls out the flow for configuring when a
customer logs in to Interactive Benchmarking for the first time.

**IMPORTANT**  In this version, sub-tower actuals are not retrieved. Fetching
sub-tower data will be enabled in a subsequent release.

**Costing Standard in TBM Studio v12**

**Assumptions**

- Your Apptio product is Front Door enabled.
- The R12 Costing Standard application and Interactive Benchmarking are in the same environment.

See picture below for an example of an environment with Costing Standard & Interactive
Benchmarking.

NOTE You can have more than one Costing Standard Application as well as other Applications in an
environment.

![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/frontdoor.jpg)

**Using Settings for configuration**

This section will walk through configuring ATUM versions & fetching actuals using the
Settings pages.

The recommended sequence is to first select your ATUM Version. You do this by click on the
Settings Flywheel in the top-right corner of the Interactive Benchmarking application. You will see
the settings page with a set of tabs.

- Click on the Advanced Tab. Here you will see the ATUM version section (see image below with V2
  selected).

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/settingsadvanced.jpg)
- You can change the ATUM version. In doing so, you will see a yellow warning banner that
  provides information on:
  - Impact of changing the ATUM version:
    - Towers & Sub Towers are different between V1 & V2 so you will see this change the list
      of towers & sub towers
    - Due to this difference, volumes, actuals cost data and benchmark selections for towers and
      sub-towers will be discarded.
  - Recommended next steps once you make this change:
    - Retrieve your actual cost data or enter it manually
    - Update your volumes
    - Review your selections across the benchmark layers (Industry, IT OpEx and Infrastructure).

  The image below shows an example of switching over to V1. The yellow banner with the impact and
  recommendations is on the right.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_11.jpg)
- You can then proceed with this selection by clicking on Save. This results in dialog box that
  lists the data with the same yellow warning banner.  **IMPORTANT:**  this step
  doesnt as yet Fetch actuals from the Costing Standard project. It only switches the current data
  over to the changed ATUM version. You need to make an explicit Fetch from Actuals as called out in
  the next several steps.

  You need to click "Continue with these actuals" to close this dialog
  box.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_12.jpg)
- The next step is to configure the settings for Fetching from Costing Standard. For this, you
  click on the  **APPTIO Source tab**  in settings (see image below). This will
  provide a drop down list of Costing Standard Applications in your Apptio (Front Door Environment).
  In this screen below, there is only one Costing Standard Application (with the name Costing Standard). You then click the  **Validate Connection**  button.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_17.jpg)
- Once the connection is validated, you will see a screen where you can select a Costing Standard
  Project and a specific month. In the example image below, you see the selected project is:
  reference.apptio.com: Costing Standard. IMPORTANT: Please pick the specific CT project that you want
  to fetch actuals cost data. The yellow banner on the right is a warning note. It calls out that you
  need to ensure the CT project is open (as selecting a closed project will trigger a calc in CT).

  Now click "Retrieve Cost Data" to fetch actuals from the selected Costing Standard project and
  month/year.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_19.jpg)
- You will now see the fetch data in a dialog box (see image below for an example). The New
  Source column contains the data fetched from the selected project.

  Click on  **Continue
  with these actuals**  . This results in saving the retrieved cost data from the project.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_20.jpg)
- You can also view the retrieved cost data by selecting the Cost Data tab in Settings. The image
  below is a screenshot of the Cost Data. It shows the overall costs, cost pool costs & tower
  costs filled in. Sub-tower costs are blank and need to be typed in manually.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_22.jpg)
- Finally, as before, Organization Profile is manually entered (as it is not part of the Costing Standard project) as it is benchmarking specific. You can enter Organization Profile by selecting
  the Organization Profile tab.

  For Sub-tower Annual Costs & Volumes, you can enter them
  either by:

  - In the settings section; Sub-tower annual costs in the Cost Data tab and Volumes in the Volumes
    tab, or
  - In the individual sub-tower pages under Infrastructure metrics.

You are now ready to make your benchmark comparisons with actuals.

**Costing Standard in TBM Studio v11**

For Costing Standard projects in v11, there is no Frontdoor integration. This means you will
need to create/use an admin user (in v11) and type in the user name/password in Interactive
Benchmarking. In the Apptio Source Tab (see image below), you have the option to manually enter the
URL (the hyperlink is: manually entering the URL and AdminDB credentials). Click on that hyperlink.

![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_1.jpg)

In the next step, you see input text boxes where you need to provide the instance URL, AdminDB
Username and AdminDB Password. This  [video](https://community.apptio.com/videos/1516 "(Opens in a new tab or window)")  provides additional
information on using this.

![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_2.jpg)

The other steps on selecting ATUM versions and setting volumes etc are the same as for R12.

**First User Experience Setting**

The Interactive Benchmarking application provides a first time user experience for customers
when they log in for the 1st time. This is to guide them through the initial set-up.

- If no user has logged in to Interactive Benchmarking for a customer & configured it, the
  first screen that you will see (if you are the 1st user) is a Getting Started page. See image below
  for an example. It identifies the steps you need to take to configure it. Note: it also provides an
  option for you to skip the configuration in case you want to either (1) configure it later using the
  Settings flow mentioned above or (2) set it up manually.

  To proceed, click the  **Lets
  Get Started**  button.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_4.jpg)
- The next several steps are similar to the steps described in the above sections but with more
  of a guided experience. Please review the 1st two sections to familiarize yourself on the specifics.
  The 1st step is to select your ATUM version. Here you are asked to pick your ATUM version. Click
   **Next**  .

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_5.jpg)
- Next is to select your Costing Standard Source. The screen you see will be like the one below.
  Pick your Costing Standard application and click Connect.  **NOTE:**  Here you
  have the option to skip these steps and go to the Benchmarking screen (by clicking **entering cost data manually**  ) or fetching from R11 (by clicking on  **manually
  entering the URL and AdminDB credentials**  ).

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_6.jpg)
- Once you click  **Connect**  , you will be prompted on selecting the right
  project & time period. The yellow banner is the same as the one described in the 1st section.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_9.jpg)
- You can select your project and time period & click "Go". See below for an example
  screen.This retrieves actuals data from the project.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_10.jpg)
- The last configuration step is type in Organization Profile. See screen below for an example.
  Type in your Organization Profile data and click  **Next**  .

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_13.jpg)
- At this point you have configured Interactive Benchmarking. You will see a "Done" screen like
  the one below. Clicking on "Explore" will take you to a configured Interactive Benchmarking
  application.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_14.jpg)

At any time, you can make modifications to your configuration by clicking on the Settings
Flywheel on the top right of the screen and following the steps mentioned in the 1st section.
