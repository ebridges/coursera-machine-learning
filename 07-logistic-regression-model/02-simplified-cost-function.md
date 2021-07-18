---
Video: machine-learning/06_logistic-regression/02_logistic-regression-model/03_simplified-cost-function-and-gradient-descent.mp4
---

## Simplified Cost Function

We can simplify our cost function's two conditions into one case:
$$
Cost(h_\theta(x),y)=-y\ log(h_\theta(x))-(1-y)log(1-h_\theta(x))
$$
Note that when $y=1$, then the second term $(1-y)log(1-h_\theta(x))$ will be zero and will not affect the result. Conversely, if $y=0$, then the first term $-y\ log(h_\theta(x))$ will be zero and will also not affect the result.

We can then express the entire cost function as follows:
$$
J(\theta)=-\frac{1}{m}\sum^{m}_{i=1}\left[ y^{(i)}log(h_\theta(x^{(i)}))+(1-y^{(i)})log(1-h_\theta(x^{(i)}))\right]
$$
A vectorized implementation of this is expressed as:
$$
h=g(X\theta)\\
J(\theta)=\frac{1}{m}\cdot\left(-y^Tlog(h)-(1-y)^Tlog(1-h)\right)
$$
