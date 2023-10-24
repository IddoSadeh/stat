
### ANOVA in R

In $\mathrm{R}$, the key command is:

    aov(formula, data = NULL,... )

The formula will involve the response variable and the factors, with purely additive models linking the factors via "+", and interaction models using "*". So a model response y with three factors, $f 1, \mathrm{f} 2$ and $f 3$ say, and interaction between $f 1$ and $f 2$, could be expressed

    model1<- aov y ~ f1*f2+f3, data = ... )

The "full" model in the above example would be encoded $f 1 * f 2 * f 3$, incidentally.

The data data-frame contains the response and factors, but if not specified $\mathrm{R}$ Commander will search within the active data set. The aov command creates an object of aov type, and various other commands can be applied to aov objects. Notably Anova produces the ANOVA table, and the summary command can also be used.

**Example** 

The npk data set in the MASS package includes data from a so-called $N, P, K$ (nitrogen, phosphate, potassium) experiment on the growth of peas conducted in six blocks. The response variable is the yield of peas per plot, the plots being a 70th of an acre each. The experiment was not balanced, so in fact is of a "fractional factorial" type introduced in the next chapter. However, certain models for these data can be fitted and analyzed. For instance, load the MASS package and enter

    aov1 <- aov (yield ~block +N*P+K, data=npk)

    Anova(aov1)

This produces the following ANOVA table:

| Source | $S S$ | $D f$ | $F$ | $P(>F)$ |
| :---: | :---: | :---: | :---: | :---: |
| Block | 343.29 | 5 | 4.3911 | 0.01295 |
| $N$ | 189.28 | 1 | 12.1055 | 0.00368 |
| $P$ | 8.40 | 1 | 0.5373 | 0.47564 |
| $K$ | 95.20 | 1 | 6.0886 | 0.02711 |
| $N: P$ | 21.28 | 1 | 6.0886 | 0.26284 |
| Residual | 218.90 | 14 |  |  |

