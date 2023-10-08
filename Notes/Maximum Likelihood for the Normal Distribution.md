---
topic:
  - "[[Normal Distribution]]"
aliases: 
created: 
last edit: 2023-09-07 Thu
type:
  - reference
  - atomic
status: 100
action: false
---
up:: [[Probability and Statistics]]
tags:: #on/Probability  #source/video #source/StatQuest #note/reference 
related:: 


## Maximum Likelihood for the Normal Distribution

$$
\mbox{Pr}(x\,|\,\mu,\sigma) = \frac{1} {\sigma\sqrt{2\pi}} e^{-(x - \mu)^{2}/(2\sigma^{2}) }
$$

## Math
### The goal is to find the optimal values for $\mu$ and $\sigma$ given some data $x$.

Given $\sigma$, the _maximum likelihood estimate_ for $\mu$ can be determined by differentiating the probability function with respect to $\mu$ and setting to 0.

Similarly, fixing $\mu$ and differentiating the probability with respect to $\sigma$ and setting to 0 will determine the optimal $\sigma$.

### Take the log of the Likelihood function

$$
\begin{align}
ln [\mbox{L}(\mu,\sigma |\,x_1,\dots,x_n)] &= ln \bigg(\frac{1} {\sigma\sqrt{2\pi}} e^{-(x_1 - \mu)^{2}/2\sigma^{2} } \times \dots \times \frac{1} {\sigma\sqrt{2\pi}} e^{-(x_n - \mu)^{2}/2\sigma^{2} }\bigg) \\
&= ln \bigg(\frac{1} {\sigma\sqrt{2\pi}} e^{-(x_1 - \mu)^{2}/2\sigma^{2} }\bigg) + \dots + ln\bigg(\frac{1} {\sigma\sqrt{2\pi}} e^{-(x_n - \mu)^{2}/2\sigma^{2} }\bigg) \\
\end{align}
$$

For the first expression:
$$
\begin{align}
ln \bigg(\frac{1} {\sigma\sqrt{2\pi}} e^{-(x_1 - \mu)^{2}/2\sigma^{2} }\bigg) &= ln \bigg(\frac{1} {\sigma\sqrt{2\pi}}\bigg) + ln( e^{-(x_1 - \mu)^{2}/2\sigma^{2} }) \\
&=ln[(2\pi\sigma^2)^{-1/2}] -\frac{(x_1-\mu)^2}{2\sigma^2}ln(e) \\
&=-\frac{1}{2}ln(2\pi\sigma^2) - \frac{(x_1-\mu)^2}{2\sigma^2} \\
&=-\frac{1}{2}ln(2\pi)-\frac{1}{2}ln(\sigma^2 ) - \frac{(x_1-\mu)^2}{2\sigma^2} \\
&=-\frac{1}{2}ln(2\pi)-ln(\sigma) - \frac{(x_1-\mu)^2}{2\sigma^2}
\end{align}
$$

Therefore:

$$
\begin{align}
ln [\mbox{L}(\mu,\sigma |\,x_1,\dots,x_n)] &= -\frac{1}{2}ln(2\pi)-ln(\sigma) - \frac{(x_1-\mu)^2}{2\sigma^2}-\dots-\frac{1}{2}ln(2\pi)-ln(\sigma) - \frac{(x_n-\mu)^2}{2\sigma^2}  \\
&=-\frac{n}{2}ln(2\pi) - n\,ln(\sigma) - \frac{(x_1-\mu)^2}{2\sigma^2}-\dots- \frac{(x_n-\mu)^2}{2\sigma^2}  \\
\end{align}
$$

### Take the partial derivative with respect to $\mu$:

$$
\begin{align}
\frac{\partial}{\partial \mu}ln [\mbox{L}(\mu,\sigma |\,x_1,\dots,x_n)] &= 0 -  0 + \frac{(x_1-\mu)}{\sigma^2} + \dots + \frac{(x_n-\mu)}{\sigma^2} \\
&=\frac{1}{\sigma^2}[(x_1-\mu)+\dots+(x_n-\mu)] \\
&=\frac{1}{\sigma^2}[(x_1+\dots+x_n)-n\mu)]
\end{align}
$$

### Set to 0 and solve for $\mu$:

$$
\begin{align}
0&=\frac{1}{\sigma^2}[(x_1+\dots+x_n)-n\mu)] \\
&=(x_1+\dots +x_n)-n\mu \\
n\mu &= (x_1+\dots +x_n) \\
\mu&=\frac{(x_1+\dots +x_n)}{n}
\end{align}
$$

__The maximum likelihood estimate for $\mu$ is the mean of the measurements.__

### The partial derivative with respect to $\sigma$:

$$
\begin{align}
\frac{\partial}{\partial \sigma}ln [\mbox{L}(\mu,\sigma |\,x_1,\dots,x_n)] &= 0 -  \frac{n}{\sigma} +\frac{(x_1-\mu)^2}{\sigma^3}+\dots+\frac{(x_n-\mu)^2}{\sigma^3} \\
&=-\frac{n}{\sigma}+\frac{1}{\sigma^3}[(x_1-\mu)^2+\dots+(x_n-\mu)^2]
\end{align}
$$

### Set to 0 and solve for $\sigma$:

$$
\begin{align}
0&=-\frac{n}{\sigma}+\frac{1}{\sigma^3}[(x_1-\mu)^2+\dots+(x_n-\mu)^2] \\
&=-n+\frac{1}{\sigma^2 }[(x_1-\mu)^2+\dots+(x_n-\mu)^2] \\
n&=\frac{1}{\sigma^2 }[(x_1-\mu)^2+\dots+(x_n-\mu)^2] \\
n\sigma^2&=(x_1-\mu)^2+\dots+(x_n-\mu)^2 \\
\sigma^2&=\frac{(x_1-\mu)^2+\dots+(x_n-\mu)^2}{n} \\
\sigma&=\sqrt \frac{(x_1-\mu)^2+\dots+(x_n-\mu)^2}{n} \\
\end{align}
$$

__The maximum likelihood estimate for $\sigma$ is the standard deviation of the measurements.__

## Visualizations


![[Pasted image 20230427105914.png]]


![[Pasted image 20230427000823.png]]


In a likelihood calculation of a normal distribution with multiple variables:


![[Pasted image 20230427104115.png]]


---

## References

[Maximum Likelihood For the Normal Distribution, step-by-step!!! - YouTube](https://www.youtube.com/watch?v=Dn6b9fCIUpM&t=6s)
[Statistics Fundamentals - YouTube](https://www.youtube.com/playlist?list=PLblh5JKOoLUK0FLuzwntyYI10UQFUhsY9)