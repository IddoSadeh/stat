# Multiple Comparisons

Sometimes in ANOVA settings the null hypothesis is uninteresting - it is obvious that the underlying means are not equal. More interesting is to investigate which factor level seems to have the highest or lowest impact on the response.

To study pairwise comparisons, we must recall that the overall significance of many individual hypothesis tests would be over-inflated. That is, if we perform all

$$
G=\left(\begin{array}{l}
g \\
2
\end{array}\right)=\frac{g(g-1)}{2}
$$

tests, at the $5 \%$ level say, it is probable that just by chance one (or more) would be significant when actually all group effects are the same.

To accommodate this we set the individual significance levels smaller, to

$$
\frac{0.05}{G}
$$

This compensates, and it can be shown that the chance of a single type I error is now no more than 0.05 .

To compare two groups, $l$ and $m$ say, we base inference on

$$
\bar{y}_{l \cdot}-\bar{y}_{m . .}
$$

Now the model implies that $\bar{y}_{l}-\bar{y}_{m}$. has variance

$$
\frac{\sigma^{2}}{n_{l}}+\frac{\sigma^{2}}{n_{m}}
$$

and we would estimate the square root of this by

$$
\operatorname{ESD}\left(\bar{y}_{l}-\bar{y}_{m .}\right)=\left(\frac{s_{p}^{2}}{n_{l}}+\frac{s_{p}^{2}}{n_{m}}\right)^{\frac{1}{2}}
$$

The value of $\bar{y}_{l}-\bar{y}_{m}$. will be considered significantly (at the $5 \%$ level) different from zero if its absolute value is greater than

$$
d_{l, m}=t_{n-g}\left(1-\frac{0.05}{2 G}\right)\left(\frac{s_{p}^{2}}{n_{l}}+\frac{s_{p}^{2}}{n_{m}}\right)^{\frac{1}{2}}
$$

where $t_{n-g}(1-0.05 / 2 G)$ is the $(1-0.05 / 2 G) 100$ percentile point of the $t_{n-g}$ distribution.

**Remark 5** *The d.o.f. here is determined by the estimator of $\sigma^{2}$, i.e., $s_{p}^{2}$, not by the sizes of the two groups being compared.*

**Example** 

In the cycling club case, there are 4 groups and so

$$
\left(\begin{array}{l}
4 \\
2
\end{array}\right)=\frac{4(4-1)}{2}=6
$$

pairwise comparisons. We find for $l, m=A, B, C, D$,

$$
d_{l, m}=t_{19}\left(1-\frac{0.05}{12}\right)\left(\frac{467}{n_{l}}+\frac{467}{n_{m}}\right)^{\frac{1}{2}}
$$

where

$$
t_{19}(1-0.004167)=t_{19}(0.996)=2.96
$$

Hence as, for instance,

$$
d_{A, B}=2.96\left(\frac{467}{6}+\frac{467}{4}\right)^{\frac{1}{2}}=41.29
$$

the table of pairwise comparisons is:

| Groups | Difference | $d_{l, m}$ | Significant? |
| :---: | :---: | :---: | :---: |
| $A-B$ | 22.08 | 41.29 | $N$ |
| $A-C$ | 11.40 | 34.38 | $N$ |
| $A-D$ | 7.66 | 35.68 | $N$ |
| $B-C$ | -10.68 | 38.74 | $N$ |
| $B-D$ | -14.42 | 41.29 | $N$ |
| $C-D$ | -3.74 | 34.38 | $N$ |

Unsurprisingly (recall, $H_{0}$ was not rejected here) none of the differences appear significant.
