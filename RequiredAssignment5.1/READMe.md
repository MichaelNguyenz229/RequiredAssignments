Project Report: Customer Coupon Acceptance Analysis
Link to Notebook: [[Insert Your GitHub Notebook URL Here](https://github.com/MichaelNguyenz229/RequiredAssignments/blob/main/RequiredAssignment5.1/assignment5_1_starter/prompt.ipynb)]
1. The Business Problem
The goal of this analysis was to determine the characteristics of drivers who are most likely to accept a coupon (labeled as 'Y=1') versus those who reject it ('Y=0'). By understanding these differences, the dealership can ensure coupons are delivered to the right people at the right time.
2. Highlights: Who Accepts vs. Who Rejects?
Based on the data exploration of Bar coupons, there are stark differences between these two groups:
• The "Habitual Socializer" (Highest Acceptance): Drivers who visit bars more than once a month and are traveling with adult passengers (friends or partners) accepted the coupon at a rate of over 70% [Based on your observations]. These customers view the coupon as an immediate social opportunity.
• The "Non-Target" Driver (Lowest Acceptance): Drivers who rarely visit bars or those traveling with children accepted the coupon at a much lower rate, consistently hovering around 29% [Based on your observations]. For these drivers, the "context" of their drive (parenting or lack of habit) makes the coupon irrelevant.
• The Age Factor: Maturity combined with habit is a major differentiator. Drivers over the age of 25 who frequent bars are significantly more likely to accept the offer than the general population.
3. Actionable Recommendations
• Priority Targeting: Deliver bar coupons specifically to drivers with no kid passengers who are currently in a "social" driving scenario.
• Frequency-Based Logic: Use the "Bar" and "Coffee House" visit history as the primary filter for distribution, as past behavior is the strongest predictor of coupon acceptance [Based on your observations].
4. Next Steps
• Address Data Gaps: Further investigation is needed for the "Cheap Restaurant" segment to resolve empty data subsets (NaN results) [Based on conversation history].
• Contextual Expansion: Perform a similar comparison for Coffee House coupons to see if time of day (morning vs. evening) creates similar differences in acceptance rates.
