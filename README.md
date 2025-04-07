## Project Overview

This project uses data from the 2002 National Survey of Family Growth (NSFG) to analyze pregnancy and childbirth. The dataset focuses on pregnancies that resulted in live births and is divided into two groups:

- **Firstborns**: The mother's first live birth.
- **Subsequent births**: Any live birth after the first.

Each row in the dataset represents one pregnancy, with details such as the mother's age, birth weight, and pregnancy duration. The analysis compares first-time and experienced mothers, highlighting patterns and differences.

---

## Dataset Columns Overview

The dataset contains the following columns, each providing essential details about each pregnancy:

| **Column**      | **Description**                                                                 | **Type**   | **Example**         |
|-----------------|---------------------------------------------------------------------------------|------------|---------------------|
| `caseid`        | Unique identifier for each participant                                           | Integer    | 100001, 100002      |
| `pregordr`      | Pregnancy order (1 = first, 2 = second, etc.)                                    | Integer    | 1, 2, 3             |
| `outcome`       | Outcome of pregnancy (1 = live birth, 2 = stillbirth, 3 = miscarriage, 4 = other) | Integer    | 1, 2, 3             |
| `birthord`      | Birth order of the child (1 = first-born, 2 = second-born, etc.)                 | Integer    | 1, 2, 3             |
| `agepreg`       | Mother's age at pregnancy (in years)                                             | Float      | 24.5, 30.2          |
| `birthwgt_lb`   | Baby's birth weight in pounds                                                    | Float      | 7.5, 6.8            |
| `birthwgt_oz`   | Baby's birth weight in ounces (16 oz = 1 lb)                                     | Integer    | 8, 12               |
| `finalwgt`      | Weight variable used for survey weighting                                         | Float      | 0.75, 1.2           |
| `prglngth`      | Pregnancy duration in weeks                                                      | Integer    | 40, 37, 42          |
| `numdep`        | Number of dependent children the mother has at the time of the survey            | Integer    | 1, 3                |

---

## Analytical Approach

### I. Comparison of the Birth Weight of Firstborn and Non-Firstborn Children

1. **Descriptive Statistics**:
   - **PMF / CDF**: Probability Mass Function (PMF) and Cumulative Distribution Function (CDF) analysis.
   - **Cohen's Effect Size**: Measure the effect size between firstborn and non-firstborn children.

2. **Inference Statistics**:
   - **Hypothesis Testing**: Test for statistically significant differences in birth weight.
   - **Regression**: Analyze the relationship between birth order and birth weight.
   - **Confidence Interval**: Estimate the range of the birth weight difference.

### II. Comparison of Pregnancy Duration Between First and Subsequent Births

Using **PMF** to analyze the pregnancy length distribution for both groups.

---

## Analysis

### I. Input Data

![NSFG Pregnancy Data](https://github.com/mydg13/mydg_project/blob/main/image/image1.png?raw=true)

### II. Comparison of the Birth Weight of Firstborn and Non-Firstborn Children:

#### 1. Descriptive Statistics

##### 1.1 PMF

![Pregnancy Analysis Chart](https://github.com/mydg13/mydg_project/blob/main/image/image2.png?raw=true)

These distributions all resemble a "bell shape," with many values clustering around the mean and fewer extreme values.

There are multiple sharp peaks and dips, along with some noticeable differences between the distributions.

→ It’s hard to determine which of these features are meaningful.

→ It’s also difficult to discern overall characteristics; for example, which distribution do you think has the higher mean?

→ Use the CDF for better insight.

##### 1.2 CDF

![Description of image](https://github.com/mydg13/BirthData_Project/blob/main/image/image3.png?raw=true)

Since the line for firstborn children is to the left of the line for later-born children, firstborns tend to be slightly lighter.

The noticeable gap in the middle suggests that the difference is more pronounced above the mean value.

##### 1.3 Statistical measures

The mean and median birth weights of firstborn children are lower compared to those of later-born children.

<p align="center">
  <img src="https://github.com/mydg13/BirthData_Project/blob/main/image/image4.png?raw=true" alt="Description of image" width="70%" />
</p>

##### 1.4 Cohen's Effect Size

Firstborn children are lighter than later-born children, but the difference is small.

<p align="center">
  <img src="https://github.com/mydg13/BirthData_Project/blob/main/image/image5.png?raw=true" alt="Description of image" width="70%" />
</p>

#### 2. Inference Statistic

##### 2.1 Hypothesis Testing

It can be observed that the average birth weight of the newborns is slightly lower. Now, we will examine whether this effect is statistically significant.

<p align="center">
  <img src="https://github.com/mydg13/BirthData_Project/blob/main/image/image6.png?raw=true" alt="Description of image" width="70%" />
</p>

##### 2.2 Regression

It has been observed that first-born children tend to weigh less than their later-born siblings, and this effect is statistically significant. However, this result is somewhat surprising, as there is no obvious biological mechanism that would necessarily cause first-borns to be lighter. This raises the question of whether the observed relationship might be spurious.

Input:

- Independent variable: isfirst (a dummy variable indicating whether the child is first-born)
- Dependent variable (target for prediction): totalwgt_lb (birth weight in pounds)

This model compares the average birth weight of first-born children with that of non-first-born children.

Findings:

- Coefficient of isfirst[T.True] (-0.1248): First-born children (isfirst=True) weigh on average 0.1248 pounds less than non-first-born children.
- R-squared (0.002): The model explains about 0.2% of the variation in birth weight based on whether the child is first-born.→ Being first-born is just one of many factors that influence birth weight; many other important variables are not captured in this model.
- P-value for isfirst[T.True] (0.000): The result is highly statistically significant, suggesting that the difference in weight between first-born and non-first-born children is unlikely to be due to random chance and may be driven by an underlying factor.

Conclusion:

- There is a measurable difference in birth weight between first-born and later-born children (first-borns tend to weigh less). However, the variable isfirst accounts for only a very small portion of the variation in birth weight. This implies that while the effect exists, its practical impact is minimal, and many other factors contribute to birth weight that are not included in the model.

<p align="center">
  <img src="https://github.com/mydg13/BirthData_Project/blob/main/image/image7.png?raw=true" alt="Description of image" width="70%" />
</p>

##### 2.3 Confidence Interval

<p align="center">
  <img src="https://github.com/mydg13/BirthData_Project/blob/main/image/image11.png?raw=true" alt="Description of image" width="70%" />
</p>

### II. Comparison of the Birth Weight of Firstborn and Non-Firstborn Children

The probability mass function (PMF) of firstborn children (blue) tends to be more right-skewed compared to the PMF of later-born children (red).

<p align="center">
  <img src="https://github.com/mydg13/BirthData_Project/blob/main/image/image8.png?raw=true" alt="Chart 1" width="45%" />
  <img src="https://github.com/mydg13/BirthData_Project/blob/main/image/image9.png?raw=true" alt="Chart 2" width="45%" />
</p>

Zoom in on the difference

![Pregnancy Analysis Chart](https://github.com/mydg13/mydg_project/blob/main/image/image10.png?raw=true)

Explanation

- X-axis: Represents the number of pregnancy weeks, ranging from 30 to 46 weeks.
- Y-axis: Represents the probability difference (measured in percentage points) between first pregnancies and subsequent pregnancies.
- Positive values: Indicate that the probability is higher for first pregnancies.
- Negative values: Indicate that the probability is higher for subsequent pregnancies.

Observations :

- From 30 to 37 weeks: The probability difference is relatively small, fluctuating around zero, indicating that the likelihood of first and subsequent pregnancies occurring within this range is nearly the same.
- At 38 weeks: The difference is negative and at its largest, showing that subsequent pregnancies are significantly more likely to occur at this week compared to first pregnancies.
- At 39 and 40 weeks: The difference remains negative but is smaller than at 38 weeks.
- From 41 to 43 weeks: The difference is positive, indicating that first pregnancies are more likely to extend into this range than subsequent pregnancies.
- From 44 to 46 weeks: The difference is close to zero, suggesting that the probability of first and subsequent pregnancies occurring in this period is nearly equal.

=> The chart reveals a clear distinction in pregnancy duration between first and subsequent pregnancies.

=> First pregnancies tend to last longer (notably between 41-43 weeks), whereas subsequent pregnancies tend to conclude earlier (especially at 
