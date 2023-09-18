# Linear Relationships

Two variables $X$ and $Y$ obey a linear relationship if $Y=\alpha +\beta X$.

## Correlation

### sample covariance
The sample covariance between two variables $X$ and $Y$ is:
    $$cov(X,Y)= \frac{1}{n}\sum_{i=1}^n (x_i-\bar{x})(y_i-\bar{y})$$

When $cov(X,Y)>0$ a fitted line on the plot may have an upward trend. 

When $cov(X,Y)<0$ a fitted line on the plot may have a downward trend. 

When $cov(X,Y) \approx 0$ a linear relationship may not exist.

### sample correlation
The sample correlation between $X$ and $Y$, based on a sample $\left(x_{1}, y_{1}\right), \ldots,\left(x_{n}, y_{n}\right)$, is denoted $r_{X, Y}$where

$$
r_{X, Y}:=\frac{\operatorname{cov}(X, Y)}{\sqrt{s_{X}^{2} s_{Y}^{2}}}
$$

in which $s_{X}^{2}$ and $s_{Y}^{2}$ are the sample variances of the $X$ and $Y$ values respectively. That is,

$$
\begin{aligned}
& s_{X}^{2}=\frac{1}{n} \sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2} \\
& s_{Y}^{2}=\frac{1}{n} \sum_{i=1}^{n}\left(y_{i}-\bar{y}\right)^{2} .
\end{aligned}
$$

There follows some useful facts about the sample correlation, sometimes referred to as Pearson's correlation, or the (sample) correlation coefficient.

1. The sample correlation is dimensionless. That is to say, $r_{X, Y}$ is independent of the units in which $X$ and $Y$ are measured.

2. $r_{X, Y}$ is free of units, it must lie between -1 and +1 (inclusive). Writing this in symbols,

$$
-1 \leq r_{X, Y} \leq+1 .
$$

3. If $r_{X, Y}=+1$, its maximum possible value, we say there is perfect positive correlation between $X$ and $Y$. 

4. If $r_{X, Y}=0$, we say that $X$ and $Y$ are uncorrelated. This means that there is no evidence whatsoever of a linear relationship between $X$ and $Y$.

5. If $r_{X, Y}=-1$, points in the scatter plot lie exactly on a line of negative slope. We say that $X$ and $Y$ appear to have perfect negative correlation.

6. There are two special cases where the correlation cannot be calculated: if the points on the scatter plot lie exactly on either a vertical or horizontal line, then $r_{X, Y}$ is not defined.

7. If $r_{X, Y}=+1$ the line must have positive slope, so $\beta>0$, and if $r_{X, Y}=-1$ the line must have negative slope, so $\beta<0$.

8.  Correlation does not imply causation. That is to say, the presence of a high (i.e., close to +1 ) or low (i.e., close to -1 ) value of the sample correlation does not imply that there is necessarily a "cause and effect" at work between the two variables.

9. The correlation $r_{X, Y}$ only measures the strength of the linear relationship between the two variables. Any non-linear trend is not detected, however strong it might be.

10. Even if $r_{X, Y}= \pm 1$, the value only indicates what the sign of the slope of the underlying line is. It says nothing about the magnitude of the slope.

11. If there is a trend present, the sign of the correlation tells us the direction of that trend. That is, to all intents and purposes, the extent of the information one can extract from a correlation.


## Linear Models
A linear model exhibits a relationship of the form:
$$Y=\alpha + \beta X + \epsilon$$

Where $\epsilon$ is an error term.

The slope $\beta$ is calculated as follows:

$$\beta = \frac{cov(X,Y)}{s_{X}^2}$$

The intercept is calculated as follws:

$$\alpha = \bar{y}- \beta \bar{x}$$

In this approach we minimzed the zum of the squares of the errors. This approach is termed the least squares estimate.

## Non-linear models

Often we will encounter non linear models. For example models of the form:
$$Y=\alpha + \beta X^2 + \epsilon$$
or
$$Y = \alpha  e^{\beta X}$$

In both cases, we can transform the model to look linear and solve for $\alpha$ and $\beta$.

For instance, in example 1, we can set $X^2=Z$ and solve the relationship $Y=\alpha + \beta Z + \epsilon$.

In example 2, we can use logarithmic rules to turn the relationship linear. The relationship would look like: $\log_{e}(Y) =\log_{e}(\alpha) +\beta X $. 
