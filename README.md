## Project Description

This project uses data from the 2002 National Survey of Family Growth (NSFG) to study pregnancy and childbirth. The dataset includes only pregnancies that ended in live births and is split into two groups:

firsts: First-born children (the mother’s first live birth)

others: Later-born children (not the first)

Each row represents one pregnancy and includes details like the mother's age, birth weight, and pregnancy length. This setup helps compare first-time vs. experienced mothers to find patterns and differences.


##  Description of Columns

The dataset contains several columns that provide detailed information about each pregnancy and the corresponding birth outcome. Here is a brief description of each column:

| **Column**      | **Description**                                                                 | **Type**   | **Example**         |
|-----------------|---------------------------------------------------------------------------------|------------|---------------------|
| `caseid`        | Unique identifier for each survey participant                                    | Integer    | 100001, 100002      |
| `pregordr`      | Order of the pregnancy (1 = first, 2 = second, etc.)                             | Integer    | 1, 2, 3             |
| `outcome`       | Outcome of pregnancy (1 = live birth, 2 = stillbirth, 3 = miscarriage, 4 = other) | Integer    | 1, 2, 3             |
| `birthord`      | Birth order of the child (1 = first-born, 2 = second-born, etc.)                 | Integer    | 1, 2, 3             |
| `agepreg`       | Age of the mother at the time of pregnancy (in years)                            | Float      | 24.5, 30.2          |
| `birthwgt_lb`   | Birth weight of the baby in pounds                                               | Float      | 7.5, 6.8            |
| `birthwgt_oz`   | Birth weight of the baby in ounces (16 oz = 1 lb)                               | Integer    | 8, 12               |
| `finalwgt`      | Final weight variable used for survey weighting                                  | Float      | 0.75, 1.2           |
| `prglngth`      | Length of the pregnancy in weeks                                                 | Integer    | 40, 37, 42          |
| `numdep`        | Number of dependent children the mother has at the time of the survey           | Integer    | 1, 3                |
|-----------------|---------------------------------------------------------------------------------|------------|---------------------|


## A/B Testing Evaluate
Metric Game_rounds : Mann-Whitney

Metric %Retention_1 : Chi-Square

Metric %Retention_7 : Chi-Square

## Conclusion
**Business Problem Recap:**

In Cookie Cats, players face gates that make them wait before progressing or making an in-app purchase. We analyzed an A/B test where the first gate was moved from level 30 to level 40, focusing on player retention and game rounds.

**Key Findings:**

- The Mann-Whitney U test showed no difference in game rounds between gate_30 and gate_40.
- The Chi-Square test found no difference in 1-day retention, but 7-day retention for gate_40 was lower (14.92%) compared to gate_30 (15.76%).

**Conclusion:**

The gate change didn’t impact game rounds or 1-day retention, but 7-day retention decreased. Therefore, we recommend keeping the old version (gate_30). Other factors, like game experience and rewards, should also be considered.



