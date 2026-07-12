---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Upgrade to Apptio Value Explorer 12.7 (v107)"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/upgradetoave1.7v107.html"
images:
  - "resources/images/ct_images/ave-before-v107.png"
  - "resources/images/ct_images/ave-updated-to-v107.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Upgrade to Apptio Value Explorer 12.7 (v107)

Applies to: Apptio Value Explorer (AVE) on TBM Studio 12.7 and later, with Template v107 and
later

The general configuration process for upgrading all applications to TBM Studio 12.7 is described
in [Upgrade Costing Standard to the Latest
Template Version](../user-guide/upgradecttolatest-9740.html) . This article contains a specific configuration step for upgrading the
Apptio Value Explorer (AVE) from any previous template version to template v107.

## Upgrade instructions

1. Follow the template upgrade instructions in [Upgrade Costing Standard to the Latest Template
   Version](../user-guide/upgradecttolatest-9740.html)

   When you get to Step 5, switch to this article, making sure you are in the correct
   branch before proceeding.
2. Upgrade the Apptio Value Explorer component.
3. Check in the AVE component upgrade.
4. Go to the Apptio Value Explorer Master Dataset in the Project Explorer.
5. Check out the document.
6. Click **Append**.
7. Delete the Apptio Value Explorer Raw table.
8. Re-append the Apptio Value Explorer Raw table.

   All of the columns will map
   automatically.
9. Save and check in your changes.
10. Return to the template upgrade instructions in [Upgrade Costing Standard to the Latest Template
    Version](../user-guide/upgradecttolatest-9740.html) to complete the remaining component upgrades.

## Background

The AVE is built on TBM Studio platform and is delivered as part of a Costing Standard project.
AVE includes a comprehensive list of product use cases. The AVE 12.7 update provides the following
improvements:

1. Refresh AVE content to include use cases for new products and features.
2. Simplify the amount of documentation in favor of more robust descriptions and outcomes that
   focus on the "why".
3. Remove the complexity of slicers, sales messaging, and duplicate rows.

## Persona

The AVE is designed for use by the following roles:

- TBM Office
  - Review and prioritize features
  - Determine which product components to configure
  - Communicate the value Apptio products deliver to the organization
- Customer Success Managers, Customer Success Advisors, Engagement Managers
  - Communicate the value that Apptio products deliver

## Compare versions

AVE before v107

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ave-before-v107.png)

AVE updated to template v107

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ave-updated-to-v107.png)

## Summary of changes

Content
:   - - Added product use cases across all Apptio products.
      - Created more granular use cases with a comprehensive description and outcomes to identify the
        reason behind the use case
      - Included use cases not delivered in Apptio out-of-the-box reports, but available using the
        extensibility of TBM Studio.

        These use cases link to the [Insights Toolkit](https://community.apptio.com/community/apptio/tbm-cookbook "(Opens in a new tab or window)") on TBM Connect.

Slicers
:   - - Changed to compact slicers in the AVE Master Report Template.
      - The **TBM Category > Sub-Category** slicer hierarchy replaces
        **Area**.
      - Removed the **Outcomes** slicer.

AVE table
:   - Simplified the three-tab table into an untabbed table. Removed the **Value and Apptio
      Approach** tab and consolidated the **Required Data Sources** tab into
      a single table.
    - Columns in the new AVE table:
      - **TBM Category** - High-level category for organizing the use cases. Replaces
        **Area** (for examle, Financials, Applications & Services).
      - **Use Case** - The "what." A short expression defining the capability of the
        product, expressed in a consistent verb-noun sentence.
      - **Description** - A longer description of the use case that can include the
        various attributes and scope of the use case.
      - **Outcome** - The "why." The expected value of the use case.
      - **Capability** - The high-level capability or action of the use case (for
        example, Plan, Optimize, Influence)
      - **Report** - If the associated component is installed, this column contains
        links to the specific Apptio report that can be used to analyze metrics for the use case. If the
        component isn't configured, this column will link to the reference project. If the report is
        customized instead of out-of-the-box, this column will link to the [Insights Toolkit](https://community.apptio.com/community/apptio/tbm-cookbook "(Opens in a new tab or window)") on TBM Connect.
      - **Data Requirements** - This column links to the Data Advisor so you can view
        the required (and optional) data sets and columns needed to configure the component and associated
        use cases.
    - Additional pickers:
      - **Product** - The Apptio product that enables the use case (for example,
        Apptio for Cloud).
      - **Module** - The underlying Apptio module that enables the use case (for
        example, HBM).
      - **In Product** - The indicator that the use case is supported out-of-the-box
        versus being a customized configuration with TBM Studio.
      - **Is Configured** - Sorts based on whether the related component is
        installed.
