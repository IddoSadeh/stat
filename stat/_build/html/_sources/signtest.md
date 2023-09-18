# The Sign Test


## Introduction

The Sign Test is a non-parametric test used to test the median of a distribution. It is particularly useful when the assumptions of normality are not met. 

it is:
- for populations that are distribution free
- for testing the median of the population
- the data needs o be independant
- the test statistic is based on signs only (+/-)

## Theoretical Background

The Sign Test is based on the median $ \tilde{x} $ of a dataset. Given a sample $ x_1, x_2, \ldots, x_n $, the test investigates whether the median is equal to a specified value $ \tilde{x}_0 $.

**Null Hypothesis ($ H_0 $)**:  
$
H_0: \tilde{x} = \tilde{x}_0
$

**Alternative Hypothesis ($ H_a $)**:  
$
H_a: \tilde{x} \neq \tilde{x}_0
$



## Steps for Performing the Sign Test

1. **Calculate the Differences**:  
   Calculate $ d_i = x_i - \tilde{x}_0 $ for each observation $ x_i $.

2. **Count the Signs**:  
   Count the number of positive ($ n_+ $) and negative ($ n_- $) differences.

3. **Calculate the Test Statistic**:  
   The test statistic $ S $ is the smaller of $ n_+ $ and $ n_- $.

$
S = \min(n_+, n_-)
$

4. **Calculate the p-value**:  
   The p-value is calculated using the binomial distribution:

$
p = 2 \times \text{Binomial PMF}(k \leq S; n, 0.5)
$



## Example and Solution

**Example Question**:  
Suppose we have a sample of exam scores: $ [50, 55, 53, 61, 58] $ and we want to test if the median score is 55.

1. **Calculate the Differences**:  
   $ d = [50-55, 55-55, 53-55, 61-55, 58-55] = [-5, 0, -2, 6, 3] $

2. **Count the Signs**:  
   $ n_+ = 2, n_- = 2 $

3. **Calculate the Test Statistic**:  
   $ S = \min(2, 2) = 2 $

4. **Calculate the p-value**:  
   $ p = 2 \times \text{Binomial PMF}(k \leq 2; 4, 0.5) = 2 \times (0.0625 + 0.25 + 0.375) = 1.375 $

Since the p-value is greater than 0.05, we fail to reject the null hypothesis and conclude that the median is not significantly different from 55.



## text notes

The median of a (random variable) r.v. $X$ is the point $\theta$ such that

$$
P(X>\theta)=P(X<\theta) \text {. }
$$

The median is a measure of the location of the distribution of $X$. If we have an i.i.d. sample $x_{1}, \ldots, x_{n}$ from $X$, and $\theta$ is the median of $X$ we would expect roughly equal amounts of the data to lie above and below $\theta$. Suppose we calculate the value $\theta-x_{i}$ for each $i=1, \ldots, n$ and record the sign of each value. Count the number of positives (+'s) and call this number $t$. Under the null hypothesis

$$
H_{0} \text { : The median of } X \text { is } \theta \text {, }
$$

we would have that

$$
t \sim B\left(n, \frac{1}{2}\right)
$$

regardless of the underlying distribution of $X$. If $t$ is too large or too small with respect to this distribution, we would reject $H_{0}$. If there are any values equal to the median proposed in $H_{0}$, we can omit these and reduce $n$ accordingly.

Now, under $H_{0}$,

$$
\begin{aligned}
E(t) & =\frac{n}{2}, \\
\operatorname{Var}(t) & =n \frac{1}{2} \frac{1}{2}=\frac{n}{4} .
\end{aligned}
$$

For large values of $n$, we can use the Normal approximation to the Binomial (equivalently, the Central Limit Theorem) and compare

$$
\frac{t-\frac{n}{2}}{\sqrt{\frac{n}{4}}}
$$

with $N(0,1)$. For $n<20$, it is better to use a continuity correction, adding $\frac{1}{2}$ to the numerator for the left hand critical region, subtracting $\frac{1}{2}$ for the right hand tail region. Better still is to get the Binomial probabilities from software.

Example 1 The following data are the weight gains (in $g$ ) of mice over a month obtained using a new feeding regime: 20, 42, 18, 21, 22, 35, 19, 18, 26, 20, 21, 32, 22, 20, 24. A previous feeding method produces a weight gain over the same period with median $25 \mathrm{~g}$. To test whether the new method produces the same median weight gain compared to the alternative that it produces less, we test

$$
\begin{aligned}
& H_{0}: \quad \theta=25 \text { against } \\
& H_{1}: \quad \theta<25 .
\end{aligned}
$$

We subtract 25 from each of the data values, and record whether the outcome is $a+$ or $a-$. We observe the sequence

$$
-+---+--+--+---
$$

and see $t=4$. We then compare

$$
\frac{4+\frac{1}{2}-\frac{15}{2}}{\sqrt{\frac{15}{4}}}=-1.55
$$

with $N(0,1)$; if $Z \sim N(0,1)$ then (from $R$ or otherwise) we have

$$
P(Z \leq-1.55)=0.06 \text {. }
$$

Therefore we would not reject the null hypothesis $H_{0}$ at the $5 \%$ level, noting that there is some evidence against $H_{0}$, the value of the test statistic being close to significant. The p-value of 0.06 gives some weak evidence against the underlying median weight gain of the new diet being $25 \mathrm{~g}$.

It would be possible to calculate the relevant Binomial probability directly in this case; verify that if $X \sim B\left(15, \frac{1}{2}\right)$ then

$$
\begin{aligned}
& P(X \leq 2) \bumpeq 0.003 \\
& P(X=3) \bumpeq 0.014 \\
& P(X=4) \bumpeq 0.042
\end{aligned}
$$

hence $P(X \leq 4)=0.059$, which demonstrates that the Normal approximation (with the continuity correction) is very good here.

The sign test can be extended to paired data and is then analogous to the paired t test, although the latter requires an assumption of Normality for the within-pair differences. To use the sign test on a sample of pairs $\left(x_{1}, y_{1}\right),\left(x_{2}, y_{2}\right), \ldots,\left(x_{n}, y_{n}\right)$ we find the signs of the differences $x_{i}-y_{i}$ for $i=1, \ldots, n$. We then count up the number of positives, and compare the total to $B\left(n, \frac{1}{2}\right)$ in either a one or two-sided test. We come later to test for matched pair data that is usually preferable to the sign test.
