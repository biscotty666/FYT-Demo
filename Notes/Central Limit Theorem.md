---
type:
  - reference
  - example
  - atomic
---
up:: [[Probability and Statistics]]
tags:: #source/book #note/reference #on/Statistics
topic:: [[Normal Distribution]]
related:: 
created:: 2023-07-30
last edit:: 2023-09-07 Thu
status:: 100
action:: false

# Central Limit Theorem

## Description
As sample size increases the sample mean $\bar{x}$ approaches the population mean $\mu$ . 

In many real-life situations, random independent samples taken from common data, eg heights or draws from an urn, tend to match the [[Normal Distribution]].

If a [[Random variables]] has a has a probability distribution which approximates the Normal distribution, the probability distribution can be fully described by the average (expected value) and standard deviation (standard error).

Note that the number of samples is not the key to the applicability of CLT. However you must be sure that the data in fact approximates the Normal distribution. If not, another distribution can be used.
## Code example (R)
[[Sampling models - Casino roulette winnings]] used a [[Monte Carlo Simulation]] to calculate average and sd. 

Based on the Central Limit Theorem, you can instead use the approximation: ^1b9582

```
mu <- n * (20-18) / 38
se <- sqrt(n) * 2 * sqrt(90)/19
pnorm(0, mu, se)

## [1] 0.0478

mean(S < 0)

## [1] 0.0459
```



---
## Reference

[[Introduction to Data Science]]

[14 Random variables](https://biscotty666.github.io/Data-Science-R-PH125x/docs/Pt14.html#central-limit-theorem)

[en.wikipedia.org/wiki/Central_limit_theorem](https://en.wikipedia.org/wiki/Central_limit_theorem)
