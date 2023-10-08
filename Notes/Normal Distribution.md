---
aliases: 
type:
  - reference
  - atomic
---
%%
up::  [[Probability and Statistics]]
tags:: #source/book #note/reference #on/Probability 
X:: [[Central Limit Theorem]] [[The 68-95-99.7 Rule]] [[Introduction to Data Science]] [[R functions for Normal Distributions]]
topic:: [[Probability]]
related:: 
created:: 2023-07-30
last edit:: 2023-09-07 Thu
status:: 100
action:: false
%%
# Normal Distribution

AKA Gaussian distribution. It is symmetric and defined by a mean, $\mu$ and a [[Standard Deviation]], $\sigma$. About 95% of values lie within 2 SDs from the average.

$$
f(x)=\frac{1}{\sigma\sqrt{{2\pi}}}e^{-\frac{1}{2}(\frac{\sigma-\mu}{\sigma})^2}
$$
The distribution variance is $\sigma^2$ .

The proportion of values in an interval can be calculated:

$$\mbox{Pr}(a < x \leq b) = \int_a^b \frac{1}{\sqrt{2\pi}s} e^{-\frac{1}{2}\left( \frac{x-m}{s} \right)^2} \, dx$$
In [[R]] the `dnorm()` function gives the density.

Using [[Z-score or Standard Units]], $z=\frac{(x-m)}{s}$ :

$$\mbox{Pr}(a < x \leq b) = \int_a^b \frac{1}{\sqrt{2\pi}s} e^{-\frac{1}{2}z^2} \, dx$$

---
# Reference

[12 Summary Statistics](https://biscotty666.github.io/Data-Science-R-PH125x/docs/Pt12.html#the-normal-distribution)

[Normal distribution - Wikipedia](https://en.wikipedia.org/wiki/Normal_distribution)