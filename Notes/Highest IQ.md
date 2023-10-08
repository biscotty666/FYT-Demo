---
topic:
  - "[[Normal Distribution]]"
aliases: 
related:
  - "[[R]]"
  - "[[Monte Carlo Simulation]]"
created: 
last edit: 2023-09-07 Thu
type:
  - reference
  - atomic
  - example
status: 100
action: false
---
up:: [[Probability and Statistics]]
tags:: #source/book #note/reference #on/Visualization 
X::  [[Introduction to Data Science]]

## Highest IQ

IQ scores are normally distributed with $\mu = 100$ and $\sigma = 15$. Suppose you want to know the distribution of the highest IQ across all graduating classes if 10,000 people are born each in your school district. In other words, sample groups of 10,000 in a [[Monte Carlo Simulation]].

```
B <- 1000
set.seed(1)

highestIQ <- replicate(B, {
  simulated_data <- rnorm(10000, 100, 15)
  max(simulated_data)
})

hist(highestIQ)
```

![[Pasted image 20230419214311.png]]

---
## References

[13 Probabilities](https://biscotty666.github.io/Data-Science-R-PH125x/docs/Pt13.html#exercises-1)