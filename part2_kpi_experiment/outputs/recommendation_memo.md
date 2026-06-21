# Recommendation Memo — Onboarding Campaign Launch Decision

## 1. Executive Summary

**Decision to be made:** Whether to replace the current onboarding experience with the new campaign for all new users.

**Who it impacts:** Product and growth teams, and every new user entering the platform going forward.

**Metric to improve:** Paid conversion rate — users who convert from trial to a paid subscription within 30 days.

**Risks monitored:** Refund rate, support ticket rate, engagement score, and segment-level conversion decline.

**Evidence required:** Statistically significant improvement in paid conversion rate, no meaningful deterioration in guardrail metrics, and consistent results across key segments.

The A/B test confirmed a statistically significant improvement in paid conversion rate (3.19% → 7.04%, p-value: 0.000513). However, three guardrail concerns were identified — rising support tickets, introduction of refunds, and lower revenue per converted user. The recommendation is to launch for selected segments only.

## 2. North Star Metric

Paid Conversion Rate was selected as the North Star metric because it directly measures whether the campaign achieves its core business objective — converting new users into paying customers. All funnel metrics feed into this outcome.

## 3. KPI Tree Explanation

The KPI tree breaks paid conversion rate into three primary drivers:
- Funnel Progression: landing page visit rate and trial start rate
- Onboarding Quality: onboarding completion rate and engagement score
- Revenue Quality: average revenue per user and refund rate

All three drivers showed improvement in Treatment, which explains the overall conversion lift. However, revenue quality raised a concern with a sharp drop 
in average revenue per converted user.

## 4. Experiment Result Summary

| Metric | Control | Treatment |
|---|---|---|
| User Count | 690 | 710 |
| Landing Page Visit Rate | 63.62% | 72.39% |
| Trial Start Rate | 25.07% | 29.01% |
| Onboarding Completion Rate | 15.65% | 21.13% |
| Paid Conversion Rate | 3.19% | 7.04% |
| Avg Revenue Per User | 51.97 | 54.25 |
| Avg Revenue Per Converted User | 1630.10 | 770.41 |
| Refund Rate | 0.00% | 0.42% |
| Support Ticket Rate | 14.78% | 24.79% |
| Avg Engagement Score | 57.03 | 62.94 |
| Avg Days to Convert | 8.86 | 6.40 |

## 5. Hypothesis Test Interpretation

Test: A/B Test (t-Test: Two Sample Assuming Unequal Variances)
- t-Statistic: -3.29
- P-Value (one-tailed): 0.000513
- Significance Level: 0.05

The p-value of 0.000513 is well below 0.05. The null hypothesis is rejected. 
The improvement in paid conversion rate is statistically significant and is not due to chance.

## 6. Guardrail Analysis

| Guardrail Metric | Control | Treatment | Verdict |
|---|---|---|---|
| Refund Rate | 0.00% | 0.42% | Minor concern |
| Support Ticket Rate | 14.78% | 24.79% | Significant concern |
| Avg Engagement Score | 57.03 | 62.94 | Positive |
| Avg Days to Convert | 8.86 | 6.40 | Positive |
| Avg Revenue Per Converted User | 1630.10 | 770.41 | Serious concern |

The support ticket rate increase of 68% and the drop in revenue per converted user from 1630 to 770 are the two most important guardrail findings. These 
suggest the campaign may be converting users who are less committed or creating friction in the experience that drives support volume up.

## 7. Segment-Level Insight

Paid conversion rate was analyzed across four segments:

Region: Treatment outperformed Control in all four regions (North, South, East, West). The improvement is consistent and not driven by one region.

Device Type: Treatment outperformed Control across Mobile, Desktop, and Tablet. No device type showed a negative result.

Traffic Source: Treatment underperformed Control in the Social segment (Control: 7.75%, Treatment: 6.06%). All other traffic sources showed improvement. This is worth investigating before full rollout.

Plan Type: Treatment outperformed Control across Free, Basic, and Premium plans. The largest lift was in the Free plan segment (3.06% to 9.29%).

## 8. Final Recommendation: Launch with Conditions

The campaign is recommended for launch, but not an immediate full rollout.

The conversion improvement is real, statistically significant, and consistent across most segments. However, the support ticket surge and revenue per 
converted user drop are serious enough to warrant a phased approach:

1. Launch to Free and Premium plan users first — these segments showed the strongest conversion lift with manageable risk
2. Investigate the Social traffic source segment before including it in rollout
3. Monitor support ticket volume closely in the first 30 days post-launch
4. Track revenue per converted user monthly to confirm it stabilizes or improves
5. Re-evaluate the Social segment after 60 days of data

A full rollout to all segments is recommended only after support ticket rate shows improvement and revenue per converted user trends upward.

## 9. Risks and Limitations

- The drop in average revenue per converted user is the biggest financial risk. If it does not recover, the campaign may grow user numbers but shrink revenue.
- Support ticket volume increase will raise operational costs. This needs to be factored into the business case for launch.
- The Social traffic source segment showed Control outperforming Treatment — a blanket rollout could hurt this segment.
- The experiment ran for a defined period. Seasonal effects cannot be ruled out.
- Random assignment is assumed but not verified through this analysis.

## 10. Next Steps

- Begin phased rollout to Free and Premium segments immediately
- Set up monitoring dashboards for support ticket rate and revenue per converter
- Run a follow-up experiment specifically for the Social traffic source segment
- Review refund patterns after 30 days to confirm they stay below 1%
- Schedule a 60-day review before deciding on full rollout