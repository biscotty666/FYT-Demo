---
fileClass: Default
aliases: 
type:
  - reference
---
up:: [[Probability and Statistics]]
tags:: #on/Probability  #source/video #note/reference 
topic:: [[Probability]]
related:: 
created:: 2023-07-30
last edit:: 2023-09-07 Thu
status:: 100
action:: false

# Binomial Distribution

## Description

The Binomial Distribution is a discrete version of a [[Normal Distribution]].

Applicable when outcomes are one of two categories, eg. true/false, survived/died, success/fail.

A binomial distribution is very useful and widely used since it can be used no matter how many categories exist if used in the form A or not A.

## Details

Required traits of a binomial distribution:
1. Procedure must have a fixed number of trials
2. Trials must be independent (see below)
3. Each trial must have outcomes classified into two categories
4. The probability of success remains constant across all trials

For categories $S$ and $F$ let $p=P(S)$ and $q=P(F)=1-p$.
- $n$ = fixed number of trials
- x = specific number of successes in $n$ trials, so any integer in [0,n].
- $p$ = probability of success in _one_ of the $n$ trials
- $q$ = probability of failure in _one_ of the $n$ trials
- $P(x)$ = probability of getting $x$ successes in $n$ trials

Note that _when sampling without replacement events can be considered independent if $n\lt0.05N$, or less than 5% of the population_.

## Equations

for $x=0, 1, \dots, n$:
$$
P(x)=\frac{n!}{(n-x)!x!}\cdot p^x\cdot q^{n-x}
$$

For the binomial distribution

$$
\begin{align}
\text{Mean} &: \mu = n\cdot p \\
\text{Variance} &: \sigma^2=n\cdot p\cdot q \\
\text{Std Dev} &: \sigma=\sqrt{n\cdot p\cdot q}
\end{align}
$$
The range rule of thumb suggests that values are unusual if the are outside $\mu\pm 2\sigma$ .

[[Expected Value of Binomial Distribution]]

### [[Coin Flip Example|Examples]]

[[Coin Flip Example]]
[[Life Insurance Example]]
[[McDonalds Example]]
[[Twitter Example]]


---

### Probability mass function

![[Pasted image 20230504223556.png]]


### Cumulative distribution function

![[Pasted image 20230504223718.png]]





---

### References

[Statistics - Binomial & Poisson Distributions - YouTube](https://www.youtube.com/watch?v=BR1nN8DW2Vg)
[Statistics Fundamentals - YouTube](https://www.youtube.com/playlist?list=PLblh5JKOoLUK0FLuzwntyYI10UQFUhsY9)