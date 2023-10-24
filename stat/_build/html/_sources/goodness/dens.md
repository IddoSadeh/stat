
# Density curve fitting

This is essentially a simple extension of the Chi-squared test we met in the last section, but adapted to test for the fit of more general distributions. We begin with a motivating example.

## Example  
Below is a tabulation of the lengths (in seconds) of a thousand telephone calls coming in to an exchange (Hoel, 1984, p.109):

| Duration (secs) | Frequency |
|-----------------|-----------|
| 0-100           | 6         |
| 100-200         | 28        |
| 200-300         | 88        |
| 300-400         | 180       |
| 400-500         | 247       |
| 500-600         | 260       |
| 600-700         | 133       |
| 700-800         | 42        |
| 800-900         | 11        |
| 900-1000        | 5         |


Plotting a histogram of the above data, a Normal model suggests itself. Is this reasonable?

In treating the data as being Normal one is mentally fitting to the histogram a Normal density curve. That is to say, one is imagining a curve of the form

$$
c \frac{1}{\sqrt{2 \pi \sigma^{2}}} \exp \left(-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^{2}\right)
$$

passing through the histogram, for some suitable scaling constant $c$. If such a model were reasonable, we recall that good point estimators of the parameters $\mu$ and $\sigma^{2}$ are the sample mean $\bar{x}$ and the (adjusted) sample variance $s^{2}$ respectively. Essentially then the problem reduces to how well the $N(\bar{x}, s)$ distribution appears to fit the data in hand.

The Chi-squared test has a role here: we compare the observed counts in each of the sets with the counts expected under the $N(\bar{x}, s)$ model. The comparison is via the Chi-squared test statistic

$$
\chi^{2}=\sum_{i=1}^{k} \frac{\left(o_{i}-e_{i}\right)^{2}}{e_{i}}
$$

where $k$ is the number of sets for which we have counts, and $o_{i}$ and $e_{i}$ are the observed and expected number respectively in class $i$.

*Remark:* There is a subtlety here which should not be overlooked: the value of the test statistic above is a function of the choice of sets over which we
have counts. So if, in our example, we had chosen five sets (say) rather than ten, the test could give different inference.

Let us return to our example regarding the telephone exchange. Calculations based on the raw data give $\bar{x}=475$ secs and $s=151$ secs, so the curve we are fitting to the histogram is of the form

$$
c \frac{1}{151 \sqrt{2 \pi}} \exp \left(-\frac{1}{2}\left(\frac{x-475}{151}\right)^{2}\right)
$$

and since we can work using proportions (and multiply up by 1000 to give expected values), it is not necessary to find the constant $c$. To calculate how many observations we would expect in each interval under the null hypothesis that the data are from a Normal distribution, there are two options easily available to us. Label the boundary points $b_{1}, \ldots, b_{k}$ (here $b_{1}=100, \ldots, b_{10}= 1000$), then either

1. find $z_{i}=\left(b_{i}-475\right) / 151$ for each boundary point $b_{i}$ and then make use of Standard Normal tables, or

2. use the <code>pnorm</code> function in $\mathrm{R}$ :

<code>
c2 <-pnorm(c1,mean=475, sd=151, lower.tail=TRUE) 
</code>


where $\mathrm{c} 1=\left(b_{1}, \ldots, b_{10}\right)^{\prime}$. The expected counts can then be found by subtraction, say via $\operatorname{diff}(\mathrm{c} 2)$.

In both cases the results, once multiplied by 1000 , give

| Expected | Observed |
|----------|----------|
| 6.4      | 6        |
| 28.0     | 28       |
| 88.6     | 88       |
| 185.5    | 180      |
| 255.1    | 247      |
| 230.3    | 260      |
| 138.0    | 133      |
| 52.3     | 42       |
| 13.3     | 11       |
| 2.2      | 5        |


The value of $\chi^{2}$ computes to 10.4. Now as there are two parameters to be estimated, and ten pairs of frequencies to be compared, the number of degrees of freedom is $9-2=7$. Now $\chi_{7}^{2}(0.95)=14.1$, so if testing at the $5 \%$ significance level there is no evidence to reject the hypothesis here that the calls were Normally distributed.

*Remark:* In general, the number of degrees of freedom in the Chi-squared goodness of fit test is $k-1-p$, where $k$ is the number of categories and $p$ is the number of parameters being estimated. This takes into account the fact that the test is actually apparently favouring the acceptance of the null hypothesis by using the data to estimate the parameters involved.

*Remark:* How should one estimate the p parameters involved? Strictly the answer to this is not easy to implement: the parameter estimates should maximise the probability density of the data for the given choice of boundaries. In practice, however, this latter point is often overlooked. It has been shown that in most instances the effect this has on the power and significance level of the test is small.

Further situations akin to the above are handled in a similar fashion. In particular, if we believed our data were from

1. the $B(n, p)$ distribution, then assuming $n$ was known the test has $k-$ $1-1=k-2$ degrees of freedom;

2. the $P_{o}(\lambda)$ distribution, then the single parameter is estimated by the sample mean and the test has $k-2$ degrees of freedom. If $\lambda$ is assumed known in advance, there would be $k-1$ degrees of freedom.