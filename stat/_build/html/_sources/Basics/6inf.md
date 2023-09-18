# Inference

Inference is the art of making deductions using statistics.

## The Normal Distribution

The probability density function for a distribution of the form $N(\mu,\sigma^2)$ is defined as:

$$\frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^2}$$

As a general rule of thumb, in normal distibutions, about 68% of the area under the density curve is within one standard deviation of the mean, 95% within two standard deviations, and 99% within three standard deviations.

The region with in two standard deviations of the mean is called the **95% confidence interval**. This means that given a normal distribution, we are 95% confident a value from the data was within the region defined by the 95% confidence interval.

## Point Estimation and Confidence Intervals

- The mean $\mu$ can be estiamted as the sample mean $\bar{x}$.

    The sample mean is given by the following equation: $$\bar{x}=\frac{1}{n}\sum_{i=1}^n x_i $$

    If we opt for estimating the mean with the sample mean, then we define $\bar{x} \sim N(\mu,\frac{\sigma^2}{n})$. This reminds us that the sampl mean varies from sample to sample.

- We can estimate the variance $\sigma^2$ for a sample with the following equation: $$s_a^2 = \frac{1}{n-1}\sum_{i=1}^n(x_i-\bar{x})^2$$

    Recall: $$\sum_{i=1}^n(x_i-\bar{x})^2= \sum_{i=1}^n x_i-n\bar{x}^2$$

- Confidence intervals for $\sigma^2$ can be calculated with the help of the the chi-sqaured distrubtion:$$\frac{\sum_{i=1}^n(x-\bar{x})^2}{\chi_{n-1}^2(1-\alpha /2)} < \sigma^2 < \frac{\sum_{i=1}^n(x-\bar{x})^2}{\chi_{n-1}^2(\alpha /2)} $$
    Where $n$ is the sample size, and $\alpha/2$ and $1-\alpha/2$ are the percentile points for the $\chi^2$ distribution.
    
    The tables for the Chi-squared distribution tend to be of the percentile points. That is, you provide a probability (or percentile) and table tells you the value on the horizontal axis such that the area under to the curve to the left of that point is the probability you chose. i.e. if $Y\sim\chi^2_6$, then tables tell us that $P(Y<2.753)=0.40$ so we would callue the value 2.753 the 40 percentile point of the given distribution. Hence $\chi^2_6(0.40)=2.753$.

- The assumption that the variable $$\frac{\bar{x}-\mu}{s_a/\sqrt{n}}$$ takes the standard Normal distribution is not enitrely accurate when the sample size $n$ is less than 20.

    So when asked to find an unkown in the variable, we can use the t distribtution tables to look up the solution. The t table lookup is similat to the chi squared lookup in the following ways:
    - The degrees of freedom are 1 less than the sample size.
    - The $\alpha$ value in $t_n(\alpha)$ is the percentile point for which we want to find the area underneath the curve left of the result.

    For example:

    The duration of time nine students in a hall of residence revised for an examination had an average of 19.0 hours, the standard deviation being 2.7. Assuming an underlying Normal distribution, to find a $95 \%$ confidence interval for the mean amount of time spent revising, determine

    $$
    \frac{\bar{x}-\mu}{s_{a} / \sqrt{n}}=\frac{19-\mu}{2.7 / \sqrt{9}}
    $$

    and compare this to the $t_{8}$ distribution. Now the upper and lower percentiles required here are

    $$
    \begin{aligned}
    & t_{8}(0.025)=-2.306 \\
    & t_{8}(0.975)=2.306
    \end{aligned}
    $$

    (note the symmetry), hence

    $$
    -2.306<\frac{\bar{x}-\mu}{s_{a} / \sqrt{9}}<2.306
    $$

    with probability 0.95. Rearranging, we find

    $$
    16.925<\mu<21.075
    $$

    is the required interval.

## Hypothesis Testing

$H_0$ - nuul hypothesis.

$H_1$ - alternative hypothesis.

It is hard to prove a hypothesis true, but we may prove it is false without a doubt.

$H_0$ is assumed to be true unless the evidence points against it.

When assesing the evidence in favour of $H_0$ being true, there are two types of errors:
- type 1 error - we reject $H_0$ when it is true. We denote the probability of this event as $/alpha$. This error is equivalent of convicting an innocent defendant in trial.
- type 2 error -the accepatnce of $H_0$ when it is false.  We denote the probability of this event as $/beta$. This error is equivalent of acquitting a guilty defendant in trial. 
- the **size** of the test is the probability of type 1 error.
- the **power** of the test is one minus the probability of a type 2 error.
- The value of $\alpha$ chosen for a test is called the **significance** level. Often chosen at $0.05$, which means we would expect to reject $H_0$ when it is true about one in twenty times.
- In other words, if the null hypothesis is true, and we repeatedly took many samples and calculated the test statistic each time, about 5% of those test statistics would fall in the critical region just by chance. These would be instances where we would incorrectly reject the null hypothesis, assuming it is actually true.

The outcome of a hypothesis test that is often stated is the **p value**. The p value is ht eporbability of observing a test statistic as least as inconsistent with the $H_0$ observed.

When testing a hypohtesis about the mean of a Normal distribution, if the variance is unkown and the sample size if fairly small (<25), the **t test** should be used. The t-test is done by estimating the variance as: $$S_A^2 = \frac{1}{n-1}\sum_{i=1}^n(x_i-x\bar{x})^2$$

and then use the t distribution on n-1 degrees of freedom rather than the standard normal.  In other word, if $H_0: \mu_x=\mu$ is true than $$\frac{\bar{x}-\mu}{s_a/\sqrt{n}}\sim t_{n-1}$$

To summarize the steps to perform a t-test:

1. Calculate the mean of the sample $\bar{x}$. 2. Find the adjusted sample variance $s_{a}^{2}$ and its square root, the adjusted standard deviation $s_{a}$.

3. Work out the value of $$
\frac{\bar{x}-\mu_{0}}{s_{a} / \sqrt{n}}$$ Call its value $t$, say.

4. We must compare the value of $t$ with the $t$ distribution on $n-1$ degrees of freedom. If the null hypothesis is true, $t$ should be consistent with $t_{n-1}$. Otherwise, the value of $t$ is likely to be too large or too small, depending what the alternative hypothesis $H_{1}$ suggests. Find your set of tables of the $t$ distribution, and locate the line giving the percentile points for the case with $n-1$ degrees of freedom.

5. Decide what the critical region of the test should be for the given alternative hypothesis and chosen significance level. Is it values of $t$ too large, too small or both that comprise the rejection zone for $H_{0}$ ? That is, decide whether the critical region is one- or two-sided, and find the region for your test using the tables.

6. Decide whether the value of $t$ you have calculated lies in or out of the critical region. If it lies inside the critical region, you must reject $H_{0}$. Otherwise, the null hypothesis is accepted.

Often it is necessary to compare the sample values from two populations. In this case, unless otherwise stated, the two samples are assumed to be independant of one another and we denote the sample sizes and means as $n_X$, $n_Y$, $\bar{x}$, and $\bar{y}$ respectivley.

- In this case, if $X$ and $Y$ are independent, with $$X \sim N(\mu_X,\sigma_X^2)$$ $$Y \sim N(\mu_Y,\sigma_Y^2)$$ Then $$X-Y \sim N(\mu_X-\mu_Y,\sigma_X^2+\sigma_Y^2)$$
and the sample means follow: $$\bar{x}-\bar{y} \sim N(\mu_X-\mu_Y,\frac{\sigma_X^2}{n_X} + \frac{\sigma_Y^2}{n_Y}$$

- If $\sigma_{X}^{2}$ and $\sigma_{Y}^{2}$ are unknown, as will usually be the case, and furthermore if

    1. $n_{X}$ and $n_{Y}$ are small (less than twenty, as a rule of thumb) and

    2. it is reasonable to assume that $\sigma_{X}^{2}=\sigma_{Y}^{2}=\sigma^{2}$ (say)

    Then here, as in the case for inferences about a single Normal mean, results can be drawn on comparison of a suitable statistic with an appropriate $t$ distribution. If $n=n_{X}+n_{Y}$ is the total sample size, then $$\frac{(\bar{x}-\bar{y})-\left(\mu_{X}-\mu_{Y}\right)}{\sqrt{\frac{s_{p}^{2}}{n_{X}}+\frac{s_{p}^{2}}{n_{Y}}}} \sim t_{n-2}$$ in which $$ s_{p}^{2}:=\frac{\left(n_{X}-1\right) s_{a, X}^{2}+\left(n_{Y}-1\right) s_{a, Y}^{2}}{\left(n_{X}-1\right)+\left(n_{Y}-1\right)}$$ is the pooled estimate of the unknown variance $\sigma^{2}$, i.e., the weighted mean of the two sample estimates. 

Sometimes we are interested in making inference about two population means
based on samples of equal size where the data must be treated in pairs.

- In this case, we assume there are $n$ pairs of observations, $\left(x_{1}, y_{1}\right), \ldots,\left(x_{n}, y_{n}\right)$, and we are interested in the difference in the underlying population means, $\mu_{X}-\mu_{Y}$. We calculate the $n$ differences $d_{i}=x_{i}-y_{i}$, and find the mean difference $\bar{d}$. As the differences might reasonably take a Normal distribution (at least approximately by the CLT if $n$ is reasonably large even when $X$ and $Y$ themselves are not Normal), inference is based on

    $$
    \frac{\bar{d}-\left(\mu_{X}-\mu_{Y}\right)}{s_{d} / \sqrt{n}} \sim t_{n-1},
    $$

    where

    $$
    s_{d}^{2}:=\frac{1}{n-1} \sum_{i=1}^{n}\left(d_{i}-\bar{d}\right)^{2} .
    $$

    Hence, for example, a $100(1-\alpha) \%$ confidence interval for $\mu_{X}-\mu_{Y}$ is

    $$
    \bar{d} \pm t_{n-1}(\alpha / 2) \frac{s_{d}}{\sqrt{n}} .
    $$

## The Central Limit Theorem

his Chapter is concerned with statistical inference about data that are assumed to be from a Normal distribution. Hence a histogram of any data set appropriate for the methods described should, at least approximately, resemble the familiar “bell—shape” of the Normal density function.

The central limit theorem states the provided a sample size $n$ is reasonably large (30 or so should be adequete), the distribution of a sample mean is always Normal:

$$\bar{x} \sim N(\mu,\frac{\sigma^2}{n}$$

and hence:

$$\frac{\bar{x}-\mu}{\sigma/\sqrt{n}}\sim N(0,1)$$