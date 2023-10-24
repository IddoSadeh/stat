
# Extensions

In standard designs, each level of each factor appears with all levels of the other factors. When there are more than one replication within each treatment, all interaction and main effects can be studied. Ideally experiments are balanced in that there are equal replications under each treatment. We consider next some special designs, concentrating on features of the designs rather than their analyses.

## Nested designs

One way in which a two factor design can appear in different form is via nested factors. In a nested design, the levels of one factor are not identical to the levels of another factors. Such designs are sometimes called hierarchical.

Suppose for example we have two drugs $A_{1}$ and $A_{2}$ one of which is tested in hospitals $B_{1}, B_{2}$ and $B_{3}$, the other in hospitals $B_{4}, B_{5}$ and $B_{6}$, assuming for simplicity there are $K$ replications in each hospital. The data could be displayed as follows.

| Drug $A_{1}$ |  |  |  | Drug $A_{2}$ |  |  |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| $B_{1}$ | $B_{2}$ | $B_{3}$ |  | $B_{4}$ | $B_{5}$ | $B_{6}$ |
| $y_{111}$ | $y_{121}$ | $y_{131}$ |  | $y_{241}$ | $y_{251}$ | $y_{261}$ |
| $\vdots$ | $\vdots$ | $\vdots$ |  | $\vdots$ | $\vdots$ | $\vdots$ |
| $y_{11 K}$ | $y_{12 K}$ | $y_{13 K}$ |  | $y_{24 K}$ | $y_{25 K}$ | $y_{26 K}$ |

This is a two-stage nested design. We could compare the effects of the two drugs and possible differences between hospitals using the same drug, but not differences between hospitals using different drugs. For instance, it would not be possible to compare how hospital $B_{1}$ differs between the two drugs. That is, it is not possible to test for the interaction between drug type and hospital, since each level of the hospital factor does not appear with each level of the drug factor.

The nesting of factors can be either in the design structure or the treatment structure.

## Factorial designs

A special class of experiments worthy of detailed study arise when each of the factors involved in an ANOVA experiment can take only two possible
levels. These levels may conveniently be thought of as "low" and "high", or alternatively "on" and "off". Such experiments are termed factorial designs, and when data are gathered at each possible combination of levels for the factors, the design is said to be full or complete.

There are certain advantages to using factorial designs, particularly in contexts where there are many factors that may affect the response. Such situations are commonplace in industrial processes, where numerous different variables could have an impact on the response (say the quality or quantity of the product). Experimentation that involves changing only one factor at once, using what are sometimes referred to as one-factor-at-a-time designs, is suboptimal for various reasons. We outline the key advantages of factorial experiments:

1. When the number of factors is even moderately high, it is expedient to use factorial designs as a screening process to identify which main effects and interactions appear to be important. That is, should there be several factors each with many possible levels, it is best to perform some preliminary study with each factor restricted to two levels, in order to clarify the important effects. Based on such a study a more refined experiment, discarding apparently unimportant factors, can lead toward optimal factor settings.
2. It can readily be seen that one-factor-at-a-time designs are inefficient, in that they yield less useful information for the same number of runs compared to a factorial design.
3. When interactions are present, one-factor-at-a-time designs will not detect these effects. This can lead to misleading results, where main effects have been masked due to significant interaction being overlooked.

Notation around this topic has little uniformity, with few textbooks concurring on symbology. Here we opt to denote the factors as $A, B, C \ldots$ and denote the corresponding levels by either "+" and "-", or alternatively (1) for the "low" (or "off") level, and the lower case factor letter for the "high" (or "on") setting. So for example factor $A$ has two levels that can be denoted + or -, or (1) and $a$. The logic for this dual notation should become apparent.

When there are $p$ factors, a factorial design is referred to as a $2^{p}$ design. The different treatments possible, sometimes called runs, can be denoted
$a^{i} b^{j} c^{k} \ldots$ where for instance

$$
i=\left\{\begin{array}{lr}
0 & \text { factor } A \text { low } \\
1 & \text { factor } A \text { high. }
\end{array}\right.
$$

So for example in a $2^{4}$ factorial experiment, the treatment $a d$ represents setting factors $A$ and $D$ to high, $B$ and $C$ to low.

In the following we discuss $2^{2}$ designs, some issues about generalizations, and so-called incomplete and fractional factorial designs. This is a subject on which entire books are devoted, so our treatment is necessarily quite scanty. It should be kept in mind however that the main tool for analysis will be ANOVA, so this chapter draws on material from the previous one.

## $2^{2}$ designs

Let us start by clarifying further how superior a factorial design will be compared to a one-factor-at-a-time design. Consider a hypothetical situation where we are investigating an industrial chemical reaction. For the sake of the experiment, suppose two factors were of interest, $A$ (temperature, with two settings) and $B$ (the presence or absence of a catalyst). In order to obtain some information about these two factors, suppose we performed three runs:

![](../Design/2.jpg)

Suppose the symbols in the table represent the amount of yield produced in the corresponding run, so that we could estimate the effect of factor $A$ by

$$
A=a-(1)
$$

and estimate the effect of $B$ via

$$
B=b-(1)
$$

As some experimental error is likely, it would be desirable to replicate each run, so that there would be six trials in total, and averages within treatments used to estimate the effects of $A$ and $B$.

**Remark 8** *Note here we are abusing notation, denoting for instance both the factor $A$ and the estimate of its effect by the symbol $A$. This is commonplace, and we hope not too confusing. It should be kept in mind here that as in all ANOVA studies, the underlying models are over-parameterized, in that it is not possible to estimate how much a factor at a given level changes the mean response. We can only estimate so-called main effects and interactions (more generally functions of parameters known as estimable functions). So for instance although we cannot estimate how much factor A changes the response when $A$ is + , we can estimate the main effect of $A$, this being the mean difference in response between $A$ being + and -.*

Suppose now that the design above is completed as follows:

![](../Design/3.jpg)

This experiment has four runs. Now we can estimate the effect of $A$ when $B$ is low by $a-(1)$, and the effect of $A$ when $B$ is high can be estimated by $a b-b$. If there is no interaction present, these two estimates should differ only by experimental variation, and their average could estimate the main effect for $A$. Similarly for factor $B$, we average $b-(1)$ and $a b-a$. The estimates that would be obtained would be as precise as those from the one-factorat-a-time design with duplication, but whereas the latter used six runs, the factorial design requires only four.

When the factors interact the one-factor-at-a-time design is potentially worthless. For suppose we observed that $a$ and $b$ each gave a better yield than (1). We may conclude that $a b$ would be the superior setting. This would be faulty reasoning if $A$ and $B$ interact. Moreover it may be found that $a$ and $b$ are each little better than (1), but that in fact $a b$ is greatly better than any of the other settings due to interaction, in which case the one-factor-at-a-time design overlooked the optimal setting.

Tabulating the four treatment combinations in a $2^{2}$ design, we have:

|  | $A$ | $B$ |
| ---: | :---: | :---: |
| $(1)$ | - | - |
| $a$ | + | - |
| $b$ | - | + |
| $a b$ | + | + |

## $2^{p}$ designs

In $2^{3}$ designs there are eight possible treatments. It can be useful to visualize the design with the cube illustrated below:

![](../Design/4.jpg)

Tabulation of the treatment combinations for $2^{3}$ designs gives the following:

|  | $A$ | $B$ | $C$ |
| ---: | :---: | :---: | :---: |
| $(1)$ | - | - | - |
| $a$ | + | - | - |
| $b$ | - | + | - |
| $a b$ | + | + | - |
| $c$ | - | - | + |
| $a c$ | + | - | + |
| $b c$ | - | + | + |
| $a b c$ | + | + | + |

**Example** 

An experiment was conducted to assess how descent time (in secs) of a model helicopter depends on wing length, body width and tail length. Let these factors be denoted $A, B$ and $C$ respectively, each having two levels low (-) and high $(+)$. Each treatment had two replications, the data given
below:

|  | time 1 | time 2 | Total |
| ---: | ---: | ---: | ---: |
| $(1)$ | 97 | 84 | 181 |
| $a$ | 87 | 100 | 187 |
| $b$ | 96 | 104 | 200 |
| $a b$ | 104 | 100 | 204 |
| $c$ | 63 | 66 | 129 |
| $a c$ | 75 | 88 | 163 |
| $b c$ | 72 | 72 | 144 |
| $a b c$ | 59 | 81 | 140 |

Here we have a $2^{3}$ design, with 2 replications per treatment.

## Blocking in factorial designs

Sometimes it is impossible to perform all the runs of a $2^{p}$ experiment under exactly the same conditions. Suppose for instance that in a $2^{3}$ study there is only facility to produce enough raw material to conduct four trials at a time. This means that to perform the complete experiment we need to run two sets of four trials, each material created from separate batches. This leads to confounding - some effect(s) must be impossible to extricate from the block structure.

## Two blocks

In the case where two blocks are used, one effect will be confounded and this is usually chosen to be the highest order interaction. Whatever the confounded effect, it determines which treatments are applied in each block. We illustrate with examples for $2^{p}, p=1,2,3$.

**Example** 

In the $2^{2}$ case, there are only four possible treatments to split into two blocks of two. The table of treatments is

|  | $A$ | $B$ |
| ---: | :---: | :---: |
| $(1)$ | - | - |
| $a$ | + | - |
| $b$ | - | + |
| $a b$ | + | + |

and the blocks comprise

| Block 1 | Block 2 |
| :---: | :---: |
| $(1)$ | $a$ |
| $a b$ | $b$ |

Each block contains one observations with $A$ at + , and one with $B$ at + . In that way neither of the main effects are confounded by the block structure.

Example 10 A $2^{3}$ design can be defined by the main effects as below:

|  | $A$ | $B$ | $C$ |
| ---: | :---: | :---: | :---: |
| $(1)$ | - | - | - |
| $a$ | + | - | - |
| $b$ | - | + | - |
| $a b$ | + | + | - |
| $c$ | - | - | + |
| $a c$ | + | - | + |
| $b c$ | - | + | + |
| $a b c$ | + | + | + |

If using two blocks and wishing to avoid confounding main effects, the blocks are as follows:

| Block 1 | Block 2 |
| :---: | ---: |
| $(1)$ | $a$ |
| $a b$ | $b$ |
| $a c$ | $c$ |
| $b c$ | $a b c$ |

Each factor appears in each block twice at each of its two levels. In this design the three-way interaction effect is confounded by blocking.

Four blocks Obviously a $2^{p}$ design can only be split into an even number of blocks, so a design with three blocks is not possible unless some treatments were discarded or repeated. Hence the extension to using two blocks is the use of four blocks. Now there will be three effects confounded by the blocks.

**Example** 

Consider a $2^{4}$ design:

|  | $A$ | $B$ | $C$ | $D$ |
| ---: | :---: | :---: | :---: | :---: |
| $(1)$ | - | - | - | - |
| $a$ | + | - | - | - |
| $b$ | - | + | - | - |
| $a b$ | + | + | - | - |
| $c$ | - | - | + | - |
| $a c$ | + | - | + | - |
| $b c$ | - | + | + | - |
| $a b c$ | + | + | + | - |
| $d$ | - | - | - | + |
| $a d$ | + | - | - | + |
| $b d$ | - | + | - | + |
| $a b d$ | + | + | - | + |
| $c d$ | - | - | + | + |
| $a c d$ | + | - | + | + |
| $b c d$ | - | + | + | + |
| $a b c d$ | + | + | + | + |

If we require four blocks, the blocking could be chosen as follows:

| Block 1 | Block 2 | Block 3 | Block 4 |
| :---: | :---: | :---: | :---: |
| $(1)$ | $b$ | $a$ | $a b$ |
| $a c$ | $a b c$ | $c$ | $b c$ |
| $b d$ | $d$ | $a b d$ | $a d$ |
| $a b c d$ | $a c d$ | $b c d$ | $c d$ |

Each block contains each factor twice at each of its two levels. The highest order interaction is confounded here, along with two two-way interactions (in fact between $A$ and $C$ and also between $B$ and $D$ ).

Some advanced texts include tables for block designs, prescribing how to create blocking so that only high-order interactions are confounded.

## Fractional factorial designs

In practice, once $p$ becomes large the number of treatments required to perform a full factorial design is prohibitive. For instance, a $2^{6}$ design requires

64 treatments, but many of these exist only to assess high-order interactions, some of which may be known to be negligible from past experience or other considerations. Hence the experimenter may choose to apply only half (or a quarter, or an eighth) of the possible treatments.

In half fractional factorial designs only half of the possible treatments are applied. This is akin to selecting two blocks but discarding one of them. In general then a half fractional design for a $2^{p}$ design involves $2^{p-1}$ treatments.

We illustrate by consideration of a $2^{3-1}$ design. Suppose the blocking is

| Block 1 | Block 2 |
| :---: | ---: |
| $(1)$ | $a$ |
| $a b$ | $b$ |
| $a c$ | $c$ |
| $b c$ | $a b c$ |

but only one of the two blocks will be chosen. Suppose block 2 is chosen. The design can be pictured as follows:

![](../Design/5.jpg)

More generally, we may opt to use only $1 / 2^{k}$ of the possible treatments. When $k=2$, this corresponds to quarter fractional factorial designs, for instance. In general, fractional factorial designs are denoted $2^{p-k}$ designs.
