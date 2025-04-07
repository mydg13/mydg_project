## Project Description

This project uses data from the 2002 National Survey of Family Growth (NSFG) to study pregnancy and childbirth. The dataset includes only pregnancies that ended in live births and is split into two groups:

firsts: First-born children (the mother’s first live birth)

others: Later-born children (not the first)

Each row represents one pregnancy and includes details like the mother's age, birth weight, and pregnancy length. This setup helps compare first-time vs. experienced mothers to find patterns and differences.


##  Description of Columns

The dataset contains several columns that provide detailed information about each pregnancy and the corresponding birth outcome. 
Here is a brief description of each column:

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


## Outline Analysis 

I. Comparison of the Birth Weight of Firstborn and Non-Firstborn Children

      Descriptive Statistics : PMF / CDF, Statistical measures, Cohen's Effect Size
      
      Inference Statistic : Hypothesis Testing, Regression, Confidence Interval

II. Comparison of Pregnancy Duration Between First and Subsequent Births   

      Using PMF


## Analysis

**I.Input Data :**

![NSFG Pregnancy Data](https://github.com/mydg13/mydg_project/blob/main/image/image1.png?raw=true)



**II.Comparison of the Birth Weight of Firstborn and Non-Firstborn Children :**

**Descriptive Statistics**

**1. PMF**

![Pregnancy Analysis Chart](https://github.com/mydg13/mydg_project/blob/main/image/image2.png?raw=true)

These distributions all resemble a "bell shape," with many values clustering around the mean and fewer extreme values.

There are multiple sharp peaks and dips, along with some noticeable differences between the distributions.

→ It’s hard to determine which of these features are meaningful.

→ It’s also difficult to discern overall characteristics; for example, which distribution do you think has the higher mean?

→ Use the CDF for better insight.

**2. CDF**

![Description of image](https://github.com/mydg13/BirthData_Project/blob/main/image/image3.png?raw=true)

Since the line for firstborn children is to the left of the line for later-born children, firstborns tend to be slightly lighter.

The noticeable gap in the middle suggests that the difference is more pronounced above the mean value.

**3. Statistical measures**

The mean and median birth weights of firstborn children are lower compared to those of later-born children.

![Description of image](https://github.com/mydg13/BirthData_Project/blob/main/image/image4.png?raw=true)

**4. Cohen's Effect Size**

Firstborn children are lighter than later-born children, but the difference is small.

![Description of image](https://github.com/mydg13/BirthData_Project/blob/main/image/image5.png?raw=true)

**Inference Statistic**

**1. Hypothesis Testing**

It can be observed that the average birth weight of the newborns is slightly lower. Now, we will examine whether this effect is statistically significant.

![Description of image](https://github.com/mydg13/BirthData_Project/blob/main/image/image6.png?raw=true)

**2. Regression**

It has been observed that first-born children tend to weigh less than their later-born siblings, and this effect is statistically significant. However, this result is somewhat surprising, as there is no obvious biological mechanism that would necessarily cause first-borns to be lighter. This raises the question of whether the observed relationship might be spurious.

Input:

      + Independent variable: isfirst (a dummy variable indicating whether the child is first-born)

      + Dependent variable (target for prediction): totalwgt_lb (birth weight in pounds)

      + This model compares the average birth weight of first-born children with that of non-first-born children.

Findings:

      + Coefficient of isfirst[T.True] (-0.1248): First-born children (isfirst=True) weigh on average 0.1248 pounds less than non-first-born children.

      + R-squared (0.002): The model explains about 0.2% of the variation in birth weight based on whether the child is first-born.→ Being first-born is just one of many factors that influence birth weight; many other important variables are not captured in this model.

      + P-value for isfirst[T.True] (0.000):The result is highly statistically significant, suggesting that the difference in weight between first-born and non-first-born children is unlikely to be due to random chance and may be driven by an underlying factor.

Conclusion:
      + There is a measurable difference in birth weight between first-born and later-born children (first-borns tend to weigh less). However, the variable isfirst accounts for only a very small portion of the variation in birth weight. This implies that while the effect exists, its practical impact is minimal, and many other factors contribute to birth weight that are not included in the model.

![Description of image](https://github.com/mydg13/BirthData_Project/blob/main/image/image7.png?raw=true)
