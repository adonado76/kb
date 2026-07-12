---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Understand usage metrics for GenAI services in Cloudability"
breadcrumb:
  - "Insights"
  - "Understand usage metrics for GenAI services in Cloudability"
source_path: "SSVCLNQ/product/genai-usage-metrics.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Understand usage metrics for GenAI services in Cloudability

Generative AI (GenAI) services such as AWS Bedrock , Azure OpenAI , and Google Vertex AI use billing models that differ from traditional compute or storage. Each provider measures usage in different ways - tokens, characters, or compute hours. Cloudability allows you to interpret these costs consistently using existing metrics and dimensions.

## Key workload types

GenAI usage generally falls into two categories:

- Inference workloads Usage of trained models for generating text, code, or images. Billing units: tokens (≈ 4 characters) or characters processed Cloudability metric: Appears under Usage Quantity
- Training or fine-tuning workloads (Compute-intensive jobs that train or adapt models) Billing units: GPU, TPU, or instance-hours Cloudability metric: Appears under Usage Hours (or similar compute metrics)

## How to analyze GenAI usage in Cloudability

Use Cloudability reports to explore how your GenAI services are being billed.

Example Configuration:

| Step | What to add | Purpose |
| --- | --- | --- |
| 1. | Metrics: Usage Quantity, Unblended Cost | See how much was consumed and what it cost |
| 2. | Dimensions: Item Description, Operation, Enhanced Service Name | Identify how the cloud provider measured usage |
| 3. | Filters: gpt, bedrock, vertex, openai, claude, mistral (note: these are examples and the filters could vary based on the servicename or product name) | Narrow your report to AI-related consumption |

Example: Create a report filtering for Enhanced Service Name = AWS Bedrock. Add Item Description and Operation as dimensions, then filter for gpt or claude. If you see “Usage Quantity = 2000” and “Unit = Tokens”, that equals 2,000 tokens (≈ 8,000 characters).

## Examples by Cloud provider

| Provider/Service name | Typical billing unit | How it Appears in Cloudability |
| --- | --- | --- |
| AWS Bedrock | Tokens | Usage Quantity = 2000 → 2,000 tokens (≈ 8,000 chars). Item Description: Bedrock:Claude:InputTokens |
| AzureOpenAI / AI Foundry | 1K Tokens | Usage Quantity = 100 → 100 × 1,000 = 100,000 tokens. Unit column shows “1K Tokens”. |
| Google Vertex / Gemini | Chars | Usage Quantity = 4,000 → ≈ 1,000 tokens. Item Description: VertexAI:TextInputCharacters |
| AWS Sagemaker | Instance Hours | Training and inference endpoints billed by instance-hour. |
| OCI GenAI | Unit Hours, Chars | Character-based for inference; AI unit-hours for dedicated clusters. |
| IBM Watsonx | Subscription Units | Tracked as instances or active users (e.g., MAUs, agentic units). |

## Fin Ops best practices

- Normalize usage: Roughly 4 characters = 1 token. Use this for comparing across CSPs.
- Separate compute vs inference: Training costs (Usage Hours) differ from prompt-based inference (Usage Quantity).
- Correlate cost and description: Combine Unblended Cost, Usage Quantity, and Item Description to identify usage and costs
- Group logically: Use Enhanced Service Name or Usage Family to benchmark GenAI spend across providers.
