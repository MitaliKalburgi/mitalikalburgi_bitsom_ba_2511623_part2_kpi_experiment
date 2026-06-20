# Hypothesis Test Notes — Onboarding Campaign Experiment

## 1. Null Hypothesis (H0)
The new onboarding campaign has no effect on paid conversion rate.
Paid conversion rate in Treatment = Paid conversion rate in Control.

## 2. Alternate Hypothesis (H1)
The new onboarding campaign increases paid conversion rate.
Paid conversion rate in Treatment > Paid conversion rate in Control.

## 3. Test Type
One-tailed test — we are only interested in whether Treatment is better than
Control, not just different. A two-tailed test would check for any difference in either direction, which is not the business question here.

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

Other metrics like landing page, visit rate and trial start rate show funnel
improvements but do not confirm revenue impact. Engagement score and days to
convert are useful context but not the primary success signal.

## 7. Interpretation Logic
- If p-value < 0.05: Reject H0. The improvement in conversion rate is
statistically significant. The campaign is working and worth considering
for full rollout — subject to guardrail metric evaluation.
- If p-value >= 0.05: Fail to reject H0. The observed difference could be
due to chance. The campaign should not be launched based on current evidence.

The final business decision will not be based on this test alone. Even if the test is significant, guardrail metrics (refund rate, support ticket rate, engagement score) must also show no meaningful deterioration before a full launch recommendation is made.

## 8. Test Results
To be updated after performing the hypothesis test in Task 7.