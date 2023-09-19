# Kruskal-Wallis Test


When you're dealing with data from more than two groups, the Kruskal-Wallis test serves as a nonparametric alternative to traditional Analysis of Variance (ANOVA). This test is particularly useful in two main scenarios:

1. When you have samples from three or more different populations.
2. When the data are outcomes from an experiment involving multiple groups.


## Chi-Squared Distribution: A Quick Recap

The Chi-squared distribution is crucial for the Kruskal-Wallis test. It's defined by its degrees of freedom ($n$). If $X$ follows a Chi-squared distribution with $n$ degrees of freedom, it's expressed as $X \sim \chi^2_n$.

## Constructing the Test

Assume we have $g$ groups with sample sizes $n_1, n_2, \ldots, n_g$. The total number of observations is $n = \sum_{i=1}^{g} n_i$. The test involves ranking all the observations from 1 (lowest) to $n$ (highest). The average rank across all groups is $\bar{R}$, and the average ranks within each group are $\bar{R}_1, \bar{R}_2, \ldots, \bar{R}_g$.

The test statistic $H$ is calculated as:

$
H = \frac{12 \sum_{i=1}^{g} n_i (\bar{R}_i - \bar{R})^2}{n(n+1)}
$

Under $H_0$, $H$ follows a Chi-squared distribution with $g-1$ degrees of freedom. A large $H$ value suggests that it's unlikely all groups come from the same distribution, leading us to reject $H_0$.



## Example

Imagine a scenario where a company wants to evaluate the effectiveness of four different training programs (A, B, C, and D) on employee productivity. Each program is administered to five employees, and their productivity scores are measured afterward. The scores are as follows:

| A  | B  | C  | D  |
|----|----|----|----|
| 40 | 55 | 35 | 42 |
| 45 | 53 | 38 | 39 |
| 38 | 50 | 37 | 36 |
| 41 | 52 | 40 | 44 |
| 39 | 54 | 36 | 43 |

The Kruskal-Wallis test aims to assess the null hypothesis $H_0$, which posits that all groups come from identical distributions. The alternative hypothesis $H_A$ suggests that at least one group comes from a different distribution.



### Data

Here are the productivity scores for each group:

- Group A: 40, 45, 38, 41, 39
- Group B: 55, 53, 50, 52, 54
- Group C: 35, 38, 37, 40, 36
- Group D: 42, 39, 36, 44, 43

### Step 1: Rank the Data

First, we rank all the observations from the lowest to the highest, regardless of which group they belong to. If there are ties, we take the average rank for those tied values.

Here are the ranks:

- Group A: 9, 13, 6, 10, 8  (Sum = 46)
- Group B: 20, 19, 16, 18, 17  (Sum = 90)
- Group C: 1, 5, 4, 7, 3  (Sum = 20)
- Group D: 11, 12, 2, 14, 15  (Sum = 54)

### Step 2: Calculate the Average Ranks for Each Group

Next, we calculate the average rank for each group:

- $\bar{R}_A = 46 / 5 = 9.2$
- $\bar{R}_B = 90 / 5 = 18$
- $\bar{R}_C = 20 / 5 = 4$
- $\bar{R}_D = 54 / 5 = 10.8$

### Step 3: Calculate the Overall Average Rank

The overall average rank $\bar{R}$ is the average of all the ranks:

$
\bar{R} = \frac{1 + 2 + \ldots + 20}{20} = \frac{210}{20} = 10.5
$

### Step 4: Calculate the Test Statistic $H$

The test statistic $H$ is calculated using the formula:

$
H = \frac{12 \sum_{i=1}^{g} n_i (\bar{R}_i - \bar{R})^2}{n(n+1)}
$

For our example:

$
H = \frac{12 [(5 \times (9.2 - 10.5)^2) + (5 \times (18 - 10.5)^2) + (5 \times (4 - 10.5)^2) + (5 \times (10.8 - 10.5)^2)]}{20 \times 21}
$

$
H = \frac{12 [(5 \times 1.69) + (5 \times 56.25) + (5 \times 42.25) + (5 \times 0.09)]}{420}
$

$
H = \frac{12 [8.45 + 281.25 + 211.25 + 0.45]}{420}
$

$
H = \frac{12 \times 501.4}{420}
$

$
H = \frac{6016.8}{420}
$

$
H = 14.33
$

### Step 5: Compare $H$ to the Chi-Squared Distribution


Using the chi-squared distribution with 3 degrees of freedom, we find that the p-value is approximately $0.0025$, as calculated in R with the code `pchisq(14.33, df=3, lower.tail=FALSE)`.

Given that this p-value is well below the commonly used significance level of $0.05$, we have strong evidence to reject the null hypothesis. This suggests that at least one of the training programs has a statistically significant different impact on productivity compared to the others.


Certainly! Below is a Markdown-compatible activity sheet for practicing the Kruskal-Wallis test, using a different example. This example focuses on the effectiveness of three different types of exercise programs (Cardio, Strength, and Yoga) on weight loss. The numbers represent the weight loss in pounds for each participant after a month in the program.

## Kruskal-Wallis Test Activity Sheet



The data below shows the weight loss for participants in three different exercise programs: Cardio, Strength, and Yoga.


| Cardio | 4 | 6 | 8 | 10 | 12 |
|--------|---|---|---|----|----|
| Strength | 3 | 5 | 7 | 9  | 11 |
| Yoga | 2 | 4 | 6 | 8  | 10 |


### Questions and Answers

1. **Purpose of the Study**

    - **Question**: What is the objective of this study?
    - **Answer**: The study aims to assess the effectiveness of three different types of exercise programs on weight loss.

2. **Null Hypothesis**

    - **Question**: What would be your null hypothesis for these data?
    - **Answer**: The null hypothesis would state that the distribution of weight loss is the same for all three exercise programs.

3. **Appropriate Tests**

    - **Question**: Which tests from your introductory course could be appropriate here? What reservations might you have?
    - **Answer**: One might consider using an ANOVA test. However, the data set is small, and we cannot assume that the data are normally distributed, which is an assumption for ANOVA.

4. **Ranking the Data**

    - **Question**: Rank the entire data set in order.
    - **Answer**: 

    
    | Observation: | 2 | 3 | 4 | 4 | 5 | 6 | 6 | 7 | 8 | 8 | 9 | 10 | 10 | 11 | 12 |
    |--------------|---|---|---|---|---|---|---|---|---|---|---|----|----|----|----|
    | Group:       | Y | S | C | Y | S | C | Y | S | C | Y | S |  C |  Y |  S |  C |
    | Rank:        | 1 | 2 | 3.5| 3.5| 5 | 6.5| 6.5| 8 | 9.5| 9.5| 11| 12.5| 12.5| 14 | 15 |
    

5. **Overall Mean Rank**

    - **Question**: What is the overall mean rank $ \bar{R} $?
    - **Answer**: $ \bar{R} = \frac{120}{15} = 8 $

6. **Mean Rankings Within Groups**

    - **Question**: What are the mean rankings within each group?
    - **Answer**: $ \bar{R}_{\text{Cardio}} = 9.2, \bar{R}_{\text{Strength}} = 8.2, \bar{R}_{\text{Yoga}} = 6.8 $

7. **Variation in Group Ranking**

    - **Question**: Compute the variation in group ranking.
    - **Answer**: $ 5((9.2 - 8)^2 + (8.2 - 8)^2 + (6.8 - 8)^2) = 30 $

8. **Test Statistic**

    - **Question**: Why does the above look promising as a test statistic?
    - **Answer**: The statistic measures the variance of the within-group rankings. Under the null hypothesis, we would expect this variance to be small.

9. **Compute $ H $**

    - **Question**: Compute the test statistic $ H $.
    - **Answer**: $ H = \frac{12 \times 30}{15 \times 16} = 1.5 $

10. **Type of Test**

    - **Question**: Would this be a one or two-tailed test?
    - **Answer**: One-tailed, as small values are consistent with the null hypothesis.

11. **p-value**

    - **Question**: How would you find the p-value for the test?
    - **Answer**: We would use the chi-squared distribution with 2 degrees of freedom to find the probability that a $ \chi^2 $ variable exceeds 1.5. The p-value would be around 0.47.

12. **Conclusions**

    - **Question**: What would you conclude about the hypothesis of interest?
    - **Answer**: The p-value is not sufficiently small to reject the null hypothesis. Therefore, we do not have enough evidence to say that one exercise program is more effective than the others.

13. **R Notes**

    - **Question**: How would you perform this test in R?
    - **Answer**: You can use the `kruskal.test()` function in R to perform the Kruskal-Wallis test. Input the data as a list or data frame and run the function to get the test statistic and p-value.




