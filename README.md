NBA Playoff Performance Analysis
1. Research Question

This project analyzes whether NBA star players perform worse in the playoffs compared to the regular season. The analysis focuses on Anthony Edwards, LeBron James, Jayson Tatum, and Kevin Durant. This question matters because playoff basketball is often associated with higher pressure, tougher defense, and stronger competition, and the goal is to determine whether those factors actually impact shooting performance.

2. Hypothesis

Null Hypothesis (H₀):
There is no difference in field goal percentage between playoff games and regular season games.

Alternative Hypothesis (H₁):
NBA star players have a lower field goal percentage in playoff games compared to regular season games.

3. Data Description

The data comes from Basketball Reference NBA player game logs. The analysis focuses on the most recent five completed seasons, from 2021 through 2025, to reflect current playing conditions and maintain consistency.

Each row represents one player’s performance in a single game. The dataset includes game logs for Anthony Edwards, LeBron James, Jayson Tatum, and Kevin Durant, and compares regular season games against playoff games.

Rows where a player was marked as inactive, did not dress, or did not play were removed because they do not represent actual game performances.

4. Methods

The analysis compares field goal percentage (FG%) between playoff and regular season games.

The test statistic is defined as:

Playoff FG% − Regular Season FG%

A permutation test is used to determine whether the observed difference could have occurred by random chance. This is done by randomly shuffling FG% values and recomputing the difference many times to create a null distribution.

Bootstrapping is used to estimate uncertainty by repeatedly resampling the data with replacement. Confidence intervals are calculated for both the mean and the median FG% difference. The median is included because the Central Limit Theorem does not apply to it in the same way as the mean.

5. Results

The observed difference in FG% is approximately +0.006, indicating that playoff FG% is slightly higher than regular season FG%.

The permutation test produced a p-value of approximately 0.165, suggesting that the observed difference could reasonably occur by random chance.

6. Uncertainty Estimation

The 95% bootstrap confidence interval for the mean FG% difference is approximately:

[-0.0059, 0.0166]

The 95% bootstrap confidence interval for the median FG% difference is approximately:

[-0.0060, 0.0261]

Both intervals include 0, indicating that a true difference of zero is plausible and that there is no strong evidence of a meaningful difference.

7. Limitations

This analysis is limited to four players and five seasons, which may not represent all NBA players.

Playoff sample sizes are smaller than regular season samples, which may increase variability.

Other factors such as defensive matchups, injuries, minutes played, and team role are not accounted for. Additionally, field goal percentage does not capture all aspects of player performance.

8. References
Basketball Reference (https://www.basketball-reference.com/
)
Python libraries: pandas, numpy, matplotlib
