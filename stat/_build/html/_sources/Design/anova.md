# ANOVA

We describe now a statistical technique called ANOVA.

The aim throughout is to study the relationship of a response variable $Y$, say, with explanatory variables that are factors.

A factor is an explanatory variable that exists at different levels, the levels being controlled by the experimenter. Levels of factors may be either qualitative or quantitative, and the set of factors levels applied to a particular experimental unit may be thought of as treatments in the context of the experiment.

The approach here involves splitting the variation in the response variable into components that enable judgements to be made about the relationship between the response and the factors. Hence the name: the analysis of variance.

A simple example illustrates the type of problem under consideration:

The following data are from a chemical plant and give the yields (in $\mathrm{kg}$ ) that resulted from trying four different catalysts in a chemical process.

| |  |  |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Catalyst 1 | 36 | 33 | 35 | 34 | 32 | 34 |
| Catalyst 2 | 35 | 37 | 36 | 35 | 37 | 36 |
| Catalyst 3 | 35 | 39 | 37 | 38 | 39 | 38 |
| Catalyst 4 | 34 | 31 | 35 | 32 | 34 | 33 |

It is of interest to determine whether the catalyst used affects the yield produced in the process. Here we have one qualitative factor with four levels.

The response is the amount of yield at each trial. There were six replications at each level of the factor, giving 24 trials in total in the experiment.

## The basic model

Much of Statistics involves the setting up of "models" to replicate real--world situations of interest. These models will include random variables to describe the inherent randomness in the process under consideration, as well as various parameters which are likely to be unknown and may have to be estimated via the data. The following is a very simple statistical model, but it is important to appreciate its role in the analysis of variance, since without its assumptions the testing of hypotheses will be invalid.

We require some notation in order to describe the situation. Let us assume that we have $g$ groups, and $t$ observations in each. (There is no necessity to enforce equal numbers in each group, but it makes the formulae easier, and in any case nearly always gives a more sensible experiment. We relax this constraint later.) Let $y_{i j}$ denote the $j$ th observation in the $i$ th group (for $i=1,2, \ldots, g, j=1,2, \ldots, t)$. The overall mean of these values is obviously

$$
\bar{y}=\frac{1}{g t} \sum_{i=1}^{g} \sum_{j=1}^{t} y_{i j}
$$

The model we must assume in the analysis of variance (ANOVA, for short) can be written as the following:

$$
y_{i j}=\mu+\alpha_{i}+\varepsilon_{i j}
$$

in which

- $\mu$ is the expected value of $\bar{y}$,
- $\alpha_{i}$ is the group (or treatment) effect for group $i, i=1, \ldots, g$,
- $\varepsilon_{i j}$ are independent error variables, assumed to be from the $N(0, \sigma)$ distribution for some $\sigma^{2}$.

We will let $\bar{y}_{i}$. denote the sample mean in the $i$ th group. Then since $\bar{y}$ is the mean of the group means, we have

$$
\sum_{i=1}^{g}\left(\bar{y}_{i}-\bar{y}\right)=0
$$

If we replace the sample values with the values predicted by the model in the above, we see that

$$
\sum_{i=1}^{g}\left(\mu+\alpha_{i}-\mu\right)=\sum_{i=1}^{g} \alpha_{i}=0
$$

since the error terms have mean zero. Therefore, under the model defined, the group effects are constrained to sum to zero.

### Testing the null hypothesis

Under the model formulated above, the null hypothesis for the equality of the means within the groups can be written as

$$
H_{0}: \alpha_{1}=\alpha_{2}=\cdots=\alpha_{g}=0
$$

In words, all the group effects are zero. Analysis of variance attempts to decide on the plausibility of this statement by comparison of the variation within the groups with the variation between the groups. A description follows.

Write the difference of an observation from the overall mean as

$$
y_{i j}-\bar{y}=\left(y_{i j}-\bar{y}_{i}\right)+\left(\bar{y}_{i}-\bar{y}\right) .
$$

Take the above equation, square both sides then sum over all $j$ and all $i$ (i.e., within the groups, then over the groups) to give

$$
\sum_{i=1}^{g} \sum_{j=1}^{t}\left(y_{i j}-\bar{y}\right)^{2}=\sum_{i=1}^{g} \sum_{j=1}^{t}\left(y_{i j}-\bar{y}_{i}\right)^{2}+\sum_{i=1}^{g} \sum_{j=1}^{t}\left(\bar{y}_{i .}-\bar{y}\right)^{2}  \quad (1)
$$

This follows since the cross-product term vanishes, because

$$
\sum_{i=1}^{g} \sum_{j=1}^{t}\left(\bar{y}_{i .}-\bar{y}\right)\left(y_{i j}-\bar{y}_{i .}\right)=\sum_{i=1}^{g}\left(\left(\bar{y}_{i .}-\bar{y}\right) \sum_{j=1}^{t}\left(y_{i j}-\bar{y}_{i .}\right)\right)
$$

and the last written sum is just the sum of the observations in the $i$ th group about their mean $\bar{y}_{i}$, and is therefore zero.

In words, we would write (1) as

$$
\text { Overall variability }=\text { Within group } \mathrm{SS}+\text { Between group SS, }
$$

where "SS" is short for "sum of squares". If $H_{0}$ is true, we would expect the within-group variation to be comparable to the between-group variation. If $H_{0}$ is false, then we would expect the Between group SS to dominate the right hand side of (5.1). We summarize some key results to produce a statistical test, reminding ourselves of a distributional result before we begin.

**Remark 1** *If $x_{1}, x_{2}, \ldots, x_{n}$ are independent observations from a Normal distribution with variance $\sigma_{X}^{2}$, and $\bar{x}$ is their sample mean, then if*

$$
s^{2}=\frac{1}{(n-1)} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}
$$

*we have that*

$$
\frac{(n-1) s^{2}}{\sigma_{X}^{2}} \sim \chi_{n-1}^{2}
$$

Let us first consider the Between group SS, namely

$$
\sum_{i=1}^{g} \sum_{j=1}^{t}\left(\bar{y}_{i}-\bar{y}\right)^{2}
$$

As the terms in the summation do not depend on $j$, we can write the above as

$$
t \sum_{i=1}^{g}\left(\bar{y}_{i \cdot}-\bar{y}\right)^{2}
$$

When $H_{0}$ is true, the model states that both the overall sample mean $\bar{y}$ and the sample mean within group $i, \bar{y}_{i}$, should be random variables with mean $\mu$. Further, since the observations are Normally distributed, we have that

$$
\bar{y}_{i .} \sim N\left(\mu, \frac{\sigma}{\sqrt{t}}\right)
$$

under $H_{0}$. It follows now from remark 1 above (putting $n=g, \sigma_{X}^{2}=\sigma^{2} / t$, $x_{i}=\bar{y}_{i}$. and $\bar{x}=\bar{y}$ in that remark) that

$$
\frac{\text { Between group SS }}{\sigma^{2}} \sim \chi_{g-1}^{2}  \quad (2)
$$

Turning now to the Within group SS, for fixed $i, y_{i j} \sim N\left(\mu+\alpha_{i}, \sigma\right)$. In particular, the observations within each group have the same mean and
variance. Since $\bar{y}_{i}$. is their sample mean, it follows from remark 1 (putting $\sigma_{X}^{2}=\sigma^{2}, x_{i}=y_{i j}$ and $\bar{x}=\bar{y}_{i}$.) that

$$
\frac{\sum_{j=1}^{t}\left(y_{i j}-\bar{y}_{i .}\right)^{2}}{\sigma^{2}} \sim \chi_{t-1}^{2}
$$

is true for each group. Since the observations in each group are independent of those in any other group, all $g$ of these Chi-squared variables will be independent of one another. As we know, the sum independent Chi-squared variables is also a Chi-squared variable, with the degrees of freedom adding. Hence we have

$$
\frac{\text { Within group SS }}{\sigma^{2}} \sim \chi_{g(t-1)}^{2} \quad (3)
$$

Before stating the result which leads to the test, we state another distributional result.

**Remark 2** 
*If $X \sim \chi_{m}^{2}$ and $Y \sim \chi_{n}^{2}$ are independent, then*

$$
\frac{X / m}{Y / n} \sim F_{m, n}
$$

*In words, the ratio of two independent Chi-squared variables, each divided by their degrees of freedom, has an $F$ distribution with parameters the respective degrees of freedom dividing the top and bottom variable in the ratio.*

Combining (2) and (3) via the above remark, we have that under $H_{0}$

$$
\frac{\text { Between group SS/ }(g-1)}{\text { Within group SS } / g(t-1)} \sim F_{g-1, g(t-1)}
$$

Now as we know, if $H_{0}$ is false we would expect the between-group variation to dominate the within-group variation, so would expect the ratio above to be inflated when the underlying group effects differ. Therefore, our critical region will lie in the upper tail of the appropriate $\mathrm{F}$ distribution.

**Remark 3** *The above argument appears quite plausible, until one has a closer look at remark 2. The result follows only when the Chi-squared variables are **independent**. Are the Between group SS and Within group SS statistically independent? It turns out that they are, but no justification has been given for this assumption. A more detailed discussion of results of this sort appears in a more advanced Statistics course.*

Having worked out the sums of squares from the data, the results are usually tabulated in a table, called the ANOVA table.

| Source | Sum of Squares | d.o.f. | MS | F |
| :---: | :---: | :---: | :---: | :---: |
| Between | $t \sum_{i=1}^{g}\left(\bar{y}_{i .}-\bar{y}\right)^{2}$ | $g-1$ | $t \sum_{i=1}^{g}\left(\bar{y}_{i .}-\bar{y}\right)^{2} /(g-1)$ |  |
| Within | $\sum_{i=1}^{g} \sum_{j=1}^{t}\left(y_{i j}-\bar{y}_{i .}\right)^{2}$ | $g(t-1)$ | $\sum_{i=1}^{g} \sum_{j=1}^{t}\left(y_{i j}-\bar{y}_{i .}\right)^{2} / g(t-1)$ | $\frac{\text { Between group MS }}{\text { Within group MS }}$ |
| Total | $\sum_{i=1}^{g} \sum_{j=1}^{t}\left(y_{i j}-\bar{y}\right)^{2}$ | $g t-1$ |  |  |

In the above "d.o.f." stands for "degrees of freedom", and "MS" stands for "mean square", being the sum of squares divided by its degrees of freedom.

**Remark 4** *The Within group SS is sometimes called either the Error SS or the Residual SS, as it gives an indication of experimental variation without the effects of the explanatory variable under consideration.*

**Example:** 

Let us return to our initial example. The group means are

$$
\begin{aligned}
& \bar{y}_{1 .}=34.00 \\
& \bar{y}_{2 .}=36.00 \\
& \bar{y}_{3 .}=37.67 \\
& \bar{y}_{4 .}=33.17,
\end{aligned}
$$

and the overall mean is $\bar{y}=35.21$. To find the Between group SS, note

$$
\sum_{i=1}^{4}\left(\bar{y}_{i \cdot}-\bar{y}\right)^{2}=12.30
$$

is the "variation" in the group means, so

$$
\sum_{i=1}^{4} \sum_{j=1}^{6}\left(\bar{y}_{i \cdot}-\bar{y}\right)^{2}=6 \times 12.30=73.80
$$

If working by hand, it is easiest to find the Total (corrected) SS, and then the Within group SS by subtraction. The Total SS is

$$
\sum_{i=1}^{4} \sum_{j=1}^{6}\left(y_{i j}-\bar{y}\right)^{2}=109.96
$$

and then we find

$$
\sum_{i=1}^{4} \sum_{j=1}^{6}\left(y_{i j}-\bar{y}_{i .}\right)^{2}=109.96-73.80=36.16
$$

Presenting the results as an ANOVA table gives the following:

| Source | $S S$ | dof | Mean Square | $F$ |
| :---: | :---: | :---: | :---: | :---: |
| Catalyst | 73.80 | 3 | 24.60 | 13.6 |
| Error | 36.16 | 20 | 1.81 |  |
| Total | 109.96 | 23 |  |  |

*To test the null hypothesis that the catalysts all have the same effect, we look at the mean square ratio, 24.60/1.81 = 13.6. This figure is to be compared with the $F_{3,20}$ distribution. Now the $95 \%$ point of this distribution is 3.10, and as 13.6 is greater than this value it lies in the critical region, we must reject the null hypothesis at the 5\% level. It would appear that the catalyst present does have an effect on the yield.*

### Unequal sample sizes

We hitherto assumed that there were $t$ observations in each of the $g$ groups. This is usually a sensible design. However the ideas are the same when group $i$ contains $n_{i}$ observations, with

$$
n=\sum_{i=1}^{g} n_{i}
$$

Now

$$
\bar{y}_{i .}=\frac{1}{n_{i}} \sum_{j=1}^{n_{i}} y_{i j}
$$

with the model asserting that

$$
\bar{y}_{i \cdot} \sim N\left(\mu+\alpha_{i}, \frac{\sigma}{\sqrt{n_{i}}}\right)
$$

for $i=1, \ldots, g$.

The total sum of squares is

$$
\sum_{i=1}^{g} \sum_{j=1}^{n_{i}}\left(y_{i j}-\bar{y}\right)^{2}=\sum_{i=1}^{g} \sum_{j=1}^{n_{i}}\left(y_{i j}-\bar{y}_{i .}\right)^{2}+\sum_{i=1}^{g} \sum_{j=1}^{n_{i}}\left(\bar{y}_{i .}-\bar{y}\right)^{2} \quad (4)
$$

this following by an identical argument to the equal sample size case.

As before, we have

Overall variation $=$ Within group SS + Between group SS,

where

$$
\text { Within group } \mathrm{SS}=\sum_{i=1}^{g} \sum_{j=1}^{n_{i}}\left(y_{i j}-\bar{y}_{i}\right)^{2} \quad (5)
$$

and

$$
\begin{aligned}
\text { Between group SS } & =\sum_{i=1}^{g} \sum_{j=1}^{n_{i}}\left(\bar{y}_{i \cdot}-\bar{y}\right)^{2} \\
& =\sum_{i=1}^{g} n_{i}\left(\bar{y}_{i}-\bar{y}\right)^{2} .
\end{aligned} \quad (6)
$$

These are sometimes called the Error $S S$ and Treatment $S S$ respectively.

The degrees of freedom essentially relates to the number of independent pieces of information in a SS. We deduct one d.o.f. for each parameter estimated.

The degrees of freedom for the SS are easily derived. For the total SS, the d.o.f. must be

$$
\sum_{i=1}^{g} n_{i}-1=n-1
$$

since only $E(\bar{y})$ is estimated.

For the Within group SS, the d.o.f. must be

$$
n-g
$$

since each $E\left(\bar{y}_{i}\right), i=1, \ldots, g$, is estimated.

By subtraction, the Between group SS has d.o.f.

$$
n-1-(n-g)=g-1
$$

| Source | SS | d.o.f. | MS | F |
| :---: | :---: | :---: | :---: | :---: |
| Between | $(6)$ | $g-1$ | $\frac{(6)}{g-1}$ |  |
| Within | $(5)$ | $n-g$ | $\frac{(5)}{n-g}$ | $\frac{(6) /(g-1)}{(5) /(n-g)}$ |
| Total | $(4)$ | $n-1$ |  |  |

The statistic in the final column is compared to the $F_{g-1, n-g}$ distribution.

**Example:**
 
 A cycling club has four groups using different training programs, labelled $A, B, C$ and $D$. The data below give the times (mins) of each member to ride a loop with a $7 \%$ uphill gradient:

| $A$ | $B$ | $C$ | $D$ |
| :--- | :--- | :--- | :--- |
| 84 | 56 | 70 | 47 |
| 93 | 78 | 59 | 73 |
| 83 | 56 | 78 | 104 |
| 61 | 61 | 53 | 71 |
| 121 |  | 104 | 69 |
| 67 |  | 110 | 99 |
|  |  | 40 |  |

The group means are

$$
\bar{y}_{1 .}=84.83, \quad \bar{y}_{2 .}=62.75, \quad \bar{y}_{3 .}=73.43, \quad \bar{y}_{4 .}=77.17 .
$$

The ANOVA table is

| Source | $S S$ | d.o.f. | $M S$ | $F$ |
| :---: | :---: | :---: | :---: | :---: |
| Between | 1220 | 3 | 407 |  |
| Within | 8868 | 19 | 467 | 0.87 |
| Total | 10088 | 22 |  |  |

To decide whether to accept the null hypothesis that the mean times under the four training regimes are the same, we compare

$$
\frac{407}{467}=0.87
$$

with the $F_{3,19}$ distribution. The statistic is far from significant - in fact the p-value here is 0.473. Hence there is no evidence to reject the claim that the regimes have the same mean times.

### Estimating $\sigma^{2}$

Recall it is assumed that observations in each group are Normally distributed with common variance $\sigma^{2}$. How can we estimate this parameter?

Each within-group variance,

$$
s_{i}^{2}=\frac{1}{n_{i}-1} \sum_{j=1}^{n_{i}}\left(y_{i j}-\bar{y}_{i}\right)^{2}
$$

gives an unbiased estimate of $\sigma^{2}$, for $i=1, \ldots, g$. Analogous to the two sample $t$ test, it is natural to pool these estimators to find

$$
\begin{aligned}
s_{p}^{2} & =\frac{\left(n_{1}-1\right) s_{1}^{2}+\cdots+\left(n_{g}-1\right) s_{g}^{2}}{n-g} \\
& =\frac{\sum_{i=1}^{g}\left(n_{i}-1\right) s_{i}^{2}}{n-g} \\
& =\frac{\sum_{i=1}^{g} \sum_{j=1}^{n_{i}}\left(y_{i j}-\bar{y}_{i .}\right)^{2}}{n-g} \\
& =\text { Within group MS. }
\end{aligned}
$$

This is an unbiased estimator of $\sigma^{2}-$ to show this, we need the fact that the mean of the $\chi_{n}^{2}$ is $n$.

**Example:** 

In the cycling club example, the estimate of $\sigma^{2}$ is: Within group $M S=467$.
