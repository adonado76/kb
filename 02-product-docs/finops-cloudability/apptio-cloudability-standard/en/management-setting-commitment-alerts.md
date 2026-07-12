---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Setting Commitment Alerts"
breadcrumb:
  - "Optimize"
  - "Guide to Commitment Management"
  - "Setting Commitment Alerts"
source_path: "SSVCLNQ/product/setting_commitment_alerts.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Setting Commitment Alerts

## Purpose

Commitment Alerts reduce manual monitoring by notifying you when commitments are approaching expiration or when utilization falls below a threshold you define. This document explains how to configure, interpret, and act on alerts, plus vendor specific nuances.

## Alert Basics

We support two types of commitment alerts:

Expiration - Notifies users of upcoming expiring commitments. On your chosen 'expiring within' frequency, Cloudability will determine if a commitment is expiring over the specified time frame.

Utilization Threshold - Notifies users of commitments that exhibit a utilization below a specified threshold. On your chosen 'lookback period' and 'threshold', Cloudability runs the Commitment Portfolio utilization algorithm to determine if any existing commitments meet the specified criteria.

To configure alerts navigate to the commitment portfolio and select the alerts button in the top right corner. Alerts are facilitated through an email notification. Note that there is a separate tailored email report for each of the two alert types. Alerts evaluate your entire portfolio of supported types with valid credentials; they are not segmented by the vendor tab or type selected when you open the panel. (Setting an alert while on the AWS tab for example will apply the alert across Azure and GCP).

The email notification will occur according to the specified send frequency and time selected. Note that the time is in UTC. Note that for both alert types, you can decide to send the alert on the specified frequency, even if no commitments meet the specified criteria.

## Vendor Nuance

- Azure Saving Plans do not support a 90-day lookback. Instead, the alert defaults to the longest available period, 30-days.
- GCP does not provide the data granularity to determine utilization of an individual commitment. Instead, we provide utilization threshold alerts on the commitment group. For more information on GCP commitment groups, see the commitment portfolio documentation.

## Step-by-Step Alerts Configuration

1. Navigate to Optimize → Commitment Portfolio .
1. Click Alerts (upper right).
1. In Commitment Alerts: Expiration Toggle ON/OFF Set Expiring Within (e.g., 7, 14, 30, 60, 90 days) (Optional) Check Send even if none expiring Utilization Threshold Toggle ON/OFF Set Lookback Period (rolling N days) (Optional) Check Send even if none below threshold Frequency Choose how often to evaluate and what time to send the email
1. Click Submit to subscribe.
1. To disable, open the panel and click Unsubscribe for the relevant alert.

## Interpreting the Email Alerts

Expiration Email

What you’ll see:

Commitment(s) that are expiring within your selected window, along with identifiers and timing details.

Recommended actions:

- Validate coverage and utilization in Commitment Portfolio.
- Understand current and future workload consideration to evaluate renewal.
- Immediately upon expiration, evaluate your recommendations to determine if new commitment purchases are appropriate.

Utilization Threshold Email

What you’ll see:

Commitments below the utilization threshold, along with their evaluated usage details.

Recommended actions:

- Investigate scope (zonal vs. regional), sharing settings, and workload shifts
- Consider exchanges/convertibles or reducing future purchase sizes/terms
- Reevaluate commitment strategy to understand why frequent under utilization occurred and how to avoid it moving forward.

## Best Practices

- Threshold selection : Start at 90–95% and refine per type’s breakeven and historical volatility.
- Lookback window : 7–14 days balances noise vs. responsiveness. Use 30–90 days for steadier usage.
- Operate to signal, not noise : Investigate low utilization over an extended period of time. Single day dips may reflect benign or seasonal usage changes that may still be worth covering with a commitment.
- Pair with dashboards : Track coverage, utilization, savings rate, and remaining cost to contextualize alert spikes.

## Key Takeaways

- Configure Expiration and Utilization Threshold alerts in Commitment Portfolio → Alerts.
- Set a lookback and threshold aligned to breakeven and volatility; choose frequency and send time.
- Use emails as a signal to investigate.
- Be aware of Azure lookback limits and GCP group level evaluations.
