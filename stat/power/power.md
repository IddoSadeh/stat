# Power of Hypothesis test

Their are two types of error when assesing evidence in favour of a null hypothesis:
1. Type 1 error: P(reject $H_0 \mid H_0$ is true) = $\alpha$.

2. Type 2 error:  P(don't reject $H_0 \mid H_0$ is false) = $\beta$.


## The power function

Let the **power** of a test be $1-\beta$.

The **power function** is for a single parameter $\theta$ as:

$$\pi(\theta)=P(\text{reject } H_0)$$

Ideally:

$$
\pi(\theta)= \begin{cases}0 & \text { if } \theta \in H_{0} \\ 1 & \text { if } \theta \in H_{1},\end{cases}
$$