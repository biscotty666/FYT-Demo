---
aliases: 
type:
  - reference
  - example
  - atomic
---
up:: [[Probability and Statistics]]
tags:: #source/book #note/reference #on/R #on/Visualization 
X:: [[Introduction to Data Science]]
topic:: [[R]]
related:: [[Data Visualization]], [[Normal Distribution]]
created:: 
last edit:: 2023-09-07 Thu
status:: 100
action:: false

## Quantile-quantile plots

Used to assess how well the normal distribution fits the data. ^00c2cf

### Quick generation of a QQ-plot with [[R]]

```
heights |>
  filter(sex == "Male") |>
  ggplot(aes(sample = scale(height))) +
  geom_qq() +
  geom_abline()
```

### Detailed explanation

##### 1. Define a vector of proportions. This vector specifies the quantiles of interest.

 Example:
 
```
p <- seq(0.05, 0.95, 0.05)
```

##### 2. Create the vector of quantiles for the actual data

```
sample_quantiles <- quantile(x, p)
```


##### 3. Create a vector of theoretical quantiles for a normal distribution with the same mean and SD of the actual data

```
theoretical_quantiles <- qnorm(p, mean(x), sd(x))
```

##### 4. Plot the samples vs theoretical with the identity line

```
qplot(theoretical_quantiles, sample_quantiles) +
  geom_abline()
```

### Alternative approach to steps 2 and 3


```
z <- scale(x)
sample_quantiles <- quantile(z, p)
theoretical_quantiles <- qnorm(p)
```

