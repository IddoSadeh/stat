# Rank Sum Test


This test is for two-sample problems, and is a test for difference in location in the corresponding distributions. We have two samples, $x_{1}, \ldots, x_{m}$ from distribution $F_{X}$ and $y_{1}, \ldots, y_{n}$ from $F_{Y}$. Our null hypothesis is $H_{0}: F_{X}=F_{Y}$. We form the combined sample of size $n+m$ and rank it, giving the smallest number rank 1, the largest rank $n+m$. Find

$$
W_{X}=\sum_{i=1}^{m} R_{i}^{X},
$$

where the $R_{i}^{X}$ are the ranks of the $X$ observations in the combined sample. Assuming no ties and the null hypothesis, $W_{X}$ is the sum of $m$ integers chosen at random (without replacement) from the numbers $1,2, \ldots, n+m$. If the $y_{i}$ 's are on average larger than $x_{i}$ 's then $W_{X}$ will appear to be smaller than would have been expected under $H_{0}$, and vice versa if the reverse situation holds.

Remark 1 We could just as easily use

$$
W_{Y}:=\sum_{i=1}^{n} R_{i}^{Y},
$$

the sum of the ranks of the $y_{i}$ 's, but as

$$
\begin{aligned}
W_{X}+W_{Y} & =1+2+\cdots+(n+m) \\
& =\frac{1}{2}(n+m)(n+m+1)
\end{aligned}
$$

is a constant, the two statistics are equivalent for our purposes.

An important application of this test is to situations where we are testing for slippage, meaning that the two distributions are identical except that one is shifted by some constant $\theta$. So we have, say, $F_{Y}(x)=F_{X}(x-\theta)$. In this case we are testing $H_{0}: \theta=0$ against one of several possible alternatives incorporating the cases when $\theta>0$ (in which case we reject $H_{0}$ if $W_{X}$ is too small), $\theta<0$ (reject if $W_{X}$ is too large) and $\theta \neq 0$ (reject if $W_{X}$ is too large or too small).

Under $H_{0}$, the distribution of $W_{X}$ can be found in various ways:

1. We can enumerate the possibilities. There are $\left(\begin{array}{c}n+m \\ n\end{array}\right)$ ways of ordering the combined sample, each equally likely under $H_{0}$. We could therefore find the probabilities for each of the possible values of $W_{X}$ under $H_{0}$. 2. Tables of critical values exist (see Neave, p.53 for example, though these tables are for $\left.U:=\min \left(W_{X}-\frac{1}{2} m(m+1), W_{Y}-\frac{1}{2} n(n+1)\right)\right)$.

3. If $m$ and $n$ are reasonably large, then under $H_{0}$ approximately

$$
W_{X} \sim N\left(\frac{1}{2} n(n+m+1), \frac{1}{12} m n(m+n+1)\right) .
$$

If there are ties - two observations with the same value - we can use average ranks in the calculation of the test statistic $W_{X}$. Strictly, we ought to adjust the distribution under $H_{0}$ accordingly, as although the mean does not change, $\operatorname{Var}\left(W_{X}\right)$ is slightly reduced in the presence of ties. Some software packages make such an adjustment. Failure to adjust makes the test slightly more conservative in that it fails to reject $H_{0}$ more often than it should.

Example 2 Consider the case when $m=3$ and $n=5$. There are

$$
\left(\begin{array}{l}
8 \\
3
\end{array}\right)=\frac{8 !}{3 ! 5 !}=56
$$

possible sequences of the $x_{i}$ 's and $y_{i}$ 's, each defining a sequence of ranks. So, for example, in the sequence $(x, y, x, x, y, y, y, y)$ the sum of the ranks of the $X$ values is $1+3+4=8$ (and the sum of the $Y$ value ranks is 28). Under the null hypothesis, each the 56 possible sequences are equally likely, and hence we can enumerate the possible values of $W_{X}$ :


\begin{tabular}{c|c}
$X$ ranks & $W_{X}$ \\
\hline $1,2,3$ & 6 \\
$1,2,4$ & 7 \\
$1,3,4$ & 8 \\
$1,2,5$ & 8 \\
$2,3,4$ & 9 \\
$1,2,6$ & 9 \\
$1,3,5$ & 9 \\
$\vdots$ & $\vdots$
\end{tabular}

The probability distribution of the $W_{X}$ values can now be found, and is as follows:

\begin{tabular}{c|cccccc}
$W_{X}$ & 6 & 7 & 8 & 9 & 10 & $\cdots$ \\
\hline Probability & $\frac{1}{56}$ & $\frac{1}{56}$ & $\frac{2}{56}$ & $\frac{3}{56}$ & $\frac{4}{56}$ & $\cdots$
\end{tabular}

To test for no difference in the locations of $F_{X}$ and $F_{Y}$ against the alternative of a shift to the left in $F_{X}$, we would have a critical region including small values of $W_{X}$. Taking $W_{X}=6,7,8$ as the critical region would define a test with significance level $\alpha=\frac{4}{56}$. For a two-sided test, a critical region of $\{6,7,20,21\}$ would have significance level $\alpha=\frac{4}{56}$.

Example 3 A married couple often play a computer game "Diamond Wonderland", and they differ as to which, if either of them, is the better at the game. A random sample of five scores from the husband $(X)$ and four from the wife $(Y)$ are given below, rounded to the nearest thousand.

\begin{tabular}{c|c}
$X$ & $Y$ \\
\hline 5 & 9 \\
7 & 11 \\
13 & 10 \\
8 & 17 \\
4 &
\end{tabular}

The null hypothesis is that the two sets of scores come from the same distribution, $H_{0}: F_{X}=F_{Y}$, and the alternative is $H_{A}: F_{X}(x)=F_{Y}(x-\theta)$ for some $\theta \neq 0$, so that either the husband or wife being better are viable alternatives to the null. We can replace the data with their rankings as follows

\begin{tabular}{c|c}
$R_{X}$ & $R_{Y}$ \\
\hline 2 & 5 \\
3 & 7 \\
8 & 6 \\
4 & 9 \\
1 &
\end{tabular}

and note that $W_{X}=18$. Is this value consistent with the null hypothesis? There are

$$
\left(\begin{array}{l}
9 \\
5
\end{array}\right)=126
$$

ways the husband's five scores could appear in the nine, all equally likely under the null hypothesis; we observe the arrangement $(x, x, x, x, y, y, y, x, y)$ here. The value of $W_{X}$ can be as low as 15 (the arrangement $(x, x, x, x, x, y, y, y, y)$ ) and as high as 35 (when the husband's scores are the five highest values). In fact there are seven arrangements with $W_{X} \leq 18$. As we are taking a two-sided alternative, the upper tail must also be considered - the values of $W_{X} \geq 32$, and by symmetry there are seven such arrangements. So there are 14 out of the 126 possible arrangements at least as inconsistent with the null hypothesis as the one actually observed. Collectively these have probabability 0.111 under $H_{0}$, this being the $p$-value of the statistic. Therefore there is only weak evidence against the null hypothesis that the scores of the husband and wife follow the same distribution.

Remark 2 If ties had occurred in the data above, we assign the average of the ranks that would have been assigned had the tied values been different. For instance, in the above example suppose the data been as follows:

\begin{tabular}{c|c}
$X$ & $Y$ \\
\hline 5 & 8 \\
7 & 11 \\
13 & 10 \\
8 & 17 \\
4 &
\end{tabular}

Now the lowest score of the wife ties with a score of her husband. We note these observations had ranks 4 and 5 originally so now are jointly ranked 4 , and we can simply assign each rank 4.5:

\begin{tabular}{c|c}
$R_{X}$ & $R_{Y}$ \\
\hline 2 & 4.5 \\
3 & 7 \\
8 & 6 \\
4.5 & 9 \\
1 &
\end{tabular}

We can then proceed as before, although the sampling distribution of $W_{X}$ changes slightly due to the tie. If there are many ties though the test may perform poorly, something to keep in mind when using the procedure.

Remark 3 Here, as in most other nonparametric tests, it is often not possible to construct a test with a specific, exact significance level $\alpha$. This is because the test statistic is a discrete random variable. Remark 4 The rank sum test is often misused. Under the null hypothesis, the distributions underlying the two data sets must be such that $W_{X}$ and $W_{Y}$ have the same distribution when the sample sizes are equal. Two distributions $F_{X}$ and $F_{Y}$ could have the same mean (or median) and yet provide different distributions for $W_{X}$ and $W_{Y}$.

The R command wilcox.test can be used to peform both this test and the signed rank test that follows. Somewhat superior, particular when there are ties in the data, is the function wilcox.exact in the exactRankTests package.