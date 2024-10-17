# Game Version Impact on Retention and Game Rounds Played

### Project Overview

This project analyzes the impact of two game versions, gate_30 and gate_40, on player retention and the number of game rounds played. The goal is to determine whether changing the game version leads to higher retention and more gameplay. The analysis will help inform product decisions by evaluating which version is more engaging for players.

### Dataset

**Link:** https://www.kaggle.com/datasets/yufengsui/mobile-games-ab-testing

The dataset consists of the following key variables:

**userid:** Unique player identifier.

**version:** Game version (gate_30 as control, gate_40 as treatment).

**sum_gamerounds:** Total number of game rounds played by the user.

**retention_1:** Whether the player returned to the game on day 1 (binary: 0 for no, 1 for yes).

**retention_7:** Whether the player returned to the game on day 7 (binary: 0 for no, 1 for yes).

### Data Cleaning

Before analysis, I handled missing data and converted retention_1 and retention_7 from boolean (True/False) to binary (0/1). Outliers in the sum_gamerounds column were identified and removed through exploratory data analysis (EDA), ensuring accurate statistical results.

### Hypotheses

Day 1 Retention
Null Hypothesis (H0): There is no difference in retention between gate_30 and gate_40 on day 1.
Alternative Hypothesis (H1): Players using gate_40 have higher retention than those using gate_30 on day 1.
Day 7 Retention
Null Hypothesis (H0): There is no difference in retention between gate_30 and gate_40 on day 7.
Alternative Hypothesis (H1): Players using gate_40 have higher retention than those using gate_30 on day 7.
Game Rounds Played
Null Hypothesis (H0): The total game rounds played (sum_gamerounds) for gate_30 is equal to that of gate_40.
Alternative Hypothesis (H1): There is a difference in the total game rounds played between gate_30 and gate_40.
Exploratory Data Analysis
EDA involved:

Visualizing retention rates for both days.
Comparing the total number of game rounds played between gate_30 and gate_40.
Removing extreme outliers in gameplay that could bias the results.
Chi-squared Test Results
Day 1 Retention
I used a Chi-squared test to assess the difference in retention rates between gate_30 and gate_40. The contingency table for day 1 retention is:

version	retention_1 = 0	retention_1 = 1
gate_30	24656	19796
gate_40	25364	19859
Chi-squared statistic: 0.208
p-value: 0.648
Since the p-value is greater than 0.05, we fail to reject the null hypothesis, suggesting no statistically significant difference in day 1 retention between the two game versions.

Day 7 Retention
The contingency table for day 7 retention is:

version	retention_7 = 0	retention_7 = 1
gate_30	36186	8266
gate_40	37203	8020
Chi-squared statistic: 2.809
p-value: 0.094
The p-value is slightly above 0.05, so we also fail to reject the null hypothesis for day 7 retention. There is no significant difference in retention on day 7 between the two groups.

T-test Results for Game Rounds Played
I compared the sum_gamerounds between gate_30 and gate_40 using a t-test, since both groups' game rounds were normally distributed after EDA.

t-statistic: -1.025
p-value: 0.305
The p-value is greater than 0.05, indicating that there is no significant difference in the number of game rounds played between the two game versions.

Conclusion
Based on the statistical tests:

Retention: There is no significant difference in day 1 or day 7 retention rates between gate_30 and gate_40.
Game Rounds Played: There is no significant difference in the total game rounds played between the two game versions.
Business Impact
Although no statistically significant differences were found, further analysis might be needed with a larger sample size or by testing different features of the game. The results suggest that switching to gate_40 does not harm retention or gameplay, but additional features should be tested for further improvements.

Next Steps
Consider testing additional game features that could have a larger impact on retention.
Run the experiment for a longer period to gather more data and check for long-term effects.
Explore interaction effects between different player segments (e.g., new players vs. returning players) to uncover potential hidden insights.
Limitations
The dataset may not have been large enough to detect small but meaningful differences in retention or gameplay.
The experiment focused on a single feature (game gate version); other factors influencing player retention were not considered.
Acknowledgements
Thanks to the game developers and data science community for their contributions to this dataset and analysis methodology.
