---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Quick Start Guide"
breadcrumb:
  - "TBM Studio"
  - "Getting Started"
source_path: "studio/new-uc/getting-started/qsg.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Quick Start Guide

## Your First Cost Model

|  |  |
| --- | --- |
| **Content Type** | Tutorial |
| **Target Audience** | New Users |
| **Time to Complete** | 10 minutes |
| **Prerequisites** | Access to a TBM Studio project (Development environment), Basic understanding of IT cost concepts, Sample cost data file (Excel or CSV format) |

## What You'll Accomplish

In this 10-minute tutorial, you'll experience the complete TBM Studio workflow by:

- Uploading your first cost data file
- Creating a simple data transformation
- Building a basic cost allocation
- Generating your first cost report

By the end, you'll see how IT costs flow from raw data through allocations to actionable
reports.

## Before You Begin

Make sure you have:

- A TBM Studio account with access to a project
- A small sample cost data file ready to upload

Note: While a standardized sample data template is recommended for this tutorial, one may not
currently be available in your project. You can use any simple cost data file (Excel or CSV)
with these minimum columns: Cost Source (e.g., "Payroll", "Cloud Services"), Department or
Business Unit, Amount (numeric cost value), and Month or Date.

## Step 1: Access TBM Studio and Navigate to Data Studio

***Time:*** *1 minute*

1. Log into TBM Studio using your credentials
2. From the **Projects** pane, select your assigned project
3. Ensure you're in the **Development** environment (shown in the top navigation)
4. In the **Project Explorer** pane on the left, expand **Data Studio**

**Expected Result:** You see the Data Studio folder structure with existing tables (if
any) in your project.

## Step 2: Upload Your Cost Data

***Time:*** *2 minutes*

1. Click the **Home** tab in the toolbar
2. Click **New** → **Table**
3. Enter the table name: *"My First Cost Data"*
4. Enter a category: *"Tutorial"* (this helps organize tables)
5. Click **OK**

The table is created and the transform pipeline opens automatically.

1. In the **Source** step, click **File Upload**
2. Either drag your data file into the upload area, or click to browse and select it
3. TBM Studio automatically detects:
   - Header row (usually row 1)
   - Column types (Label, Numeric, State/Date)
4. Review the **Import** step settings:
   - Confirm the **Start import at row** is set correctly (typically row 2 for
     data)
   - Review the **Columns** list - verify column types are detected correctly
   - For any numeric cost columns, ensure they show type "Number"
5. Click **Save** on the Home tab
6. Click the **Table** step in the pipeline to preview your data

**Expected Result:** You see your uploaded data displayed in a table with all rows and
columns visible. Column headers match your file, and data types are correctly
identified.

**Common Issues** - If numbers appear as text, click the column in the Import step and
change the type to "Number". If you see errors, check that your file has no blank rows at
the top.

## Step 3: Create a Simple Transform

***Time:*** *2 minutes*

Now you'll add a simple transformation to clean or enhance your data.

1. In the **Transform Steps** pipeline, click **Add Step** (+ icon)
2. Select **Filter** from the step types
3. Configure the filter:
   - Click **Add Condition**
   - Select your cost amount column
   - Set operator to **>** (greater than)
   - Enter value: **0** (to exclude zero or negative values)
4. Click **OK**
5. Click the **Table** step to preview the filtered results

**Expected Result:** Your table now shows only rows where cost is greater than zero. The
row count may be lower than the original upload.

Tip: This is a basic example. In real projects, you might add steps to join data,
map values, or apply formulas.

## Step 4: Add Your Table to the Model

***Time:*** *2 minutes*

To allocate costs, your table must be part of the cost model.

1. In the transform pipeline, click **Add Step**
2. Select **Model** as the step type
3. Click the new **Model** step in the pipeline

The Single-Table Model view opens, showing your table in the center.

1. Click your table (the rectangle in the center)
2. In the **Rows** panel, check the key columns that identify unique cost items (e.g.,
   Cost Source, Department)
3. In the **Drivers** panel on the left, click **Add Unit Driver**
4. Configure the unit driver:
   - **Add To**: Select the cost metric (usually "Cost")
   - **Using**: Select **Column**
   - **Column**: Select your amount/cost column
5. Click **OK**
6. Click **Save** on the Home tab
7. Click **Check In** to make your changes available

**Expected Result:** Your table is now a model object that can receive or send cost
allocations. You see your cost totals in the model view.

**Understanding What Happened:** You just created a "unit driver" - this tells the model
where the cost values come from in your table.

## Step 5: Create a Basic Allocation (Optional)

***Time:*** *2 minutes*

Note: This step requires a second table or object in your model. If your project has an
existing model object (like "Business Units" or "Applications"), you can create a simple
allocation.

**If a target table exists:**

1. In the Model view, click **Add Allocation** in the right panel
2. Configure the allocation:
   - **To**: Select the target object (e.g., "Business Units")
   - **Driver**: Select a matching column that exists in both tables (e.g.,
     Department)
3. Click **Preview** to see how costs will allocate
4. Click **Save**

**Expected Result:** You see costs flowing from your source table to the target table
based on the driver you selected.

**If no target exists:** Skip this step for now. You've already accomplished the core
data upload and model integration. Your next step would be to work with an administrator to
set up allocation targets.

## Step 6: Generate Your First Report

***Time:*** *3 minutes*

Now you'll create a simple report to visualize your data.

1. In the **Project Explorer**, expand **Reports**
2. Click **Home** tab → **New** → **Report**
3. Enter report name: *"My First Cost Report"*
4. Enter description: *"Tutorial - First cost report"*
5. Select **Viewable By**: Choose appropriate permissions (or keep default)
6. Select layout: **Standard (1024px)** with **Add Heading** checked
7. Click **OK**

The report editor opens.

1. From the **Component Configuration** panel, drag a **Table** onto the report
   canvas
2. Configure the table:
   - **Data Source**: Select your model object (e.g., "My First Cost Data")
   - **Rows**: Drag your key dimension (e.g., Cost Source or Department) to the Rows
     area
   - **Values**: Drag your cost metric to the Values area
3. The table populates with your data
4. Add a **Slicer** for interactivity:
   - Drag **Slicer** component above your table
   - Configure it to filter by one of your dimensions (e.g., Department)
5. Click **Save**
6. Click **Check In**

**Expected Result:** You have a functioning report that shows your costs by the
dimension you selected. The slicer allows users to filter the data interactively.

Tip: Click values in the slicer to filter the table - you've just created
interactive reporting!

## Verify Your Success

You've successfully completed the quick start if you can:

- See your uploaded data in Data Studio
- View your table in the Model with a unit driver configured
- Access your report and see cost data displayed
- Use the slicer to filter the report

**Congratulations!** You've just completed the full TBM Studio workflow: Data → Model →
Report.

## What's Next?

Now that you understand the basic workflow, explore these next steps:

**Immediate Next Steps**

- **Learn the Interface**: Review Section 1.4 (Navigate the Interface) to understand the
  workspace better
- **Understand Core Concepts**: Read Section 1.2 (Core Concepts) for deeper understanding
  of tables, models, and metrics

**Building Your Skills**

- **For Data Work**: See Section 3.1 (Work with Data) for advanced upload and
  transformation techniques
- **For Cost Modeling**: See Section 3.2 (Build Cost Models) to create multi-tier
  allocations
- **For Reporting**: See Section 3.3 (Create Reports) to build sophisticated
  visualizations

**Role-Based Paths**

- **Business Analysts**: Section 2.1 (Learning Path for Business Analysts)
- **IT Finance Teams**: Section 2.2 (Learning Path for IT Finance)
- **Administrators**: Section 2.3 (Learning Path for Administrators)

## Get Help

- If you encounter errors, see Section 7.1 (Common Issues & Solutions)
- For detailed reference on any feature, see Section 5 (Reference)

## Troubleshooting

| **Issue** | **Solution** |
| --- | --- |
| **Can't upload file** | Check file format (must be .xlsx, .xls, or .csv) and ensure file doesn't have special characters in the name (use letters, numbers, underscores, and hyphens only) |
| **Columns showing as wrong type** | In the Import step, manually change the column type by clicking the column and selecting the correct type from the dropdown |
| **Don't see Model step option** | Make sure you've saved your table first. The Model step can only be added after the table is created |
| **Report shows no data** | Ensure you've checked in your table and model changes. Reports only show data from checked-in objects |
| **Can't check in** | You must save your changes first (click Save on the Home tab), then you can check in |
| **Update Workspace** | Check the ribbon bar Home tab to see if the ‘Update Workspace’ is active. If active, click the icon to refresh your workspace to ensure you view the latest updates. |
