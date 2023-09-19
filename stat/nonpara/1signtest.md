# The Sign Test


The Sign Test serves as a non-parametric statistical method for evaluating the median of a given data set. This test is especially beneficial when the data doesn't follow a normal distribution. 

The test is applicable:
- To data sets that don't require a specific distribution
- For assessing the median value of the data set
- When the data points are not dependent on each other
- The test statistic relies solely on the signs (positive/negative)

## How to Conduct the Sign Test

1. **Compute the Difference**:  
   For each data point $ x_i $, find $ d_i = x_i - \hat{x}_0 $.

2. **Tally the Signs**:  
   Count the occurrences of positive ($ n_+ $) and negative ($ n_- $) differences.

3. **Determine the Test Statistic**:  
   The test statistic $ S $ is the lesser of $ n_+ $ and $ n_- $.

$
S = \min(n_+, n_-)
$

4. **Find the p-value**:  
   Utilize the binomial distribution to calculate the p-value:

$
p = 2 \times \text{Binomial PMF}(k \leq S; n, 0.5)
$

## Additional Information

The median of a random variable $ X $ is the value $ \theta $ where the probabilities of $ X $ being greater or less than $ \theta $ are equal:

$
P(X > \theta) = P(X < \theta)
$

When you have an independent and identically distributed (i.i.d.) sample from $ X $, and $ \theta $ is its median, you'd expect roughly half of the data to be above $ \theta $ and half below. If you calculate $ \theta - x_i $ for each $ i $ and note the sign, you can count the number of positive signs and label this $ t $. Under the null hypothesis that the median is $ \theta $, $ t $ would follow a binomial distribution with parameters $ n $ and $ \frac{1}{2} $.

For large sample sizes, you can use the Normal approximation to the Binomial distribution for comparison. For smaller sample sizes, it's advisable to use software to get the exact Binomial probabilities.

## Example




We have weight gains of mice over a month with a new feeding regimen: $[20, 42, 18, 21, 22, 35, 19, 18, 26, 20, 21, 32, 22, 20, 24]$.

The prior feeding method had a median weight gain of $25g$.

We want to test the following hypotheses:

$
H_0: \theta = 25 \quad \text{(null hypothesis)}
$
$
H_1: \theta < 25 \quad \text{(alternative hypothesis)}
$

### Step 1: Compute the Difference

We subtract $25$ from each data value:

$
d_i = x_i - 25
$

The differences are $[-5, 17, -7, -4, -3, 10, -6, -7, 1, -5, -4, 7, -3, -5, -1]$.

### Step 2: Tally the Signs

We note the signs of each difference:

$
-+---+--+--+---
$

We find $n_+ = 4$ (number of positive differences) and $n_- = 11$ (number of negative differences).

### Step 3: Determine the Test Statistic

The test statistic $S$ is the lesser of $n_+$ and $n_-$:

$
S = \min(4, 11) = 4
$

### Step 4: Find the p-value

For small sample sizes like $n=15$, we can use the binomial distribution to find the p-value. However, in this example, we'll use the Normal approximation with a continuity correction, as done in the original example:

$
Z = \frac{4 + \frac{1}{2} - \frac{15}{2}}{\sqrt{\frac{15}{4}}} = \frac{4.5 - 7.5}{\sqrt{3.75}} = \frac{-3}{\sqrt{3.75}} = -1.55
$

Using a standard Normal distribution table or software, we find $P(Z \leq -1.55) = 0.06$.

### Conclusion

Since the p-value of $0.06$ is greater than the significance level of $0.05$, we fail to reject the null hypothesis $H_0$. This suggests that there is weak evidence against the null hypothesis, and we cannot conclude that the new feeding regimen leads to a different median weight gain.

This should closely mirror the calculations and conclusions in the original example.


## Sign Test Activity Sheet

Suppose a school wants to test the effectiveness of a new teaching method for improving math scores. They randomly select 12 pairs of similar classes. One class in each pair uses the new teaching method, while the other sticks to the traditional method. After a semester, they compare the average improvement in test scores for each pair. A "+" indicates that the class with the new method showed greater improvement, and a "-" indicates the opposite.


| Class pair | Outcome |
|------------|---------|
| 1          | +       |
| 2          | -       |
| 3          | +       |
| 4          | -       |
| 5          | +       |
| 6          | +       |
| 7          | -       |
| 8          | +       |
| 9          | +       |
| 10         | -       |
| 11         | +       |
| 12         | +       |


### Questions and Answers

1. **Purpose of the Study**

    - **Question**: What was the aim of this study?
    - **Answer**: The study aimed to assess the effectiveness of a new teaching method on improving math scores.

2. **Type of Study**

    - **Question**: What type of study is this?
    - **Answer**: This is an experimental study.

3. **Null Hypothesis**

    - **Question**: What would be your null hypothesis based on the given data?
    - **Answer**: The null hypothesis states that there is no difference in the improvement of math scores between the new and traditional teaching methods.

4. **Expected Value of Test Statistic**

    - **Question**: What would be the expected value of your test statistic under the null hypothesis?
    - **Answer**: Under the null hypothesis, the expected value $ E[T] $ would be $ \frac{12}{2} = 6 $.

5. **One-sided or Two-sided Test**

    - **Question**: Would you choose a one-sided or two-sided test?
    - **Answer**: A two-sided test is probably most appropriate here, as it's not clear whether the new method could perform worse or better than the traditional method.

6. **Inconsistency with Null Hypothesis**

    - **Question**: How many outcomes could be at least as inconsistent with the null hypothesis as the one observed?
    - **Answer**: There are 24 possibilities that are as inconsistent or more inconsistent with the null hypothesis. This includes 12 possibilities with one "-" and 11 "+", and 12 with one "+" and 11 "-".

7. **Sampling Distribution**

    - **Question**: Can you sketch the sampling distribution for the test statistic under the null hypothesis?
    - **Answer**: The sampling distribution under $ H_0 $ would follow a binomial distribution $ B(12, \frac{1}{2}) $.

8. **Computing the p-value**

    - **Question**: How would you compute the p-value for this test, assuming a two-sided alternative?
    - **Answer**: In this example, we have 12 pairs, and 8 of them showed that the new teaching method is better ("+"). If the null hypothesis is true—that is, if the new teaching method has no effect—then each pair has a 50% chance of showing a "+" and a 50% chance of showing a "-". 

    The test statistic follows a binomial distribution $ B(12, \frac{1}{2}) $. To find the p-value, we sum the probabilities of observing 8 or more "+" and 4 or fewer "-". 

    Using the binomial probability formula $ P(x) = \binom{n}{x} \times p^x \times (1-p)^{(n-x)} $, where $ \binom{n}{x} $ is the number of combinations of $ n $ items taken $ x $ at a time, $ p $ is the probability of a single success, and $ n $ is the number of trials, we get:

    $
    p_{\text{value}} = 2 \times \left( \sum_{x=8}^{12} \binom{12}{x} \times 0.5^x \times 0.5^{(12-x)} \right)
    $

    Calculating this gives:

    $
    p_{\text{value}} = 2 \times \left( \binom{12}{8} \times 0.5^8 \times 0.5^4 + \binom{12}{9} \times 0.5^9 \times 0.5^3 + \binom{12}{10} \times 0.5^{10} \times 0.5^2 + \binom{12}{11} \times 0.5^{11} \times 0.5^1 + \binom{12}{12} \times 0.5^{12} \times 0.5^0 \right)
    $

    $
    p_{\text{value}} = 2 \times \left( 0.1208 + 0.0537 + 0.0164 + 0.0029 + 0.0002 \right)
    $

    $
    p_{\text{value}} = 2 \times 0.1940 = 0.3880
    $

    The p-value is approximately 0.388, which is not significant at the 0.05 level. Therefore, we fail to reject the null hypothesis.

9. **R Notes**

    - **Question**: How would you perform this test in R?
    - **Answer**: You can use the `binom.test()` function in R. For this data, you would use `binom.test(8, 12)` for a two-sided test. To perform a one-sided test assuming the new method is better, you would use `binom.test(8, 12, alternative = "greater")`.
