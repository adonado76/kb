---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Studio Issues"
breadcrumb:
  - "TBM Studio"
  - "Troubleshooting and Support"
  - "Common Issues and Solutions"
source_path: "studio/new-uc/ts-support/ds-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Studio Issues

## Data Won't Load or Upload Fails

**Symptoms:**

- File upload fails with validation error
- Data table shows zero rows after upload
- Upload appears to hang or time out

**Possible Causes:**

- File format doesn't match expected schema
- Missing required columns
- Data type mismatches
- File encoding issues
- File exceeds size limits

**Solutions:**

1. **Verify file format and content** - Confirm the file has content and is correctly
   delimited. Check that column headers match the expected schema. Ensure numeric columns
   contain only numeric values.
2. **Check column validation** - Open the data table and review any validation badges
   (red numbers next to table name). Click on the badge to see specific validation errors.
   Correct data type mismatches in your source file.
3. **Verify date partitions** - Ensure data for the correct time period is being
   uploaded. Check that date columns are in the expected format.

**Prevention Tips**

- Always preview data before uploading
- Use the data validation step to catch errors early
- Maintain consistent file naming and format conventions

*Related: Data Architecture (Section 4.2), Upload Data (Section 3.1.1)*

## Transform Table Not Calculating

**Symptoms:**

- Transform shows stale data
- Downstream model objects show incorrect values
- Error badge appears on transform table

**Solutions:**

1. **Save and check for errors** - Click Save on any modified transform tables. Look for
   error badges (red numbers) next to the table name.
2. **Verify document status** - Check if the document is checked out. If checked out by
   another user, coordinate with them.
3. **Review transform step logic** - Open each transform step and verify formulas. Check
   for circular references.
