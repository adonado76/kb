---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Benchmarking FAQ"
breadcrumb: []
source_path: "it-benchmarking/faq.html"
images:
  - "resources/images/it_benchmarking_images/itb_faq.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Benchmarking FAQ

**Q. What expenditures do I exclude from IT spend overall?**

You need to exclude two types of charges for Benchmarking :

1. Industry specific hardware or software, for example, robotic manufacturing equipment:

- Equipment built or purchased for non-data-processing purposes, but which has computerized
  components, such as robotic manufacturing machines, specialized stock trading end-user devices, such
  as trader headsets, automated teller machines, specialized point-of-sale devices, scanners, and
  blood pressure monitors and sensors on a supervisory control and data acquisition (SCADA) system.
- Appliance-like or proprietary data processing equipment that has a single (typically
  industry-vertical) purpose that cannot be used for other general purposes, such as a computer that
  can only control the flow of electricity through the power grid. Since it cannot be repurposed, it
  is not included in our model. Note that other systems that gather data from this type of computer
  that can be used for other purposes are not considered operational technology, and therefore, are
  within the scope of our model.

2. Spend that is outside of the control of IT, for example, shadow IT

- Costs for technology or services that are resold, such as salaries for developers involved in
  building commercially packaged software or IT-skilled employees who provide services for the
  organization's external clients.
- Internal "cross charges" and corporate allocations related to large, significant, or unusual
  one-time expenses, such as reductions in workforce, redundancy, re-locations, retirement, human
  resources, and chairperson salary.
- Business data subscriptions and services, such as Bloomberg, even if they are managed by the IT
  organization.
- Business process outsourcing services (BPO) where organizations outsource entire business
  functions, such as payroll or benefits management. This includes cases where the BPO vendor provides
  access to software, and also guarantees that the outcomes of their services will meet business
  requirements, such as tax and withholding regulations. Vendor-provided software as a service (SaaS),
  which only guarantees that the software will perform as specified, is within scope of IT spend.
  Traditional outsourcing of IT functions, such as servers and email, are also within scope.
- Shadow IT, which is standard IT spend that is outside the control and support of the IT
  department.

**Q. What expenditures do I exclude for Infrastructure Benchmarks?**

The data in our Infrastructure Benchmark comes from ISG. To ensure like for like comparison, do
not include any of the below 4 cost pool expenses in any of your costs when comparing your
performance to the Infrastructure Benchmark metrics:

- Facilities and Power
- Internal Services
- Other
- Telecom

Note: Map all of the Telecom cost pool expenses to Network – Transport as this is where ISG analyzes
them.

![Image](../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/itb_faq.jpg)

**Q. Does Network – Transport include all Telecom cost pool expenses in the Infrastructure
Benchmarks from ISG?**

Yes. ISG maps all expenses related to cost pool Telecom to Network – Transport. Do not include
Telecom cost pool expenses for any other infrastructure benchmarks.

**Q. How do I account for depreciation and amortization (D&A)?**

Industry Benchmarks: The performance metrics (sourced from Rubin) include cash outlays only. The
spend metric should include all Capital Expenditures and Operating Expenditures for the current
fiscal year. Do not include D&A in Industry Benchmarks.

IT OpEx Benchmarks: The performance metrics (sourced from Apptio data) include operational
expenditures only. Do include D&A expenses but do not include capitalized expenses in IT OpEx
Benchmarks

Infrastructure Benchmarks: The performance metrics (sourced from ISG) include cash outlays as
well as depreciation. Do include D&A expenses as well as capitalized expenses in Infrastructure
Benchmarks.

Note: If you have configured Benchmarking in Cost Transparency your D&A expense schedule will
get pulled in automatically. If you are using Interactive Benchmarking, your D&A expenses are
estimated using a three year straight line depreciation schedule of your capital expenditures.

**Q. How are public cloud costs accounted for in Opex and infra BM?**

Industry Benchmarks: All public cloud expenditures are included in IT spend.

OpEx Benchmarks: All public cloud expenditures are included in the cost pool Outside Services
and are mapped up to IT Tower and Applications subsequently.

Infra Benchmarks: Infrastructure benchmarks are for on-prem expenses only. All public cloud
expenses need to be excluded. This is handled automatically in the Apptio cost model by assigning
all cloud costs to Delivery = “Public Cloud” and excluding these costs from the tower level
infrastructure costs that are compared to the Infra Benchmarks.

**Q. Can I benchmark specific BUs or regions separately?**

The best way to benchmark individual BUs or Regions is to populate BU/Region specific financials
and unit volumes in Interactive Benchmarking. The software provides you the option to adjust
archetypes or compare to different industries as you see fit.

Note: There is no functionality to have data persist for different BUs/Regions. You will have to
update the data as you analyze different BUs/Regions. Customers can modify the Costing Standard
Benchmark reports to show and compare different benchmarks based on BU/Region. This requires custom
reporting to create these views and is not provided out of the box.

**Q. Do I include contractor spend?**

Yes. The only reason to not include contractor spend is if it is part of Business Process
Outsourcing services (BPO).

**Q. Where do I allocate industry specific IT spend, such as MRI machines, assembly line
robots and their software, infusion pumps andPOS devices in retail?**

Industry specific IT spend is not included in IT cost benchmarks and needs to be excluded.

**Q. How do I handle the case when my underlying cost data comes in different currencies?**

You will first want to consolidate the various currencies of the cost data into a single
currency view. You can then map your single-currency cost data to the benchmarks as detailed in the
configuration guide. By default, the Apptio cost model requires a “base currency” to be configured
to standardize all costs in the cost models. Different currencies can be shown through the UI
through preferred multi-currency settings.

Note: All major currencies are supported.

**Q. Where do I allocate business data and information subscriptions?**

Business data and information subscriptions need to be allocated to the cost pool  Other
 . However, IT cost benchmarking does not include business data and information subscriptions
and you need to exclude any such expenses for like for like comparisons.

**Q. Can I change the metrics the benchmarks are measured in, for example, divide by
devices rather than users?**

No. All available KPIs are surfaced in the product. We are always looking to expand the KPIs we
are surfacing though so please reach out to your customer success or account manager and share the
views and metrics that you are interested in.

**Q. Do I include IT expenses related to change/grow and transform in the benchmarking?**

Yes. Any operational expenses are included in all three Industry, IT OpEx and Infrastructure
Benchmarks. Capital expenditure is not included in IT OpEx benchmarks .

**Q. If you change the volumes/quantities in the Infrastructure Benchmarks screen, is that
supposed to overwrite the volumes/quantities that are pulled from CT?**

No, cost and volume changes made directly in the Infrastructure Benchmark application are unique
to Interactive Benchmarking. They are not sent to the Costing Standard y cost model. However, the
tower / sub-tower costs and the associated unit volumes in the IT Resource Towers object in Costing Standard can be integrated with Interactive Benchmarks.

**Q. When selecting the period to extract the data from CT into benchmarking, does it use
the YTD figures and then annualize, or does it annualize based only on the month selected?**

The Costing Standard Benchmarking data uses a running, 12-month total for the annual costs and
for the unit costs.

**Q. What should be included in the Database sub-tower?** 

- Include your server-based database management systems (DBMS) such as Oracle and MS SQL.
- Do not include hardware expenses in data management as these get mapped to compute and storage.
- Do include personnel expenses for operational and second level support including administration,
  configuration and updates.
- Also include any database software as well as managed services for server databases

**Q. Where is the benchmarking data coming from?**

The three different segments of benchmarking rely on three different data sources:

- Industry Benchmarks are sourced from Rubin Worldwide
- IT OpEx Benchmarks are sourced from Apptio
- Infrastructure Benchmarks are sourced from ISG

**Q. How can I ensure like for like comparisons?**

There are various ways you will want to ensure comparability:

Industry Benchmarks: Adjust for

- Industry
- Region
- Size

IT OpEx Benchmarks: Adjust for operating model archetypes for both

- Applications (build vs buy)
- Cost pools (people, hardware, software, vendor)

Infrastructure Benchmarks: Adjust for

- Volume
- Region
- Industry

Note: For infrastructure benchmarks, volume is the biggest driver due to economies of scale; Region
and Industry have a minor impact.

**Q. How does the product work with CT and how do I configure it appropriately for
example, changing volumes in IBX feeds through to CT?**

[See the section on configuration](configuration/config-guide.html)  to learn how
to set up benchmarking

Any choices you make in Interactive Benchmarking do not overwrite volume or cost data in CT
