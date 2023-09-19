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