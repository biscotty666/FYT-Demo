---
topic:
  - "[[Normal Distribution]]"
aliases: 
related:
  - "[[Data Visualization]]"
  - "[[R]]"
created: 
last edit: 2023-09-07 Thu
type:
  - atomic
  - reference
  - example
status: 100
action: false
---
up::  [[Data Visualization]]
tags:: #source/book #note/reference #on/Visualization #on/R 
X:: [[Random variables]] [[R functions for Normal Distributions]]

## Visualize the probability density of a random variable

We calculated the [[Probability distribution of random variables]]. We can split the result $S$ into several intervals which can be shown as a [[Histograms in R and Python]]. We see that the results approximate a [[Normal Distribution]], which is shown by the line calculated with `dnorm`.

```
s <- seq(min(S), max(S), length = 100)
normal_density <- data.frame(s = s, f = dnorm(s, mean(S), sd(S)))
data.frame(S = S) |>
  ggplot(aes(S, after_stat(density))) +
  geom_histogram(color = "black", binwidth = 10) +
  ylab("Probability") +
  geom_line(data = normal_density, 
            mapping = aes(s, f), 
            color = "blue")
```

![[Pasted image 20230420220607.png]]


---

## References

[[Introduction to Data Science]]



