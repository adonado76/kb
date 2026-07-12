---
capability_id: finops.optimize.rate-optimization
domain: finops.optimize
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - cloudability-premium
status: draft-pilot
generated_from:
  - 02-product-docs/cloudability-premium/en/product/rightsizing-for-aws-ec2.md
  - 02-product-docs/cloudability-premium/en/product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.md
last_updated: "2026-07-01"
---
# Rate Optimization — How IBM Cloudability Premium Addresses This FinOps Capability

## The capability

Rate Optimization, within the Optimize domain of the FinOps Framework, is about reducing the
unit cost of cloud resources already in use — through rightsizing, commitment-based discounts
(Reserved Instances, Savings Plans), and eliminating idle spend — without compromising
performance or reliability.

## How IBM Cloudability Premium covers it

Cloudability Premium provides a **Rightsizing dashboard** that surfaces two types of
recommendations per resource: *rightsize* (move to a better-fit instance type) and
*terminate* (the resource is predominantly idle). Recommendations are available across the
major cloud providers and services organizations typically run in production: AWS (EC2, RDS,
EBS, Lambda, Auto Scaling Groups, S3), Azure (Compute, Disks, SQL, Blob Storage), Google Cloud
(GCE, Cloud Storage, GKE MIG), and OCI (VMs).

A key design decision that matters for enterprise conversations about savings credibility: each
recommendation can be evaluated on two different cost bases —

- **On-Demand basis**: compares current vs. recommended instance using pure on-demand pricing,
  ignoring any existing Reserved Instance or Savings Plan coverage. This maximizes the number of
  recommendations surfaced and removes the noise of commitment-based discounts from the analysis.
- **Effective basis**: incorporates the historical impact of RIs/SPs already in place, so the
  comparison reflects what the organization is actually paying today. This is the more
  conservative option — savings reported this way tend to be lower, but more defensible in front
  of Finance.

Recommendations are backed by a Rightsizing Explorer view that lets teams group, filter, and
navigate opportunities across the entire cloud estate from a single screen, and each dashboard
exposes KPIs (total spend, estimated idle savings, estimated rightsize savings, estimated
optimized spend) that can be dropped directly into a savings-tracking narrative for leadership.

## Why this matters in a client conversation

Most rate-optimization tools stop at "here's a cheaper instance type." Cloudability Premium's
on-demand vs. effective cost basis distinction is the detail that lets a FinOps or ITFM lead
answer the follow-up question every CFO asks: *"is this savings number real, or does it assume
we throw away commitments we already paid for?"* That's a concrete differentiator worth having
ready for an RFP response or a capability-mapping slide.

## Source documents

- Rightsizing for AWS EC2 — `02-product-docs/cloudability-premium/en/product/rightsizing-for-aws-ec2.md`
- Rightsizing overview — `02-product-docs/cloudability-premium/en/product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.md`

*Nota: este brief es un piloto en ingles para validar el formato del pipeline. La version en
español/portugues y la cobertura de Azure/GCP/OCI a detalle se generan en la siguiente pasada,
una vez que confirmemos que este formato sirve para tu caso de uso de RFP.*
