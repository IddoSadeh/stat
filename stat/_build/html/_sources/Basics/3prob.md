# Probability
Qunatifiyng uncertainity is done by measuring probability. 

- Events will be noted will a captial letter. 
Say we define and event as $A$, then the probability will be denoted as $P(A)$.

- Probability is measured between $0$ and $1$ inclusive.

- If there are $n$ equally likely possibile outcomes for an event $A$, and $A$ occurs $r$ times than the probability is $P(A) = \frac{r}{n}$.

## Combinations

- If there are $m$ ways in which $A$ can be chosen, and $n$ ways in which $B$ can be chosen, there are $mn$ ways in which $A$ and $B$ can be chosen together.

- The number of ways that $n$ distinct objects can be arranged in order is $n!$. We say there are $n!$ permutations of $n$ distinct objects.

- Suppose we wish to select $r$ objects from $n$ objects, where $r < n$, and want to arrange them in order. In how many ways can this be done? Well,there are $n$ choices for the first object. Then there are $(n − 1)$ choices for the second one, $(n − 2)$ for the third one, .... , $(n − r + 1)$ for the final one (as there are $n − r$ left unchosen). So there are $n × (n − 1) × (n − 2) × · · · × (n − r + 1)$
possible choices. By taking note of what cancels out in the fraction in the first equation below, we see that
$ n × (n − 1) × (n − 2) × · · · × (n − r + 1) = \frac{n × (n − 1) × · · · × 2 × 1}
{(n − r) × (n − r − 1) × · · · × 1} =\frac{n!}{(n − r)!}$. 
Sometimes this is denoted as $^nP_r$.


    For example: How many three letter words can be made from the first eight letters of the alphabet:
     $^nP_r = \frac{8!}{5!}=336$

- When the order does not matter, we use $n choose r$ denoted as $^nC_r$. Formally, The number of ways r objects can be chosen from n objects is:
    
    $^nC_r = {n \choose r} = \frac{n!}{(n-r)!}$

## Probability
- Union: 

    Let $A \cup B$ denote the event that at least one of $A$ or $B$ occurs.

- Intersection: 

    Let $A \cap B$ denote the event that both of $A$ and $B$ occur.

- Empty Set:

    Denoted $\phi$.

- Disjoint Sets:

    $A \cap B = \phi$.

- Mutally exclusive: 

    $P(A\cap B) = 0$.

- Complement:

    $A^c$ is defined as when $A$ does not occur.

- General rule for probability:

    $P(A\cup B) = P(A)+P(B)+P(A\cap B)$

- Independance:

    Two events are said to be independent if:
    
    $P(A\cap B) = P(A)P(B)$

    Three events A, B, and C are said to be independent if, any two events are independent and
     
    $P(A\cap B \cap C) = P(A)P(B)P(C)$

- Conditional Probability

    Probability of A happening given B happens and $P(B) > 0$:

    $P(A|B) = \frac{P(A\cap B)}{P(B)}$

- Bayes Theorem:

     Let $E_1, . . . , E_n$ be a collection of mutually exclusive and exhaustive events. Let A be any event in the sample space. Then

     $P(E_k|A) = \frac{P(A\cap E_k)P(E_K)}{\sum_{i=1}^nP(A|E_I)P(E_i)}$

     Example: 
     Suppose 60\% of a company's computer chips are made by one factory (A say), with the remainder made by another, B. For a chip from $A$ there is a $35 \%$ chance of it being defective, whilst the corresponding rate for $B$ is 25\%. A chip is chosen at random and is found to be defective. What is the probability that it came from factory A? From the information given,

    $$
    \begin{array}{ll}
    P(\text { defective } \mid A)=0.35, & P(A)=0.6 \\
    P(\text { defective } \mid B)=0.25, & P(B)=0.4 .
    \end{array}
    $$

    Hence by Bayes' theorem,

    $$
    \begin{aligned}
    P(A \mid \text { defective }) & =\frac{P(\text { defective } \mid A) P(A)}{P(\text { defective } \mid A) P(A)+P(\text { defective } \mid B) P(B)} \\
    & =\frac{0.35 \times 0.6}{0.35 \times 0.6+0.25 \times 0.4} \\
    & =0.67 .
    \end{aligned}
    $$

    Note that Bayes' theorem allows us to "turn around" conditional probability statements, from statements about $\{A$ given $B\}$ to the probability of $\{B$ given $A\}$. In the above example, for instance, information concerning the probability of being defective given the factory, $P$ (defective $\mid A$ ), is translated into a statement about the probability of the factory given the defect, $P(A \mid$ defective $)$.
