# Onboarding Campaign Experiment — KPI Framework & Decision Analysis

## 1. Business Context

A subscription-based digital product company tested a new onboarding and activation campaign against its existing experience. Users were randomly assigned to two groups:

- Control: Existing onboarding flow
- Treatment: New campaign experience

The experiment ran to evaluate whether the new experience meaningfully improves user conversion and early engagement, with the end goal of informing a go no-go launch decision.

## 2. Dataset Description

The dataset contains 1,408 rows and 16 columns covering user-level experiment 
data. Each row represents one user and includes their experiment group, 
demographic and traffic attributes, funnel behavior (landing page visit, trial 
start, onboarding completion), conversion outcome, revenue, support tickets, 
refund requests, engagement score, and days to convert. After removing 8 
duplicate user IDs, 1,400 unique users were retained for analysis — 
690 in Control and 710 in Treatment.

## 3. Business Problem Statement

The company needs to decide whether to replace the current onboarding experience with the new campaign across all new users.

This decision sits with the product and growth teams but has downstream implications for revenue, customer support load, and long-term retention. Getting it wrong in either direction carries real cost — launching a campaign that hurts retention is as damaging as holding back one that genuinely works.

To make a sound call, three things need to be true:

1. The Treatment group shows a statistically significant improvement in paid conversion rate
2. Guardrail metrics — refund rate, support tickets, engagement — show no meaningful deterioration
3. The improvement is reasonably consistent across segments, not driven by one region or device type masking problems elsewhere

## 4. North Star Metric

**Paid Conversion Rate** — users who converted to paid divided by total users in the group

This is the right North Star because the campaign's stated objective is to improve conversion and early engagement. Of those two, conversion is the one that ties directly to revenue. Engagement matters, but engagement without conversion does not grow the business.

Funnel metrics like landing page visit rate, trial start rate, and onboarding completion rate are supporting indicators — they tell us where in the journey the campaign is having an effect, but they are not the finish line. Revenue per user and engagement score are important for quality checks but serve better as guardrails than as the primary success signal.

The blind-spot risk here is real: a campaign can inflate conversion by creating urgency or pressure without delivering genuine product value. That tends to show up quickly as refund spikes and support volume — which is exactly why those metrics are monitored alongside the North Star, not after the fact.

## 5. KPI Tree Summary

**North Star:** Paid Conversion Rate

**Primary Driver 1 — Funnel Progression**
- Landing Page Visit Rate
- Trial Start Rate

**Primary Driver 2 — Onboarding Effectiveness**
- Onboarding Completion Rate
- Average Engagement Score

**Primary Driver 3 — Revenue Quality**
- Average Revenue Per Converted User
- Refund Rate

**Guardrail Metrics**
- Refund Rate
- Support Ticket Rate
- Days to Convert
- Segment-Level Conversion Decline

Full KPI tree visual available in outputs/kpi_tree.png


## 6. Experiment Analysis Approach

- Dataset was validated before analysis — checked for missing values, duplicate user IDs, invalid binary entries, and revenue outliers
- All KPIs were calculated separately for Control and Treatment
- At least 3 metrics were broken down by region, device type, traffic source, and plan type
- A/B Test — One-tailed t-Test (Two Sample Assuming Unequal Variances) was applied to paid conversion rate as the primary test
- Guardrail metrics were assessed independently to flag any negative effects

Detailed calculations, formulas, and segment analysis are available in analysis/experiment_analysis.xlsx. The clean summary output is in outputs/experiment_summary.xlsx.

## 7. Hypothesis Test Summary

- H0: Paid conversion rate is equal between Control and Treatment
- H1: Treatment group conversion rate is higher than Control
- Test type: A/B Test — One-tailed t-Test (Two Sample Assuming Unequal Variances)
- Significance level: 0.05
- Result: Updated after analysis in hypothesis_test_notes.md

## 8. Guardrail Metrics Considered

- Refund Rate
- Support Ticket Rate
- Average Engagement Score
- Days to Convert
- Average Revenue Per Converted User

## 9. Final Recommendation

Launch recommended for Free and Premium plan segments based on statistically significant conversion improvement and consistent results across regions and device types. Basic plan segment showed only marginal improvement (3.62% to 3.88%) and should be monitored further before inclusion. Full rollout also pending resolution of support ticket rate increase and revenue per converted 
user decline.Full details in outputs/recommendation_memo.md.

## 10. Assumptions and Limitations

- Users were randomly assigned to groups — no selection bias is assumed
- 30 days is treated as a sufficient observation window for this product type
- 8 duplicate user IDs were identified and removed, leaving 1,400 unique users for analysis
- 18 missing values in device_type and 24 in traffic_source were replaced with 'Unknown'to retain those rows in segment analysis
- 14 missing values in engagement_score were left blank — treated as genuine missing data
- 1,336 missing values in days_to_convert were left blank — this column is only populatedfor users who converted, so blanks are expected and correct
- All binary columns (visited_landing_page, started_trial, completed_onboarding,converted_to_paid, refund_requested) were validated — all values confirmed as 0 or 1
- 3 revenue outliers identified in revenue_30d (max 8,610.72) and retained — no evidence of data entry error
- Control group: 690 users, Treatment group: 710 users after cleaning

## 11. Screenshots

- screenshots/summary_metrics.png — Control vs Treatment summary table
- screenshots/hypothesis_test_output.png — Hypothesis test output
- screenshots/kpi_tree_preview.png — KPI tree visual
