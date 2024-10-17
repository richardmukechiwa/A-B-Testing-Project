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

#### **Day 1 Retention**

**Null Hypothesis (H0):** There is no difference in retention between gate_30 and gate_40 on day 1.

**Alternative Hypothesis (H1):** Players using gate_40 have higher retention than those using gate_30 on day 1.

#### **Day 7 Retention**

**Null Hypothesis (H0):** There is no difference in retention between gate_30 and gate_40 on day 7.

**Alternative Hypothesis (H1):** Players using gate_40 have higher retention than those using gate_30 on day 7.

#### **Game Rounds Played**

**Null Hypothesis (H0):** The total game rounds played (sum_gamerounds) for gate_30 is equal to that of gate_40.

**Alternative Hypothesis (H1):** There is a difference in the total game rounds played between gate_30 and gate_40.

#### Exploratory Data Analysis

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

### **Results Explanation**

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

### Conclusion

- **Day 1 Retention:** No significant difference in the retention rates between gate_30 and gate_40.
- **Day 7 Retention:** Statistically significant improvement in retention for gate_40 compared to gate_30.
- **Gameplay:** No significant difference in the total number of game rounds played between the two versions.
  
**_This suggests that the new gate placement (gate_40) increases long-term retention (Day 7) without impacting gameplay volume.
Business Impact_**


### Next Steps and Future Improvements

- **Analyze Retention Drivers:** Further analysis into what other game mechanics or features might be influencing the differences in retention.
- **Experiment with Other Features:** Test additional game features that might affect retention, such as tutorial effectiveness or user interface changes.
  
### Limitations

The experiment focused on a single feature (game gate version); other factors influencing player retention were not considered.
