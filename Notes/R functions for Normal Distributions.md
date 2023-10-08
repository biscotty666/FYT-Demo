---
aliases: 
type:
  - reference
  - example
  - atomic
---
%%
up:: [[R]]
tags:: #note/reference #on/R 
X:: [[Introduction to Data Science]]
topic:: [[R]]
related:: [[Normal Distribution]]
created:: 
last edit:: 2023-09-07 Thu
status:: 100
action:: false
%%
# R functions for Normal Distributions
## Random values
`rnorm(n)` 

- returns random `n` values normally distributed

## Probability density
`dnorm(x, mean = 0, sd = 1)` 

- returns the density of a vector of quantiles `x`

## Probability distribution
`pnorm(p, mean = 0, sd = 1)` 

- returns the distribution function of a vector of quantiles `p`. 
-  uses the symbol $\Phi$ , eg. $\Phi(-1.96) = 0.025$ or $\Phi(1.96) = 0.975$.
- returns the proportion of standard normal distributed data that are small than `p`

**`qnorm()` and `pnorm()` are inverse functions.**
## Quantile function
`qnorm(q, mean = 0, sd = 1)` 

- returns the quantile function 

**`qnorm()` and `pnorm()` are inverse functions.**

---
## References

