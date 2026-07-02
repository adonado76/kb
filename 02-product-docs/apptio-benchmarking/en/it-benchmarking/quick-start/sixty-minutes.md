---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "“First 60 minutes” with Benchmarking"
breadcrumb:
  - "Benchmarking"
  - "Quickstart"
source_path: "it-benchmarking/quick-start/sixty-minutes.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# “First 60 minutes” with Benchmarking

The walkthrough below assumes you are the Admin, TBMA or analyst responsible for initial
setup.

1. **Open Interactive Benchmarking and identify your starting point** and select **Settings**
   > **Configuration**

   ![Benchmarking Configuration](../../resources/images/it%20benchmarking_images/config-settings.png)

     
   You should be able to answer: Where do I change configuration?
2. **Enter or validate organizational profile data**  
   Organizational profile data is
   required for Industry and many IT OpEx metrics. It is not pulled from Costing. It is manually entered.  
   Inputs:
   - Organization (Annual) Revenue
   - Organization (Annual) OpEx
   - Number of Employees as an FTE (full-time equivalent) for the supported organization  
   Guidelines
   - Use values that match the IT cost scope. If the IT org exclusively supports North America, do
     not use global revenue.
   - Use the most recent completed fiscal year rather than a forecasted year or annualized
     spend.
   - If you have multiple legal entities but a single IT function/org, align your profile with how
     the IT costs are scoped.  
     You can refine later. The first goal is to be directionally
     correct, so rough estimates are acceptable.
3. **Provide annual IT cost data, volumes, and FTEs**You have two paths:  
   - **PATH 1** Connect to Costing (recommended)  
     In Interactive Benchmarking configuration:
     - Integrate with the Costing platform by selecting “Cost Transparency”.
     - Validate the connection.
     - Select the primary Costing project that holds your IT actual spend.
     - Select the fiscal period from the fiscal year that should be used for your baseline
       benchmarks.
     - Retrieve the data.

     ![Apptio Source configuration to integrate with IBM Apptio Costing project](../../resources/images/it%20benchmarking_images/path1-benchmarking.png)

     Once connected, Benchmarking will connect to the Production environment of your Costing
     project and
     - Pull annual IT cost by Cost Pool.
     - Pull annual IT cost by Resource Tower and, where mapped, by Sub-Tower.

     Note: Ensure the Costing project uses TBM Cost Pools and Resource Towers aligned to the
     selected TBM version defined in Interactive Benchmarking.
   - **PATH 2** Manual cost input (if Costing is not ready or used)

     If you cannot yet integrate
     with Costing, open the Configuration area and
     - Manually enter data into Cost Data section.
     - Manually enter data into Volumes section.
     - Manually enter data into the FTEs section.

       ![Interactive Benchmarking Configuration – Cost Pools, Resource Towers Volumes, & FTEs](../../resources/images/it%20benchmarking_images/manual-cost-input-benchmarking.png)

     Regardless of integration method:
     - Confirm that the total IT cost loaded into Benchmarking reconciles to Finance for the selected
       year.
     - Confirm that all major towers you expect actually have non-zero values.
     - If any values are missing or you feel deserve an override, enter the values manually and save
       them before proceeding.
4. **Run a basic benchmark comparison**

   Now, test the configuration produces usable
   results.

   In Interactive Benchmarking:
   - Choose up to three peer groups that reflects your comparison set.
     - Similar industry.
     - Similar revenue band.
     - Appropriate region.
   - Open the Industry Benchmarks view.
     - Check metrics like IT spend as percentage of revenue or IT spend per employee.
     - Verify your organization’s actuals metric appears on the chart.  
       Hint: Look for the
       dotted lines.

       ![Industry Benchmarks – IT Spend as % of Revenue](../../resources/images/it%20benchmarking_images/benchmarking-views.png)
   - Select “IT OpEx Benchmarks” from the report collection menu.
     - Look at distributions by Cost Pool and by Resource Tower.
     - Confirm the values look plausible and Resource Towers are present.

       ![IT OpEx Benchmarks – By Cost Pool](../../resources/images/it%20benchmarking_images/itopex-benchmarking.png)
   - If Infrastructure cost and volumes were provided, open the “Infrastructure Benchmarks” from the
     report collection menu and review unit costs such as cost per server or cost per TB and FTE efficiency.
     - You are not tuning yet, only checking for absurd outliers caused by unit or volume issues.

       ![#: Infrastructure Benchmarks – Unit Costs](../../resources/images/it%20benchmarking_images/infrastructure-benchmarking-unit-cost.png)

     At this step, you are looking for obvious problems:
     - Blank charts where there should be data.
     - Numbers that are orders of magnitude off.
     - Peer filters that do not match the story you want to tell.

     If something looks broken, note it and later use Configuration Guide and Troubleshooting
     & FAQ sections to fix or troubleshoot.
5. **Bookmark and share initial views**

   Once you have a few views that make sense:
   - Capture a small set of screenshots or exports for your first stakeholder conversation.

     Minimum
     starter pack:
     - One Industry benchmark view that shows IT spend vs revenue.
     - One IT OpEx distribution view that shows cost structure by Cost Pool or Resource Tower.
     - One Infrastructure view, if available, that shows a tower where you suspect interesting
       gaps.

     The point is not to be perfect. The point is to have a small, consistent set of views
     you can come back to and iterate on.
