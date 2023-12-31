# Permutation Tests


Randomization and permutation tests offer an intuitive approach for hypothesis testing, often used when comparing two or more groups. The core idea is to calculate a test statistic based on the observed data and then evaluate how this statistic compares to a distribution of test statistics generated by randomly shuffling the group labels.


## Example

Suppose we have the following promotion times (in months) for employees in two departments:

- Department A: 5, 7, 12, 14, 18, 21, 22, 23, 24, 25
- Department B: 7, 12, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32

### Step 1: Choose a Test Statistic

For this example, let's choose the sum of promotion times for Department A as our test statistic. The observed sum is $5 + 7 + 12 + 14 + 18 + 21 + 22 + 23 + 24 + 25 = 161$.

### Step 2: Generate Permutations

Under the null hypothesis that there's no difference in promotion times between the two departments, any subset of 10 times from the combined data should have a sum similar to 161.

To generate permutations, we would combine all the times from both departments and then randomly select 10 times, calculating the sum each time. However, for this example, we'll simplify by noting that there are $\binom{31}{10} = 141,075$ possible subsets of 10 times from the combined data of 31 times.

### Step 3: Count Extreme Values

In a real-world scenario, you'd use computational methods to find how many of these 141,075 subsets have a sum greater than or equal to the observed sum of 161. For the sake of this example, let's assume that only 1,500 of these subsets have a sum that is as extreme as 161.

### Step 4: Calculate p-value

The p-value is calculated as the proportion of subsets with a sum as extreme as the observed sum, divided by the total number of possible subsets:

$
\text{p-value} = \frac{1,500}{141,075} \approx 0.0106
$

Since the p-value is less than the commonly used alpha level of 0.05, we would reject the null hypothesis. This suggests that the promotion times in Department A are significantly different from those in Department B.


## Steps for Conducting a Permutation Test

1. **Select a Test Statistic**: Calculate the test statistic based on the observed data.
2. **Generate Permutations**: Compute the test statistic for all possible combinations of the $ n+m $ observations, where $ n $ and $ m $ are the sizes of the two groups.
3. **Count Extreme Values**: Count the number of permutations that produce a test statistic as extreme as the observed one.
4. **Calculate p-value**: Divide the count from step 3 by the total number of possible permutations $ \binom{n+m}{n} $.

Permutation tests are particularly useful when the data are independent and the null hypothesis posits that all data come from the same distribution. The main limitation has historically been computational, as the number of possible permutations can be very large.

### Inference Scope: Studies vs. Populations

The ability to generalize the findings depends on the study design. In the example given, the data directly concern the employees involved, so there's no need to generalize to a larger population. However, in many studies, especially those involving human subjects, random sampling is not feasible, making it challenging to generalize the findings. 

For randomized experiments, even if the subjects are not randomly sampled from a larger population, the random assignment to treatment groups allows for causal inferences. In such cases, the test is often referred to as a "randomization test" to distinguish it from a standard permutation test.

In summary, the scope of inference can vary widely depending on whether the study involves random sampling, random assignment, or neither. Therefore, caution should be exercised when generalizing the findings to a broader context.

## Activity Q&A



The data below shows the weight loss for participants on two different diets, A and B:


| Diet A | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 |
|--------|---|---|---|---|---|---|---|---|----|----|
| Diet B | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9  | 10 | 11 | 12 | 13 | 14 |


### Questions and Answers

1. **Discuss the Data and the Issues**

    - **Question**: What is the question being posed in this example?
    - **Answer**: The question is whether Diet A is more effective than Diet B in terms of weight loss.

2. **Null Hypothesis**

    - **Question**: What would be your null hypothesis for these data?
    - **Answer**: The null hypothesis would be that both diets are equally effective in weight loss.

3. **Type of Test**

    - **Question**: Would you use a one-sided or two-sided alternative hypothesis?
    - **Answer**: A one-sided alternative hypothesis would be appropriate here, as we are interested in whether Diet A is more effective than Diet B.

4. **Appropriate Tests**

    - **Question**: Which tests from your introductory course could be appropriate here? What reservations might you have?
    - **Answer**: A two-sample t-test could be considered. However, the sample sizes are different, and we don't know if the data are normally distributed, which are assumptions for the t-test.

5. **Choosing a Test Statistic**

    - **Question**: Why is the difference in group means a viable choice for a test statistic?
    - **Answer**: The difference in group means directly addresses the question of whether one diet is more effective than the other in terms of weight loss.

6. **Number of Regroupings**

    - **Question**: How many ways can the data be regrouped?
    - **Answer**: The number of ways to choose 10 observations from 24 is $ \binom{24}{10} = 1961256 $.

7. **Example Regrouping**

    - **Question**: What would be the test statistic for the regrouping `(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)`?
    - **Answer**: The test statistic would be $ \bar{x} - \bar{y} = 5.5 - 11.5 = -6 $.

8. **Number of Specific Regroupings**

    - **Question**: How many ways are there to regroup the data so that Diet B has the numbers `(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)`?
    - **Answer**: There's only one way to achieve this specific regrouping.

9. **Table of Test Statistics**

    - **Question**: Fill in the table below for different regroupings.
    - **Answer**:

    
    | Diet B data                        | Test Statistic | No. of Regroupings |
    |------------------------------------|----------------|--------------------|
    | (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)    | -6             | 1                  |
    | (2, 3, 4, 5, 6, 7, 8, 9, 10, 11)   | -5             | 1                  |
    | (3, 4, 5, 6, 7, 8, 9, 10, 11, 12)  | -4             | 1                  |
    

10. **Total Number of Extreme Cases**

    - **Question**: How many ways are there to regroup the data so that the test statistic is at least as extreme as the case observed?
    - **Answer**: There are 3 ways to regroup the data so that the test statistic is at least as extreme as the case observed.

11. **Compute the p-value**

    - **Question**: What is the p-value for the test?
    - **Answer**: $ \frac{3}{1961256} \approx 1.53 \times 10^{-6} $

12. **Conclusions**

    - **Question**: What would you conclude about the hypothesis of interest?
    - **Answer**: The p-value is extremely low, providing strong evidence against the null hypothesis. This suggests that Diet A is more effective than Diet B.


## 16. R Notes

To perform this test in R, you can use the `perm.test` function from the `coin` package. The function allows you to perform a variety of permutation tests.

```R
# Install and load the package
install.packages("coin")
library(coin)

# Enter the data
dietA <- c(2, 3, 4, 5, 6, 7, 8, 9, 10, 11)
dietB <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14)

# Perform the test
test_result <- perm.test(dietA, dietB, alternative = "two.sided")
print(test_result)
```

This will output the test statistic and the p-value, among other details.