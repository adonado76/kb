---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Frequently Asked Questions"
breadcrumb:
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
  - "Frequently Asked Questions"
source_path: "SSIU957/it-benchmarking/troubleshooting/faq.html"
images:
  - "03-media/apptio-benchmarking/cost-pool-expenses.jpg"
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Frequently Asked Questions

## Q. How exact are these benchmarks?

A. They’re statistically solid, not penny-accurate. The benchmarks tell us whether we’re low, typical, or high compared to peers and where to focus questions. We still rely on our own detailed data for final decisions.

## Q. Can we see who the peers are?

A. No. Participants are anonymous by design. We only see aggregated distributions (medians, quartiles, bands), not named organizations.

## Q. Does being above median mean we’re inefficient?

A. Not automatically. It means we spend more than the typical peer on that metric. That might be inefficiency, or it might reflect deliberate choices like higher resilience, tighter regulation, or a different sourcing model. The benchmark tells us where to investigate, not that something is automatically wrong.

## Q. Why is this number different from my team’s number?

A. Because we’re likely using a different scope or definition. Benchmark metrics use standard TBM-aligned definitions so they’re comparable across organizations. When we see differences from internal numbers, we reconcile the scope first, then decide which metric to use for which purpose.

## Q. Can we change how the benchmark is calculated?

A. No. Benchmark definitions are fixed so everyone is comparing the same thing. We can create custom internal metrics in Costing if we need to look at the data differently, but that’s separate from the external benchmark.

## Q. I have a problem I’m unable to resolve on my own. How can I request help?

A. Support tickets can be submitted and reviewed on IBM’s Help Center . Additionally, customers are welcome to visit Community where fellow IBM Apptio customers and IBMers collaborate and share knowledge.

## Q. I have an idea to improve Interactive Benchmarking. How do I submit the idea to IBM?

A. Customers are welcome to submit their ideas via IBM Ideas portal .

## Q. Can I access benchmark details from previous years?

A. Not with Interactive Benchmarking. However, the Costing-enabled benchmark reports can provide the information (if integrated with Costing).

## Q. If integrated with Costing, from which Costing project’s environment is IT spend data retrieved?

A. The Production environment only.

## Q. Do I include spending outside the control of the IT organization?

A. No. Do not include any spending including “Shadow IT” controlled by other areas of your larger enterprise.

## Q. Which cost pools should I exclude from infrastructure benchmarking?

A. Exclude the following:

- Facilities and Power
- Telecom
- Internal Services
- Other

## Q. Where do I include expenses belonging to the Telecom cost pool?

A. Assign the Telecom cost pool expenses to the “Transport” Sub-tower.

## Q. Are there infrastructure benchmark metrics for the “Facilities and Power”, “Internal Services”, or “Other” cost pools?

A. No.

## Q. How are public cloud costs accounted for in OpEx and infrastructure benchmarking metrics?

A. In OpEx benchmarking, public cloud costs are included in the Outside services cost pool. In Industry benchmarking, public cloud costs are included in IT spend.

## Q. Do I include contractors?

A. Yes.

## Q. Where do I allocate business data or information subscriptions?

A. Allocate these to the Other cost pool.

## Q. What can I do if I would like to look at different KPIs for a specific area, for example, to divide by devices rather than users?

A. All available KPIs are surfaced in the product.

## Q. What expenditures do I exclude from IT spend overall?

1. Industry specific hardware or software, for example, robotic manufacturing equipment: Equipment built or purchased for non-data-processing purposes, but which has computerized components, such as robotic manufacturing machines, specialized stock trading end-user devices, such as trader headsets, automated teller machines, specialized point-of-sale devices, scanners, and blood pressure monitors and sensors on a supervisory control and data acquisition (SCADA) system. Appliance-like or proprietary data processing equipment that has a single (typically industry-vertical) purpose that cannot be used for other general purposes, such as a computer that can only control the flow of electricity through the power grid. Since it cannot be repurposed, it is not included in our model. Note that other systems that gather data from this type of computer that can be used for other purposes are not considered operational technology, and therefore, are within the scope of our model.
1. Spend that is outside of the control of IT (e.g., “Shadow IT”). Costs for technology or services that are resold, such as salaries for developers involved in building commercially packaged software or IT-skilled employees who provide services for the organization's external clients. Internal "cross charges" and corporate allocations related to large, significant, or unusual one-time expenses, such as reductions in workforce, redundancy, re-locations, retirement, human resources, and chairperson salary. Business data subscriptions and services, such as Bloomberg, even if they are managed by the IT organization. Business process outsourcing services (BPO) where organizations outsource entire business functions, such as payroll or benefits management. This includes cases where the BPO vendor provides access to software, and also guarantees that the outcomes of their services will meet business requirements, such as tax and withholding regulations. Vendor-provided software as a service (SaaS), which only guarantees that the software will perform as specified, is within scope of IT spend. Traditional outsourcing of IT functions, such as servers and email, are also within scope. Shadow IT, which is standard IT spend that is outside the control and support of the IT department.

## Q. What expenditures do I exclude for Infrastructure Benchmarks?

A. The data in our Infrastructure Benchmark comes from ISG. To ensure like for like comparison, do not include any of the below 4 cost pool expenses in any of your costs when comparing your performance to the Infrastructure Benchmark metrics:

- Facilities and Power
- Internal Services
- Other
- Telecom

![Telecom cost pool expenses to Network](../../resources/images/it%20benchmarking_images/cost-pool-expenses.jpg)

## Q. Does Network – Transport include all Telecom cost pool expenses in the Infrastructure Benchmarks from ISG?

A. Yes. ISG maps all expenses related to cost pool Telecom to Network – Transport. Do not include Telecom cost pool expenses for any other infrastructure benchmarks.

## Q. How do I account for depreciation and amortization (D&A)?

Industry Benchmarks: The performance metrics (sourced from Rubin) include cash outlays only. The spend metric should include all Capital Expenditures and Operating Expenditures for the current fiscal year. Do not include D&A in Industry Benchmarks.

IT OpEx Benchmarks: The performance metrics (sourced from Apptio data) include operational expenditures only. Do include D&A expenses but do not include capitalized expenses in IT OpEx Benchmarks

## Q. How are public cloud costs accounted for in Opex and infra BM?

A. Industry Benchmarks: All public cloud expenditures are included in IT spend.

OpEx Benchmarks: All public cloud expenditures are included in the cost pool Outside Services and are mapped up to IT Tower and Applications subsequently.

Infra Benchmarks: Infrastructure benchmarks are for on-prem expenses only. All public cloud expenses need to be excluded. This is handled automatically in the Apptio cost model by assigning all cloud costs to Delivery = “Public Cloud” and excluding these costs from the tower level infrastructure costs that are compared to the Infra Benchmarks.

## Q. Can I benchmark specific BUs or regions separately?

The best way to benchmark individual BUs or Regions is to populate BU/Region specific financials and unit volumes in Interactive Benchmarking. The software provides you the option to adjust archetypes or compare to different industries as you see fit.

## Q. Do I include contractor spend?

A. Yes. The only reason to not include contractor spend is if it is part of Business Process Outsourcing services (BPO).

## Q. Where do I allocate industry specific IT spend, such as MRI machines, assembly line robots and their software, infusion pumps and POS devices in retail?

A. Industry specific IT spend is not included in IT cost benchmarks and needs to be excluded.

## Q. How do I handle the case when my underlying cost data comes in different currencies?

## Q. Where do I allocate business data and information subscriptions?

A. Business data and information subscriptions need to be allocated to the cost pool Other . However, IT cost benchmarking does not include business data and information subscriptions and you need to exclude any such expenses for like for like comparisons.

## Q. Can I change the metrics the benchmarks are measured in, for example, divide by devices rather than users?

A. No. All available KPIs are surfaced in the product. We are always looking to expand the KPIs we are surfacing though so please reach out to your customer success or account manager and share the views and metrics that you are interested in.

## Q. Do I include IT expenses related to change/grow and transform in the benchmarking?

A. Yes. Any operational expenses are included in all three Industry, IT OpEx and Infrastructure Benchmarks. Capital expenditure is not included in IT OpEx benchmarks .

## Q. If you change the volumes/quantities in the Infrastructure Benchmarks screen, is that supposed to overwrite the volumes/quantities that are pulled from CT?

A. No, cost and volume changes made directly in the Infrastructure Benchmark application are unique to Interactive Benchmarking. They are not sent to the Costing Standard y cost model. However, the tower / sub-tower costs and the associated unit volumes in the IT Resource Towers object in Costing Standard can be integrated with Interactive Benchmarks.

## Q. When selecting the period to extract the data from CT into benchmarking, does it use the YTD figures and then annualize, or does it annualize based only on the month selected?

A. The Costing Standard Benchmarking data uses a running, 12-month total for the annual costs and for the unit costs.

## Q. What should be included in the Database sub-tower?

A. Include your server-based database management systems (DBMS) such as Oracle and MS SQL.

Do not include hardware expenses in data management as these get mapped to compute and storage.

Do include personnel expenses for operational and second level support including administration, configuration and updates.

Also include any database software as well as managed services for server databases

## Q. Where is the benchmarking data coming from?

- Industry Benchmarks are sourced from Rubin Worldwide
- IT OpEx Benchmarks are sourced from Apptio
- Infrastructure Benchmarks are sourced from ISG

## Q. How can I ensure like for like comparisons?

There are various ways you will want to ensure comparability:

Industry Benchmarks Adjust for:

- Industry
- Region
- Size

IT OpEx Benchmarks

Adjust for operating model archetypes for both:

- Applications (build vs buy)
- Cost pools (people, hardware, software, vendor)

Infrastructure Benchmarks

Adjust for:

- Volume
- Region
- Industry

## Q. How does the product work with CT and how do I configure it appropriately for example, changing volumes in IBX feeds through to CT?

A. See the section on configuration to learn how to set up benchmarking. Any choices you make in Interactive Benchmarking do not overwrite volume or cost data in CT
