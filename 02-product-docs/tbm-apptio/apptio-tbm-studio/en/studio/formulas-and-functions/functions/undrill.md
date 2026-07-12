---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Undrill function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/undrill.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Undrill function

**Applies to**: TBM Studio 12.0 and later

Returns the value for a metric at the top level of a model.

The value returned for a metric is based on the level to which you have drilled in a model. If
you are several levels down in a model, but want the value for the metric at the top level in the
model, you can use the Undrill function.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic text

## Syntax

`Undrill(metric)`

## Arguments

*metric*

Either a modeled or calculated metric.

## Return type

Number

## Examples

Assume you have a model that includes several business units, and server costs have been
allocated to each business unit. If you drill down several levels of reports into one of the
business units, let's say Retail, you will see the server costs for Retail. But, what if you wanted
to show the percentage of server costs allocated to Retail.

You can use the Undrill function to return the total server costs for all business units and
divide that into the Retail server costs. You could add a column to the report table to hold the
undrilled cost using the following:

`=Undrill(Cost)`
