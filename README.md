
# The 162-Game Grind: Analyzing Position Player Workload, Performance, and Durability Across an MLB Season - INCOMPLETE

This is a personal analytics project examining whether position-player workload patterns are associated with changes in offensive performance and injury-related absences over the course of an MLB season. The analysis focuses on the relationship between playing-time patterns, batting average, and player durability across a 162-game regular season.

The project combines Retrosheet game-level batting and fielding data, Baseball Savant Statcast performance data, and MLB injured list/transaction data, covering four MLB seasons (2022–2025).

---

## Project Objectives

This project investigates three research hypotheses:

1. **Workload and offensive performance:** Is higher recent workload associated with weaker offensive performance over time, measured by batting average?
2. **Rest and offensive performance:** Do players who receive rest have higher immediate offensive performance than players who play consecutively?
3. **Workload and durability:** Is higher recent workload associated with a greater likelihood of subsequent injured list (IL) placement?

Key business questions:
1. As position players accumulate playing time throughout a 162-game season, are periods of higher workload associated with declines in offensive production?
2. Does receiving rest provide an immediate offensive performance benefit compared to playing in consecutive games?
3. Are players experiencing higher recent workloads more likely to subsequently experience injury-related absences?

---

## Research Design

1. **Population:** MLB position players across the 2022–2025 regular seasons.
2. **Sample eligibility:** Players must appear in at least 50 games during a season to be included in the primary analysis.
3. **Unit of observation:** Player-game, allowing workload and performance patterns to be tracked throughout each season rather than relying exclusively on season-level averages.
4. **Primary offensive performance metric:** Batting average (hits divided by at-bats).
5. **Primary durability metric:** Subsequent IL placement.
6. **Secondary durability metrics:** Days on the IL and days on the active roster.
7. **Workload measurement:** Rolling 7-, 14-, and 28-day windows incorporating plate appearances, defensive innings, consecutive games, and rest days.

---

## Data Sources

1. Retrosheet — game-level batting and fielding records, player identifiers, game dates, and defensive playing-time information.
2. Baseball Savant (MLB Statcast) — expected batting average (xBA), expected weighted on-base average (xwOBA), exit velocity, hard-hit percentage, and other contact-quality metrics.
3. MLB transaction and injured list records — player IL placements, transaction dates, activation dates, and injury-related absences.

**Data limitation:** Publicly available game and transaction data provide proxies for player workload and durability, not direct measurements of physiological workload or physical recovery. Active-roster status does not necessarily indicate that a player is fully healthy. Additionally, requiring a minimum of 50 games played may exclude players who experience early or particularly severe injuries. Findings will therefore apply to the eligible sample rather than all MLB position players. Observed relationships will be interpreted as associations, not evidence of causation.

---

## Methodologies

The following steps are planned for implementation using Python and R, with Tableau for the final interactive dashboard:

1. Research design, hypothesis development, player eligibility criteria, and data dictionary creation.
2. Acquisition and inspection of Retrosheet game-level batting and fielding data.
3. Acquisition of Statcast performance data and establishment of consistent player/date joins.
4. Acquisition and standardization of IL placement, transaction, and activation data.
5. Data cleaning, merging, validation, and engineering of rolling 7-, 14-, and 28-day workload, rest, consecutive-game, and offensive performance features.
6. Exploratory data analysis of workload, batting average, injury-related absences, and position-group differences.
7. Statistical analysis of the relationship between recent workload and subsequent offensive performance, controlling for relevant player and performance characteristics.
8. Durability analysis examining associations between lagged workload and subsequent IL placement, including careful definitions of injury events and observation periods.
9. Development of an interactive Tableau dashboard to visualize workload patterns, offensive performance, and durability throughout the season.
10. Final written report, limitations assessment, GitHub repository cleanup, and portfolio presentation.

---

## Key Hypotheses

### 1. Higher Recent Workload Is Associated With Weaker Offensive Performance Over Time

* Examine the relationship between recent playing-time workload and subsequent batting average.
* Measure workload using rolling 7-, 14-, and 28-day plate appearances and defensive innings.
* Evaluate whether higher workload periods are associated with changes in subsequent offensive production.
* Use Statcast measures, including xBA and xwOBA, as supplementary indicators of underlying offensive performance.

---

### 2. Players Who Receive Rest May Have Higher Immediate Offensive Performance Than Players Who Play Consecutively

* Compare subsequent batting average between players who receive a rest day and those who appear in consecutive games.
* Measure immediate performance over the player's next three games.
* Examine whether the relationship differs based on recent workload and position.
* Account for differences in recent offensive performance when evaluating the relationship.

---

### 3. Higher Recent Workload Is Associated With a Greater Likelihood of Subsequent IL Placement

* Examine whether recent workload patterns are associated with subsequent IL placement.
* Compare rolling workload measures before IL events with workload during comparable non-IL observation periods.
* Evaluate the relationship between workload and subsequent injury-related absences using lagged workload features.
* Examine IL duration and active-roster availability as supplementary durability measures.

---

## Strategic Implications

### For MLB Teams

* Understanding the relationship between playing-time patterns and subsequent offensive production could provide additional context when evaluating rest-day and lineup-management decisions.
* Identifying workload patterns associated with subsequent IL placement could help inform player availability and roster-management strategies.
* Position-specific workload differences may provide useful context when evaluating the demands placed on different player roles.

---

### For Player Development and Performance Departments

* Tracking workload and offensive performance over time could help identify patterns that are less visible in traditional season-level statistics.
* Comparing actual batting average with expected batting average may help distinguish changes in results from changes in underlying contact quality.
* Examining consecutive-game stretches and rest patterns could provide additional insight into how playing-time distribution relates to offensive performance.

---

### For Baseball Analytics

* Combining game-level performance, Statcast, and transaction data provides an opportunity to connect multiple dimensions of player evaluation.
* Rolling workload measurements offer a more detailed view of season-long playing-time patterns than cumulative season statistics alone.
* The project demonstrates how publicly available baseball data can be combined to investigate player performance and durability while recognizing the limitations of publicly observable workload measures.
* Associations between workload, performance, and injury-related absences should not be interpreted as proof that workload causes injuries or performance declines.

---

## Repository Contents

* `research_proposal.md` — Research question, hypotheses, sample definition, and overall project design.
* `hypotheses.md` — Detailed definitions of the three primary research hypotheses and their associated variables.
* `data_dictionary.csv` — Variable definitions, data types, sources, units of measurement, and calculation methods.
* `data/raw/` — Original Retrosheet, Statcast, and transaction datasets.
* `data/processed/` — Cleaned, standardized, and merged analytical datasets.
* `python/` — Data acquisition, cleaning, feature engineering, exploratory analysis, and statistical modeling scripts.
* `r/` — Supplementary statistical analysis and modeling workflows.
* `visualizations/` — Exploratory charts and analytical visualizations.
* `tableau/` — Final interactive dashboard and supporting files.
* `final_report/` — Written research report, methodology, findings, and limitations.
* `README.md` — Project overview, research design, data sources, methodologies, and final findings.

---

## Final Insights

To be completed following the statistical analysis and visualization stages. The final report will evaluate whether recent workload patterns are associated with changes in batting average, whether rest is associated with immediate offensive performance, and whether higher recent workload is associated with subsequent IL placement.

The ultimate goal is to better understand how position-player workload, offensive performance, and durability intersect over the course of a 162-game MLB season. By combining game-level playing-time data, Statcast performance measures, and injury-related transaction records, this project aims to provide a more complete picture of player availability and performance throughout the season while recognizing the limitations of publicly available data.
