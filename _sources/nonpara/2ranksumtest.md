# Rank Sum Test


The Rank Sum Test, often denoted by $W$, is a two-sample statistical procedure aimed at evaluating whether two samples originate from the same distribution. Given two samples $x_1, x_2, \ldots, x_m$ from distribution $F_X$ and $y_1, y_2, \ldots, y_n$ from $F_Y$, the null hypothesis $H_0$ is that $F_X = F_Y$.

To perform the test, combine both samples into a single set of $n+m$ elements and assign ranks to each, from the smallest (rank 1) to the largest (rank $n+m$). Compute:

$
W_X = \sum_{i=1}^{m} R_i^X
$

Here, $R_i^X$ are the ranks of the $x$ observations in the combined sample. Under $H_0$, $W_X$ is essentially the sum of $m$ randomly selected integers from the set $1, 2, \ldots, n+m$.

## Alternative Formulation

It's also possible to use $W_Y$, the sum of ranks for the $y$ sample, as both $W_X$ and $W_Y$ are related:

$
W_X + W_Y = \frac{(n+m)(n+m+1)}{2}
$

## Applications and Special Cases

The Rank Sum Test is particularly useful for detecting shifts between two distributions. For instance, if $F_Y(x) = F_X(x - \theta)$, then you're testing $H_0: \theta = 0$ against various alternatives.

## Methods to Determine $W_X$ Under $H_0$

1. Enumerate all possible combinations, which number $\binom{n+m}{m}$. Then, find the probabilities for each possible value of $W_X$ under $H_0$.
2. Critical value tables are available for reference.
3. For sufficiently large $m$ and $n$, $W_X$ can be approximated by a normal distribution:

$
W_X \approx N\left(\frac{m(n+m+1)}{2}, \frac{mn(n+m+1)}{12}\right)
$

## Handling Ties

If there are tied observations, average ranks can be used. Some statistical software adjusts the variance of $W_X$ to account for ties, making the test more conservative.



## Additional Notes

1. The test may not yield an exact significance level due to the discrete nature of the test statistic.
2. Misuse can occur if the underlying distributions for $W_X$ and $W_Y$ are not the same when sample sizes are equal.

## Software Tools

The `wilcox.test` function in R can be used to perform this test, and the `wilcox.exact` function in the `exactRankTests` package is particularly useful when there are ties in the data.

## Example

We'll consider a hypothetical case where employees are divided into two departments, A and B, and we're looking at the time it takes for employees to get their first raise.

### Modified Scenario and Data

In a hypothetical case, Smith Corp. v. Employees, the plaintiff claims that employees in Department A are discriminated against in terms of the time it takes to receive their first raise. The data below, which show times (in months) from hiring to first raise, split by department, are used as evidence:

| Department  | Times to Promotion (in months) |
|-------------|--------------------------------|
| Department A| 5, 7, 12, 14, 18, 21, 22, 23, 24, 25 |
| Department B| 7, 12, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32 |


### Questions and Answers

#### 1. Discuss the Data and Issues

**Original Question**: What is the question being posed by the plaintiff with regards to the data?

The plaintiff is asking whether the data appear consistent with the suggestion that the distributions of times to first raise in the company are the same for the two departments. The plaintiff implies that Department A is discriminated against.

#### 2. Null Hypothesis

**Original Question**: In constructing a test for these data, what would be your null hypothesis?

The null hypothesis would be that the distributions of times to first raise are the same for both departments.

#### 3. One-sided or Two-sided Test

**Original Question**: In conducting a hypothesis test here, would you take a one-sided or two-sided alternative? Does it matter?

A one-sided test seems appropriate, as the plaintiff is arguing that Department A has a longer time before receiving a raise compared to Department B.

#### 4. Appropriate Tests

**Original Question**: Of the tests you have met in your introductory course, which would possibly be appropriate for the case here? What reservations might you have about applying that test to the data given?

A two-sample t-test could be considered, but the assumption of normality may not hold, especially given the small sample size for one of the groups.

#### 5. Replacing Data with Ranks

**Original Question**: Rank the data smallest to largest, giving the smallest number rank 1, the largest rank 31. Re-write the table of data replacing the data by their ranks.

For Department A: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10  
For Department B: 2, 3, 4, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 31

#### 6. Sum of Ranks

**Original Question**: The test is based on the sum of the ranks for one of the samples. Find the sum of the ranks for Department A, $W_{A}$ say.

The sum of the ranks for Department A is $W_{A} = 55$.

#### 7. Inconsistency with Null Hypothesis

**Original Question**: Keeping the sample sizes the same, consider changes to the department associated with each observation; if the null hypothesis were true, in how many ways could the outcomes have come out to be at least as inconsistent with the null hypothesis as that actually observed?

For $W_{A} = 55$, combinations that are as inconsistent are: $ (45, 10) $, $ (46, 9) $, $ (47, 8) $, $ (48, 7) $, $ (49, 6) $, $ (50, 5) $, $ (51, 4) $, $ (52, 3) $, $ (53, 2) $, $ (54, 1) $. So there are 10 ways that $W_{A} \geq 55$.

#### 8. Number of Ways to Label

**Original Question**: How many ways are there to label 31 numbers so that 10 are "Department A" and 21 are "Department B"?

There are $ \binom{31}{10} = 244,862,270 $ ways to allocate the labels to the data points.

#### 9. Computing the $ p $-value

**Original Question**: How would you compute the $ p $-value for the test based on the previous parts, assuming a one-sided alternative?

The $ p $-value would be $ \frac{10}{244,862,270} $.

#### 10. Conclusion

**Original Question**: What would you conclude about the hypothesis of interest? Would you have any reservations about your conclusion?

The $ p $-value is extremely small, suggesting that the null hypothesis is unlikely. However, the sample size for Department A is smaller, which could be a limitation.

#### 11. Larger Sample Sizes

**Original Question**: Suppose the two sample sizes had been much bigger - ten times bigger, say. Which distribution would this statistic approximately follow under the null hypothesis?

The test statistic $ W_{A} $ would approximately follow a Normal distribution under the null hypothesis, according to the Central Limit Theorem.

Certainly, let's complete the activity sheet with questions 12-14.

#### 12. Introduction to the Wilcoxon Rank Sum Test

**Original Question**: This activity introduces a test known as the Wilcoxon rank sum test. Like the sign test, this test makes no explicit assumption about the shapes of the distribution of the two data sets, and so it is also a nonparametric test. There are variants on this test, and a closely related test known as the Mann-Whitney test. These tests, which all share the idea explained in this activity, are alternatives to the two-sample $ t $ test. Such tests are preferable in cases where the data are clearly non-Normal and the sample size is small. Read the notes on the rank sum test from the course website.

Through this activity, we've learned about the Wilcoxon rank sum test, which is a nonparametric alternative to the two-sample $ t $ test. This test is particularly useful when the data are not Normally distributed or when the sample sizes are unequal or small. The test is based on the ranks of the data rather than their actual values, making it less sensitive to outliers and skewed distributions.

#### 13. Recap of the Activity

**Original Question**: Re-cap what you have done during this activity. Why do you think you were asked to do this activity? What have you learned?

During this activity, we've gone through the steps of conducting a Wilcoxon rank sum test using a hypothetical scenario involving two departments in a company. We've learned how to rank data, calculate the sum of ranks for a sample, and compute a $ p $-value to test a hypothesis. This activity helps us understand the utility of nonparametric tests, especially when the assumptions of parametric tests like the $ t $-test are not met.

#### 14. R Notes

**Original Question**: We can apply the Wilcoxon rank sum test in R in two ways. To reproduce closely the activity, we can use the function `wilcox.exact` available in the package `exactRankTests`, which is no longer being updated. However, it is now more common to use R function `wilcox.test`, which will generally give identical results, but will handle tied ranks differently.

To perform the Wilcoxon rank sum test in R, you can use either the `wilcox.exact` function from the `exactRankTests` package for an exact test or the more commonly used `wilcox.test` function for an approximate test. The latter is often preferred as it can handle tied ranks and is more widely supported. Both functions will provide you with a $ p $-value that you can use to make a decision regarding your hypothesis.

Here's how you might use `wilcox.test` in R:

```R
# Data for Department A and B
dept_a <- c(5, 7, 12, 14, 18, 21, 22, 23, 24, 25)
dept_b <- c(7, 12, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32)

# Perform the test
result <- wilcox.test(dept_a, dept_b, alternative = "greater")

# Display the result
print(result)
```

This will output the $ p $-value among other statistics, which you can then interpret to make your conclusion.