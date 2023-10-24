# Chi-Squared Goodness of Fit Test

- Used for categorical data.
- No expected value should be less than three.

The official definition is confusing but here is a simple example:

Say you have $n$ possible outcomes for an event. 

You expect (the $H_0$) that the probability of each outcome is $\frac{1}{n}$.

Hence given $k$ trials, you expect each outcome to occur $\frac{k}{n}$ times.

When you perform the trial, you may not get the expected values, to check the hypothesis you calculate:

$$\sum_{i=1}^{n} \frac{(o_i-e_i)^2}{e_i}$$

where $o_i$ is the observed count for outcome $i$ and $e_i$ is the expected.

Now look up the Chi-squared distribution value for the degrees of freedom and your significance level:

$$\chi_{n-1}^2(0.95)$$

If the value you got is larger than the value you found in the Chi-squared distribution you would reject the null hypothesis.