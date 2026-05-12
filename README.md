# NBA Playoff Performance Analysis

## 1. Research Question

This project analyzes whether NBA star players perform worse in the playoffs compared to the regular season. The analysis focuses on Anthony Edwards, LeBron James, Jayson Tatum, Kevin Durant, Stephen Curry, Luka Doncic, Nikola Jokic, and Giannis Antetokounmpo.

This question matters because playoff basketball is often associated with higher pressure, tougher defense, and stronger competition. The goal is to determine whether those factors show up in shooting performance, specifically field goal percentage.

## 2. Hypothesis

**Null Hypothesis (H₀):**  
There is no difference in field goal percentage between playoff games and regular season games.

**Alternative Hypothesis (H₁):**  
NBA star players have a lower field goal percentage in playoff games compared to regular season games.

## 3. Data Description

The data comes from Basketball Reference NBA player game logs. The analysis focuses on the most recent five completed seasons, from 2021 through 2025, to reflect current playing conditions and maintain consistency.

Each row represents one player’s performance in a single game. Regular season and playoff game logs were combined into one dataset.

Key variables include player name, season, game type, minutes played, field goals made, field goals attempted, and field goal percentage.

Rows where a player was marked as inactive, did not dress, or did not play were removed because those rows do not represent actual game performances.

After cleaning, the dataset includes 2702 regular season games and 989 playoff games.

## 4. Methods

The analysis compares field goal percentage (FG%) between playoff and regular season games.

The test statistic is defined as:

**Playoff FG% − Regular Season FG%**

A negative value means playoff FG% is lower than regular season FG%.

A permutation test was used to determine whether the observed difference could have occurred by random chance. This was done by randomly shuffling FG% values and recomputing the mean difference many times to create a null distribution. The permutation test used 1000 simulations.

Bootstrapping was also used to estimate uncertainty around the FG% difference by repeatedly resampling the data with replacement and calculating confidence intervals. The bootstrap analysis used 1000 resamples.

Bootstrap confidence intervals were calculated for both the mean FG% difference and the median FG% difference. The median was included because the Central Limit Theorem does not apply to medians in the same direct way that it applies to means.

## 5. Results

The average regular season FG% was approximately 0.503, while the average playoff FG% was approximately 0.488.

The observed difference was approximately -0.016, meaning playoff FG% was about 1.6 percentage points lower than regular season FG%.

The permutation distribution was centered near 0 under the null hypothesis, while the observed difference fell far into the left tail of the distribution.

The permutation test produced a p-value of approximately 0.001. This means the observed decrease was unlikely to occur purely by random chance under the null hypothesis.

## 6. Uncertainty Estimation

The 95% bootstrap confidence interval for the mean FG% difference was approximately:

**[-0.0247, -0.0074]**

Because this interval is entirely below 0, it supports the conclusion that playoff FG% is likely lower than regular season FG% in this dataset.

The 95% bootstrap confidence interval for the median FG% difference was approximately:

**[-0.026, 0.000]**

The median interval is included as a non-CLT uncertainty metric. Bootstrapping is useful here because the median does not rely on the same normal-based assumptions as the mean.

## 7. Limitations

This analysis is limited to eight NBA star players and five recent seasons, so the results may not represent all NBA players.

Playoff sample sizes are smaller than regular season sample sizes, which may affect variability.

Other factors such as defensive matchups, injuries, minutes played, team role, opponent strength, and shot difficulty were not directly controlled for. Field goal percentage is useful, but it does not capture every part of player performance.

## 8. Conclusion

Overall, the results suggest that NBA star players in this dataset shot slightly worse in the playoffs compared to the regular season. Although the difference was not extremely large, both the permutation test and bootstrap confidence interval suggest that the decrease is statistically meaningful rather than purely random variation.

## 9. References

Game log data was collected from Basketball Reference player game logs:  
https://www.basketball-reference.com/

Python libraries used:
- pandas
- numpy
- matplotlib