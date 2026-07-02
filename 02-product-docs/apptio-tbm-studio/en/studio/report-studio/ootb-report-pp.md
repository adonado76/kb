---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Steps to Enable Modernized OOTB (NX) Reports in Client Instance"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Configuration and Customization"
source_path: "studio/report-studio/ootb-report-pp.html"
images:
  - "resources/images/studio_images/pp-s2.png"
  - "resources/images/studio_images/pp-s3a.png"
  - "resources/images/studio_images/pp-s5a.png"
  - "resources/images/studio_images/pp-s5b.png"
  - "resources/images/studio_images/pp-screenshot.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Steps to Enable Modernized OOTB (NX) Reports in Client Instance

This document outlines the **steps required to enable Modernized OOTB (New Experience
(NX)) reports** on a client instance. These reports provide enhanced visibility, better insights,
and a more user-friendly‑ experience while continuing to use the **same datasets as Classic TBM
Studio**.

1. **Verify Prerequisites**

   Before enabling any reports, ensure the client environment meets
   the **mandatory template and server version requirements**.

   - **Required Versions**
     - **Template Version:** V120
     - **Server Version:** 12.11.22 or higher

     These versions are **mandatory** to enable the Modernized OOTB reports.
2. **Point Client Template to Content Version V120 (No Upgrade Required)**

   If the client is
   **not already pointing to Content Version V120**, they do **not need to perform a full template
   upgrade**. You can find the content version using TBM Studio à Project Tab à Project Settings à
   Pop up window will have a field called Component Version which will help you know what the current
   content template version is.

   ![edit project settings popup](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s2.png)

   - **What is Required**
     - Temporarily **point the client instance to Content Version V120** via the **Report
       Components** section using drop down menu of Component version (navigate through TBM Studio à
       Project Tab à Project Settings à Pop up window will have field called Component Version)
     - This step is required because **new Modernized OOTB (NX) report components are only visible
       when the content version is set to V120**
   - **Key Clarifications**
     - **No template upgrade is required**
     - This is **only a content version pointer change**, not a structural upgrade
     - After pointing to V120, clients can **install the required report collections**
   - **Reverting the Content Version (Optional)**
     - Once the required NX report components are installed, the client **can revert to their original
       content version** if desired
     - **There is no risk in doing this**
   - **Important Assurance**
     - Installed NX report components will **remain available** even after reverting
     - All installed **tables, models, and reports stay intact**
     - No data loss or functional impact occurs due to reverting the content version

     Note: Without temporarily pointing to **Content Version V120**, the new NX components will
     **not be visible** in the Components list.
   - **Reference Documentation**

     If additional guidance is needed, clients can refer to the
     official Apptio documentation:

     - Installing new Apptio Costing solutions on older template projects

       https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-installing-new-apptio-costing-solutions-older-template-projects
3. **Install Modernized NX Components**

   Once the environment is on:

   - Template Version **V120**
   - Server Version **12.11.22 or above**

   The report components can be enabled using **either** of the following
   options:

   **Option A: Admin/ TBM Studio Write Access Role**
   - A user with **Apptio Admin Role or TBM Studio with write access** can directly enable the
     components. This can be done using Step 2 to enable Template version to latest content version
     first. Post that users can navigate to Projects Tab and install the newly available NX Components.

     ![enable templates and modules](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s3a.png)

   **Option B: Customer Success Manager (CSM)**
   - The client can request their **assigned CSM** to enable the components on their behalf.
4. **Identify Available Report Collections and Components**

   The following table lists the
   **Report Collections** and **Main Report Components** available as part of this release.

   - **Modernized NX Report Collections and Components**
   - **Financials**
   - **CTF – Cost Source NX Reports**
     - Financial Review
     - Financial Review – CapEx
     - Financial Analysis
   - **Mainframe**
   - **BI – Mainframe Insights NX Reports**
     - Mainframe TCO
     - Mainframe Analysis
     - Mainframe Apps
     - Mainframe Usage
     - Mainframe Usage Consumption
     - Mainframe Usage Consumption Invoice
   - **AI TCO & Usage**
   - **AI TCO & Usage NX Reports**
     - AI TCO & Usage
   - **Vendors**
   - **CTF – Vendors NX Reports**
     - Vendor Review
     - Vendor Cost Take‑Out
     - Vendor List
   - **Labor**
   - **CTF – Labor NX Reports**
     - Labor Review
     - Labor Analysis
     - Labor Cost Take‑Out
   - **Applications**
   - **CT Apps – Applications NX Reports**
     - Application Review
     - Application List
     - New & Retired Apps
     - Infrastructure Analysis by Application
   - **Services**
   - **CT Apps – Services NX Reports**
     - Service List
     - Service Review
   - **Public Cloud TCO**
   - **Public Cloud TCO NX Reports**
     - Public Cloud TCO
5. **Install NX Report Components in TBM Studio**
   1. Navigate to **TBM Studio**  as mentioned in step 3.
   2. Go to the **Components** section
   3. Locate the required **NX Report Components**
   4. **Install** the desired components

   Once installed, the components will appear under the **Available Components** list in TBM
   Studio.

   The screenshot below shows the star tagged components as new components available to
   install.

   ![install components](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s5a.png)

   Once clicked on any component, it will show the description and
   details about the component. After clicking on the install button, the user will be able to install
   the components, and reports will be available in New Report Studio, which is the blue button
   mentioned in screen shot.

   ![apps bx report component](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s5b.png)
6. **Navigate to the New Report Studio**
   1. After component installation, click the **blue link/button** at the top of the screen
   2. This action navigates the user to the **New Reporting Studio**
7. **Access and Use Modernized NX Reports**
   - Installed report components will appear as **Collection folders** in the New Reporting
     Studio
   - Users can:
     - Select the required **collection**
     - Navigate to individual **main reports**
     - Use built-in‑ **drill‑down paths** for deeper insights

     Screenshot showing how will it appear post installing the component:

     ![report viewer page](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-screenshot.png)

   Important:
   - The Modernized OOTB reports use the **same data sets** already available in **Classic TBM
     Studio**
   - No additional data configuration or ingestion is required
   - Once Modernized NX Report components are installed and checked in, then End users will be able
     to see those report collections and reports in their instance.

## FAQ: Modernized OOTB (NX) Reports

**Section A: General FAQ – OOTB NX (Modernized) Reports**

1. What are Modernized OOTB (NX) reports?

   Modernized OOTB (New Experience – NX) reports are
   **next‑generation out‑of‑the‑box reports** designed to deliver:
   - Better visibility
   - Cleaner, modern UI
   - Improved insights
   - Simplified navigation with drill‑down experiences

   They are built on top of the **existing TBM data model** and leverage the same
   datasets as Classic TBM Studio reports.
2. How are NX reports different from Classic OOTB reports?

   NX reports:
   - Are **user‑friendly and insight‑driven**
   - Consolidate large, complex reports into focused views
   - Provide drill‑down navigation instead of static multi‑page reports
   - Align with Apptio’s **modern reporting and UX standards**

   Classic reports remain supported, but NX reports represent the **future direction of
   reporting**.
3. Do NX reports replace Classic OOTB reports?

   No. **NX reports coexist with Classic
   reports**. Customers can:
   - Continue using Classic reports
   - Explore and adopt NX reports at their own pace

   Over time, NX reports will become the primary reporting experience.
4. Are NX reports generally available (GA)?

   Yes. NX reports are released as **GA**. This means:
   - Features may evolve
   - Feedback is actively incorporated
   - Enhancements may be released frequently
5. Which functional areas are covered by NX reports?

   NX reports are available across 8 components
   for Batch 1, including:
   - Financials
   - Mainframe
   - AI TCO & Usage
   - Vendors
   - Labor
   - Applications
   - Services
   - Public Cloud TCO

**Section B: Implementation & Enablement FAQ**

1. What are the prerequisites to enable NX reports?

   The client must be on:
   - **Template Version:** V120
   - **Server Version:** 12.11.22 or higher

   These are mandatory for enabling NX reports.
2. Is a full template upgrade required to enable NX reports?

   No. A **full template upgrade is
   not required**. Clients only need to **temporarily point to Content Version V120** to make NX
   components visible.
3. Why do we need to point to Content Version V120?

   NX report components are packaged under
   **Content Version V120**. Without pointing to V120:
   - NX components will **not appear** in the Components list
   - Installation is not possible
4. Can we revert back after installing NX components?

   Yes. Clients can revert to their original
   content version after installation. There is **no risk**:
   - Installed NX components remain available
   - Tables, models, and reports stay intact
   - No data loss or system impact
5. Who can enable NX Report components?

   NX Report components can be enabled by:
   - An **Admin/ TBM Studio Write Access Role**
   - Or the client’s **assigned Customer Success Manager (CSM)**
6. Where do users access NX reports after installation?

   After installation:
   - Click the **blue link/button** on the top of the screen
   - This navigates users to the **New Reporting Studio**
   - Reports appear as **Collections** with navigation and drill paths
7. Do NX reports need new data sources or ingestion?

   No. NX reports use the **same datasets
   already available in Classic TBM Studio**. No additional:
   - Data configuration
   - Data ingestion
   - Mapping

     is required.

**Section C: Usage & Behavior FAQ**

1. Can NX reports be used immediately after installation?

   Yes. Once components are installed and
   checked in:

   - Report collections become visible
   - End users can start using reports immediately
2. Are NX reports role‑based?

   Access to NX reports follows:

   - Existing user roles
   - Project permissions

     No separate access management is required.
3. Do NX reports support drill‑downs?

   Yes. NX reports are designed with:

   - Summary‑level insights
   - Contextual drill‑downs
   - Simplified navigation paths

**Section D: Customization FAQ (Important for Customers)**

1. What is the recommended best practice for OOTB NX reports?

   **Do not customize OOTB NX
   reports.** Keeping reports unmodified ensures:
   - Automatic access to enhancements
   - Compatibility with future releases
   - Reduced maintenance overhead
2. What happens if I customize an OOTB NX report?

   If an OOTB NX report is customized:
   - Future enhancements will **not** be applied
   - The report becomes **customer managed**
   - New features and fixes will not propagate
3. Will customized NX reports receive updates in future releases?

   No. Enhancements are delivered
   **only to unmodified OOTB NX reports**.
4. How can customers receive the latest NX report enhancements?

   Customers must:
   1. **Revert customizations** on affected OOTB reports
   2. Coordinate with their **CSM or IBM Apptio Support**
   3. Upgrade the instance to the desired release version
5. How do I revert customizations in OOTB NX reports?
   1. Navigate to **TBM Studio → Project Tab**
   2. Select **Components**
   3. Go to **Installed Components**
   4. Open the customized component
   5. Scroll to **Customized Elements**
   6. Click the **Revert** icon for each customized report
   7. (*Only reports need to be reverted*)
   8. Click **Check‑In**
6. Do I need to revert everything in the component?

   No. Only **customized report elements**
   must be reverted to receive report‑level enhancements.
7. What if customization is absolutely required?

   Best practice:
   - **Copy the OOTB report**
   - Customize the copied report
   - Keep the original OOTB NX report unchanged

     This allows customization **without losing future
     enhancements**.

## Key Takeaways

- Avoid customizing OOTB reports
- Customized reports do not receive enhancements
- Revert customizations before upgrades
- Coordinate with CSM or Support

Navigate to [NX
Reports](/docs/SSI71A/cost-transparency/get-started/costing-guide-nav.html#base_file_name__nrs)

**Parent topic:** [Configuration and Customization](../../studio/report-studio/config-custom.html)
