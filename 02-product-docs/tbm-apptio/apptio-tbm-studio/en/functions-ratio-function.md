---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Ratio function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Ratio function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/ratio.html"
images:
  - "03-media/apptio-tbm-studio/aug354.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Ratio function

*Applies to : TBM Studio 12.0 and later*

Use in allocation advanced formulas to handle situations where the weighting column values are zero. The function returns a value of 1.

## Where to use

- Allocation source formulas
- In an Advanced allocation formula in a model

## Syntax

Ratio({column},~{column})

## Arguments

column

The name of the column in the target object that will be used to weight the allocation.

The "~" is an application operator that tells the application to sum the values in the column.

## Return type

The number 1.

## Example

In this example, the costs from all data centers are allocated to servers based on matching the data center names in the Data Centers object with the data center names in the Servers object. The allocation is weighted by the size of the servers in each data center based on an advanced formula. Data centers with no match in the Servers object are not allocated.

## Formula

The advanced formula used is:

=SOURCE*({Server.Size)/Sum(Size){Servers.Size},~{Servers.Size})

SOURCE represents the value of the Data Centers object. It is "filtered" by the Data-based reference option selected in the To section of the Properties dialog. Servers.Size represents the value in the Size column in the Servers object unit table. The "~" is an operator that tells the application to sum the values in the Size column.

## Data calculations

The following tables show how the allocation is calculated. The allocation is based on matching the data center names in the Data Centers table with the data center names in the Servers table. Allocations are spread across the servers in a data center based on the relative size of the servers. For example, 1/5 of the $100,000 associated with the Boston data center is allocated to Server1 and 4/5 is allocated to Server2. The Seattle data center costs are not allocated because there are no servers in the Seattle data center.

## Data Centers table

| Server | Data center | Size | Allocation |
| --- | --- | --- | --- |
| Server1 | Boston | 1 | $100,000 x 1/5 = $20,000 |
| Server2 | Boston | 4 | $100,000 x 4/5 = $80,000 |
| Server3 | Dallas | 1 | $50,000 x 1/3 = $16,667 |
| Server4 | Dallas | 2 | $50,000 x 2/3 = $33,333 |
| Server5 | Chicago | 8 | $10,000 x 8/8 = $10,000 |
| 5 servers |  | 16 | $160,000 |

## Servers table

| Data Center | Lease | Capacity |
| --- | --- | --- |
| Boston | $100,000 | 10 |
| Dallas | $50,000 | 10 |
| Chicago | $10,000 | 10 |
| Seattle | $40,000 | 10 |
| Total | $200,000 | 40 |

## Handling zero values

If there is at least one value in the weighting column that is not zero, the application will calculate the values correctly. If all the values in the weighting column are zero, the application will not be able to calculate the values. In these instances, you can use the Ratio function to effectively set the calculated values to 1. The result is that the allocated value will be spread evenly across the target units.

In the example above, if the Size values were all zero, then you would use the following advanced formula:

=SOURCE*Ratio({Servers.Size},~{Servers.Size})

Note that the columns are entered as arguments for the function, not as a ratio. The arguments are separated by a comma.
