---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "SumIfHierarchy"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "SumIfHierarchy"
source_path: "SSWRJM/studio/formulas-and-functions/functions/sumifhierarchy.html"
images:
  - "03-media/apptio-tbm-studio/aug346.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# SumIfHierarchy

*Applies to : TBM Studio 12.0, 12.1*

The SumIfHierarchy function is used to calculate the cost of a service based on the cost of its sub-services. The function is used to calculate the value of a column added to a service cost transform table. The function requires a set, known hierarchy that does not contain any circular references. The hierarchy can have an unlimited number of levels.

## Where to use

- Date sets

## Syntax

For demand, use the following syntax:

SumIfHierarchy(Service,Consumes,Quantity)

For price, use the following syntax:

SumIfHierarchy(Consumes,Service,Quantity,BasePrice)

## Arguments

Service

The name of the column containing the name of the service.

Consumes

The name of the column containing the name of the sub-service.

Quantity

The name of the column containing the number of sub-services consumed by the service.

BasePrice

The name of the column containing the price assigned to the sub-services.

## Return type

Number

## Example

The table below illustrates the use of the SumIfHierarchy function to calculate service demand and service price for workstations. Base prices are entered for each sub-service, for example, monitor, keyboard, and mouse. Notice that a base price is not entered for the Standard Software Suite sub-service because it is composed of other sub-services, specifically Microsoft Office, Microsoft Visio, and VPN. The total cost for desktop and laptop workstations is provided in the last two rows of the table:

The equation for the Service Demand column is:

=SumIfHierarchy(Service,Subservice,Quantity)

The equation for the Service Price column is:

```
=SumIfHierarchy(Subservice,Service,Quantity,Base
          Price)
```
