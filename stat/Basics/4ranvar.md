# Random Variables and Probability Distributions

A random variable is a variable whose possible outcomes are outcomes of a random phenomenon. It is a function that maps a sample space to real numbers. For example:

- Toin coss

    The sample space for a coing toss is $S=\{H,T\}$ so we can define a random variable $X$ as: $$X= \begin{cases}1 & \text { if } H \\ 0 & \text { if } T .\end{cases}$$
    In this case $P(X=1)=P(H)$.

    If we toss two coins than the sample space is $S=\{\{H,H\} ,\{H,T\} , \{T,H\} , \{T,T\}\}$. If we define the random vairable as the number of heads recorded we get: $$ \begin{aligned}& P(X=0)=\frac{1}{4} \\& P(X=1)=\frac{1}{2} \\& P(X=2)=\frac{1}{4} .\end{aligned}$$

## Probability Mass Function (pmf)

When the random variable can take on only discrete (countable) values, the distribution of the random variable is described by a probability mass function denoted $p(x)$. That is:
$$p(x)=P(X=x)$$

For any mass function, $\sum_x p(x) = 1$

## The Binomial Distribution

- Sequence of independent trials with two possible outcomes.
- The two even are complementary events.

$P(k \text{ success in } n \text{ trails}) = {n \choose k}p^kq^{n-k}$ 
where $p$ is the probability of the event occuring (success) and $k$ is th probability of the event not occuring (failure).

The above equation defines the Binomial distribution with n trials and the probability of a single successs being p. This is denoted $B(n,p)$ for short.

Often the symbol $\sim$ is used for shorthand: is distibuted as, hence $X \sim B(n,p)$ is read as "X is a random variable distributed as a binomial distribution with n trials and the probability of success p."

Example Questions:

**Exercise 1** The probability of a missile hitting a warship on a single shot is
0.6, and three hits are required to put the warship out of action. If a salvo
of six missiles are fired at the warship, what is the probability of putting the
ship out of action?

**Exercise 2** A batch of galvanised washers are guaranteed to be 2% defective,
at most. Assuming this assertion is correct, in a sample of ten what is the
probability of observing at least two defectives?

**Exercise 3** You are told that nine out of ten doctors will prescribe a drug.
Assuming this is true, if you choose four doctors at random, what is the
probability that no more than two of these will prescribe the drug?


To solve these problems, we can use the binomial probability formula, which is:

$
P(X = k) = \binom{n}{k} \times p^k \times (1-p)^{(n-k)}
$

Where $P(X = k)$ is the probability of $k$ successes in $n$ trials, $p$ is the probability of success on a single trial, and $\binom{n}{k}$ is the binomial coefficient, often read as "n choose k."

**Exercise 1 Solution**

In this case, $n = 6$ (the number of missiles), $p = 0.6$ (the probability of a hit), and we want to find the probability of getting at least 3 hits.

$
P(X \geq 3) = 1 - [P(X=0) + P(X=1) + P(X=2)]
$

Calculating each term:

- $P(X=0) = \binom{6}{0} \times 0.6^0 \times 0.4^6 = 1 \times 1 \times 0.004096 = 0.004096$
- $P(X=1) = \binom{6}{1} \times 0.6^1 \times 0.4^5 = 6 \times 0.6 \times 0.01024 = 0.036864$
- $P(X=2) = \binom{6}{2} \times 0.6^2 \times 0.4^4 = 15 \times 0.36 \times 0.0256 = 0.13824$

Adding these up: $0.004096 + 0.036864 + 0.13824 = 0.1792$

Finally, $P(X \geq 3) = 1 - 0.1792 = 0.8208$

**Exercise 2 Solution**

Here, $n = 10$, $p = 0.02$, and we want to find $P(X \geq 2)$.

$
P(X \geq 2) = 1 - [P(X=0) + P(X=1)]
$

- $P(X=0) = \binom{10}{0} \times 0.02^0 \times 0.98^{10} = 1 \times 1 \times 0.817072 = 0.817072$
- $P(X=1) = \binom{10}{1} \times 0.02^1 \times 0.98^9 = 10 \times 0.02 \times 0.8342 = 0.167$

Adding these up: $0.817072 + 0.167 = 0.984072$

Finally, $P(X \geq 2) = 1 - 0.984072 = 0.015928$

**Exercise 3 Solution**

Here, $n = 4$, $p = 0.9$, and we want to find $P(X \leq 2)$.

$
P(X \leq 2) = P(X=0) + P(X=1) + P(X=2)
$

- $P(X=0) = \binom{4}{0} \times 0.9^0 \times 0.1^4 = 1 \times 1 \times 0.0001 = 0.0001$
- $P(X=1) = \binom{4}{1} \times 0.9^1 \times 0.1^3 = 4 \times 0.9 \times 0.001 = 0.0036$
- $P(X=2) = \binom{4}{2} \times 0.9^2 \times 0.1^2 = 6 \times 0.81 \times 0.01 = 0.0486$

Adding these up: $0.0001 + 0.0036 + 0.0486 = 0.0523$

So, $P(X \leq 2) = 0.0523$


## The Poisson Distribution
This distribution is used for events that are discrete and occur over time.

We denote the mean number events over some duration $T$ as $\lambda$. The Poisson distribution with mean $\lambda$ is denoted $P_o(\lambda)$. If $X \sim P_o(\lambda)$ then $P(X=x) = \frac{\lambda^xe^{-x}}{x!}$ gives the probability of $x$ occurences of the vent over a time interval of length $T$

**Example**
A waiter drops on average 2.4 dishes per hour. During an hour, what is the chance that he breaks (a) at most four dishes and (b) exactly four dishes, assuming a Poisson distribution for the breakages?

**Solution**



In this case, $ \lambda = 2.4 $ dishes per hour.

- (a) At most four dishes

    To find the probability that the waiter breaks at most four dishes, we sum the probabilities of breaking 0, 1, 2, 3, or 4 dishes:

    $
    P(X \leq 4) = P(X=0) + P(X=1) + P(X=2) + P(X=3) + P(X=4)
    $

    Calculating each term:

    - $ P(X=0) = \frac{2.4^0 \times e^{-2.4}}{0!} = \frac{1 \times e^{-2.4}}{1} \approx 0.0902 $
    - $ P(X=1) = \frac{2.4^1 \times e^{-2.4}}{1!} = 2.4 \times e^{-2.4} \approx 0.2165 $
    - $ P(X=2) = \frac{2.4^2 \times e^{-2.4}}{2!} = 1.2 \times e^{-2.4} \approx 0.2598 $
    - $ P(X=3) = \frac{2.4^3 \times e^{-2.4}}{3!} = 0.4 \times e^{-2.4} \approx 0.1039 $
    - $ P(X=4) = \frac{2.4^4 \times e^{-2.4}}{4!} = 0.1 \times e^{-2.4} \approx 0.0250 $

    Adding these up: $ 0.0902 + 0.2165 + 0.2598 + 0.1039 + 0.0250 \approx 0.6954 $

- (b) Exactly four dishes

    The probability of breaking exactly four dishes is $ P(X=4) $, which we already calculated as approximately $ 0.0250 $.


## Tables

Often the calculations are long and hard. Tables with precalculate values exist.

### The cummalitive distibution function (cdf)

The cdf gives the probability of being less than or rqual to a given value:

$$F(x) = P(X\leq x) = \sum_{k=0}^xp(k)$$

This can be useful when looking for $p(x)$:
$$p(x)= P(X=x) = P(X \leq x) -P(X\leq x-1) = F(x)-F(x-1)$$

In short, say you are looking $p(x)$, you can find $F(x)$ and $F(x-1)$ in a table, and $p(x) =F(x)-F(x-1)$.

## The Poission approximation to the Binomial

If $X \sim B(n,p) $, then provided that $n$ is reasonably large ($>30$) and $p$ is comparativley small, so that thair product $np$ is "moderate" in size ($\leq 7$) than approximately $X \sim P_o(np)$

## The Normal Distribution

This distribution works for continous distibution. It depends on two paramters: mean ($\mu$) and variance ($\sigma^2$). The distibution is denoted $N(\mu,\sigma^2)$.

For normal distibution, a pmf is not appropraite, and we use a probability density function (pdf). The curve formed for this density function is "bell-shaped". A normal distibutiuon centerd and symmetric about zero is denoted $N(0,1)$ and looks as following:

![Alt text](stat\Basics\image-1.png)

The area under two points on the curve is probabilit of the event occuring between those two points, hence the area under the whole curve is 1.

Tables exist for finding these probabilties, and the number in the table would be the are under the curve to the left of the value.

If we are not dealing with a standard normal distibution ($N(0,1)$) we can standardize it by defining $Z = \frac{X-\mu}{\sigma}$ and $Z$ will follow a standardised normal distribution ($Z \sim N(0,1)$). Doing this allows for using the table for $Z$.

For example:

Say we are given a distribtuion $N(400,50^2)$. We define $Z = \frac{X-400}{50}$. If we were to examine when $X<360$, we will examine when $Z<-0.8$. Now we can check a table to see what the are under a Normal probability density function is to the left of $-0.8$.

### The Standard Deviation

As a general rule of thumb, in normal distibutions, about 68% of the area under the density curve is within one standard deviation of the mean, 95% within two standard deviations, and 99% within three standard deviations.

### Sums of Normals

If

$$X \sim N(\mu_X,\sigma_X^2)$$
$$Y \sim N(\mu_Y,\sigma_Y^2)$$

are two independant Normal variabls then:

$$X+Y \sim N(\mu_X+\mu_Y,\sigma_X^2+\sigma_Y^2)$$
