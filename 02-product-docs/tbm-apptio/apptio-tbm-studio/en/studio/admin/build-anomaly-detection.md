---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Build Anomaly Detection"
breadcrumb: []
source_path: "studio/admin/build-anomaly-detection.html"
images:
  - "resources/images/studio_images/anol-det.png"
  - "resources/images/studio_images/anomalies-banner.png"
  - "resources/images/studio_images/anomalies-settings.png"
  - "resources/images/studio_images/build-anomaly.png"
  - "resources/images/studio_images/enable-calculation-effort.png"
  - "resources/images/studio_images/yes-no-anaomaly.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Build Anomaly Detection

The anomaly detection feature is designed to help you identify unusual changes in
calculation effort, which can help you optimize your reports and transforms. This feature is based
on the data collected by Calc Explorer, which provides detailed information about the calculation
effort for each build.

The anomaly detection feature uses the data from Calc Explorer to identify unusual changes in
calculation effort. It compares the calculation effort for each build to the previous builds and
identifies any significant changes. If a significant change is detected, the feature will alert you
and provide detailed information about the change.

## Benefits of Anomaly Detection

The anomaly detection feature can help you:

- Identify and optimize inefficient reports and transforms
- Reduce calculation effort and improve performance
- Improve the overall quality and reliability of your reports and transforms

## How to Use Anomaly Detection

To enable the anomaly detection feature, do the following:

1. Navigate to **Project** > **Enable Features** and select **Show Anomalies Panel**
   checkbox.
2. Navigate to **TBM Studio** > **Project** > **Anomalies** tab.

   ![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/build-anomaly.png)
3. Expand the anomaly type and investigate any anomalies that are detected.

   ![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/anol-det.png)

   Table 1.

   | Field | Description |
   | --- | --- |
   | Started | Shows the timestamp when the calc started |
   | Calc Explorer | Links to the calc which had the anomaly |
   | Change Set | Links to the list of transforms and entities changed with the build |
   | Changes | Links to the change messages associated with the build |
4. Take appropriate action to optimize the reports and transforms as needed.

## How to Auto-Pause Calculation (Beta)

Auto-Pause Calcs feature is introduced to pause the calculations when an anomaly is detected. To
enable this feature,

1. From **Anomalies** tab, Select **Settings** Icon.

   ![Anomalies Setting Icon](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/anomalies-settings.png)
2. Under **Calculation Effort** tab, enable the **Auto-Pause Calcs on Detected Anomaly (Beta)**

   ![Enable Calculation Effort](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enable-calculation-effort.png)
3. Click **Save**

Once the feature is enabled and If an anomaly is detected, a banner will appear to confirm that
the calculation has been paused.

![Banner](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/anomalies-banner.png)

When you resolve the anomaly, select either **Yes** or **No** to unpause the calculations.

![Yes or No](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/yes-no-anaomaly.png)

## Types of Anomalies

There are two types of anomalies that the feature can detect:

- **Calculation Anomaly**: This type of anomaly is an increase in calculation effort over what
  what was expected for a calc.
- **Entity-Based Anomaly**: This type of anomaly occurs when there is an unusual pattern in the
  data shape (e.g., an unusual number of rows).
- **Combined**: This type of anomaly occurs when there is a combination of calculation and
  entity-based anomalies.

**Calculation Anomalies**

A calculation anomaly occurs when the calculation time for a build is significantly higher than
usual. This can be caused by various factors, such as:

- Uploading a large amount of data, modifying formulas, or changing report configurations.
- Changes that increase the calculation effort, such as adding new reports or transforms.

**Investigating Calculation Anomalies**

To investigate a calculation anomaly, you can:

- **View the change set**: See the specific changes made in the build, such as uploaded files
  or modified formulas.
- **Explore Calc Explorer**: Analyze the calculation effort for the build and identify areas
  where the calculation time is higher than usual.

The system will eventually provide explainability features to help you understand the cause of
the calculation anomaly. This will include information such as:

- **Specific files or changes**: Which files or changes caused the calculation time to
  increase.
- **Assignment ratios table**: How changes to the assignment ratios table affected the
  calculation time.

## Troubleshooting

If you encounter any issues with the anomaly detection feature, do the following:

- Check the Calc Explorer data to ensure that it is accurate and up-to-date.
- Investigate any anomalies that are detected and take action to optimize the reports and
  transforms as needed.

## FAQs

- Q: What is the purpose of the anomaly detection feature? A: The anomaly detection feature is
  designed to help you identify unusual changes in calculation effort, which can help you optimize
  your reports and transforms.
- Q: How does the anomaly detection feature work? A: The anomaly detection feature uses the data
  from Calc Explorer to identify unusual changes in calculation effort. It compares the calculation
  effort for each build to the previous builds and identifies any significant changes.
- Q: What types of anomalies can the feature detect? A: The feature detect changes in calculation
  effort due to material changes, increased calculation effort, or data shape anomalies such as
  outliers, skewness, or distribution shifts.
