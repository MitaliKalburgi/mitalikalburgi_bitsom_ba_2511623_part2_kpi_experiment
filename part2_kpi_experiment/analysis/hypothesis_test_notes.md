# Hypothesis Test Notes — Onboarding Campaign Experiment

## 1. Null Hypothesis (H0)
The new onboarding campaign has no effect on paid conversion rate.
Paid conversion rate in Treatment = Paid conversion rate in Control.

## 2. Alternate Hypothesis (H1)
The new onboarding campaign increases paid conversion rate.
Paid conversion rate in Treatment > Paid conversion rate in Control.

## 3. Test Type
A/B Test — One-tailed test. We are only interested in whether Treatment performs better than Control, not just different. A two-tailed test would check for any difference in either direction, which is not the business question here.

## 4. Significance Level
Alpha = 0.05 (5%)
If the p-value is below 0.05, we reject the null hypothesis and conclude the
campaign has a statistically significant positive effect on conversion.

## 5. Metric Being Tested
Paid Conversion Rate
(Users converted to paid / Total users in group)

## 6. Reason for Choosing This Metric
Paid conversion rate is the North Star metric for this experiment. The entire purpose of the new campaign is to convert more users to paid subscriptions.
Testing this metric directly answers the business question — did the campaign work or not?

Other metrics like landing page, visit rate and trial start rate show funnel improvements but do not confirm revenue impact. Engagement score and days to
convert are useful context but not the primary success signal.

## 7. Interpretation Logic
- If p-value < 0.05: Reject H0. The improvement in conversion rate is
statistically significant. The campaign is working and worth considering
for full rollout — subject to guardrail metric evaluation.
- If p-value >= 0.05: Fail to reject H0. The observed difference could be
due to chance. The campaign should not be launched based on current evidence.

The final business decision will not be based on this test alone. Even if the test is significant, guardrail metrics (refund rate, support ticket rate, engagement score) must also show no meaningful deterioration before a full launch recommendation is made.

## 8. Test Results

Test performed: A/B Test (t-Test: Two Sample Assuming Unequal Variances)

Control Group:
- Users: 690
- Conversion Rate: 3.19%
- Variance: 0.0309

Treatment Group:
- Users: 710
- Conversion Rate: 7.04%
- Variance: 0.0655

Test Output:
- t-Statistic: -3.29
- P-Value (one-tailed): 0.000513
- t-Critical (one-tailed): 1.646
- Degrees of Freedom: 1259
- Significance Level: 0.05

Decision Rule:
If p-value < 0.05, reject the null hypothesis.
0.000513 < 0.05 — Null hypothesis is rejected.

Business Interpretation:
The new onboarding campaign produces a statistically significant improvement in paid conversion rate. Treatment group converted at 7.04% compared to 3.19% 
in Control — more than double. The probability of this result occurring by chance is 0.05%, which is extremely low. Based on this test alone, the campaign is working. However, the final launch decision must also consider guardrail metrics before a full rollout recommendation is made.

## 9. Guardrail Metric Evaluation

All values below are sourced from the Experiment Summary (outputs/experiment_summary.xlsx — experiment_summary sheet).

Refund Rate:
- Control: 0.00% | Treatment: 0.42%
- Treatment introduced refunds where Control had none.
- Low in absolute terms but worth monitoring post-launch.
- Verdict: Minor concern ⚠️

Support Ticket Rate:
- Control: 14.78% | Treatment: 24.79%
- Treatment generated significantly more support tickets — a 68% increase.
- This suggests the new experience may be creating confusion or friction.
- Verdict: Significant concern ⚠️

Average Engagement Score:
- Control: 57.03 | Treatment: 62.94
- Treatment users are meaningfully more engaged.
- Positive signal for long-term retention.
- Verdict: Positive ✅

Average Days to Convert:
- Control: 8.86 days | Treatment: 6.40 days
- Treatment users convert faster — good for cash flow and funnel efficiency.
- Verdict: Positive ✅

Average Revenue Per Converted User:
- Control: 1630.10 | Treatment: 770.41
- Treatment converted users are paying significantly less on average.
- This is the most serious guardrail concern — higher conversion volume but lower revenue per converter could mean the campaign is attracting 
lower-value users or pushing users to cheaper plans.
- Verdict: Serious concern ⚠️

Overall Guardrail Assessment:
The campaign shows strong conversion improvement but raises three guardrail concerns — rising support ticket rate, introduction of refunds, and a sharp 
drop in revenue per converted user. These concerns are addressed in the final recommendation 
(outputs/recommendation_memo.md).