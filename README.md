# Game Version Impact on Retention and Game Rounds Played

## Project Overview

This project analyzes the impact of two game versions, gate_30 and gate_40, on player retention and the number of game rounds played. The goal is to determine whether changing the game version leads to higher retention and more gameplay. The analysis will help inform product decisions by evaluating which version is more engaging for players.

## Dataset

**Link:** https://www.kaggle.com/datasets/yufengsui/mobile-games-ab-testing

The dataset consists of the following key variables:

**userid:** Unique player identifier.

**version:** Game version (gate_30 as control, gate_40 as treatment).

**sum_gamerounds:** Total number of game rounds played by the user.

**retention_1:** Whether the player returned to the game on day 1 (binary: 0 for no, 1 for yes).

**retention_7:** Whether the player returned to the game on day 7 (binary: 0 for no, 1 for yes).

## Data Cleaning

Before analysis, I handled missing data and converted retention_1 and retention_7 from boolean (True/False) to binary (0/1). Outliers in the sum_gamerounds column were identified and removed through exploratory data analysis (EDA), ensuring accurate statistical results.

## Hypothesis

#### Day 1 Retention

**Null Hypothesis (H0):** There is no difference in retention between gate_30 and gate_40 on day 1.

**Alternative Hypothesis (H1):** Players using gate_40 have higher retention than those using gate_30 on day 1.

#### Day 7 Retention

**Null Hypothesis (H0):** There is no difference in retention between gate_30 and gate_40 on day 7.

**Alternative Hypothesis (H1):** Players using gate_40 have higher retention than those using gate_30 on day 7.

#### Game Rounds Played

**Null Hypothesis (H0):** The total game rounds played (sum_gamerounds) for gate_30 is equal to that of gate_40.

**Alternative Hypothesis (H1):** There is a difference in the total game rounds played between gate_30 and gate_40.

## Exploratory Data Analysis

**EDA involved:**

- Removing extreme outliers in gameplay that could bias the results.
  
- Visualizing retention rates for both days.

- Comparing the total number of game rounds played between gate_30 and gate_40.


###  Results Summary

| **Metric**              | **Statistic**       | **p-value**      | **Conclusion**                             |
|-------------------------|---------------------|------------------|--------------------------------------------|
| **Retention on Day 1**  | Chi-squared: 3.493  | 0.062            | No significant difference (p > 0.05)       |
| **Retention on Day 7**  | Chi-squared: 11.181 | 0.00083          | Significant difference (p < 0.05)          |
| **Gameplay (Rounds)**   | t-statistic: 0.832  | 0.405            | No significant difference (p > 0.05)       |

## **Results Explanation**

**1. Retention on Day 1**
- Chi-squared statistic: 3.493
- p-value: 0.062
- Conclusion: No significant difference in retention between the two groups on Day 1.
  
**2. Retention on Day 7**
- Chi-squared statistic: 11.181
- p-value: 0.00083
- Conclusion: Significant difference observed in Day 7 retention, with gate_40 showing better retention.
  
**3. Gameplay (Total Game Rounds Played)**
- t-statistic: 0.832
- p-value: 0.405
- Conclusion: No significant difference in the total game rounds played between gate_30 and gate_40.

## Business Impact

**_This suggests that the new gate mechanism (gate_40) positively impacts player retention in the long term (day 7) but not in the short term (day 1). The new mechanism does not seem to affect the total gameplay time, as measured by the sum of game rounds._**

## Next Steps and Future Improvements

- **Analyze Retention Drivers:** Further analysis into what other game mechanics or features might be influencing the differences in retention.
- **Experiment with Other Features:** Test additional game features that might affect retention, such as tutorial effectiveness or user interface changes.
  
## Limitations

The experiment focused on a single feature (game gate version); other factors influencing player retention were not considered.
