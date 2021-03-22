---
Video: machine-learning/04_linear-regression-with-multiple-variables/02_multivariate-linear-regression/03_gradient-descent-for-multiple-variables.mp4
---

## Gradient Descent for Multiple Variables

**Hypothesis**: $h_\theta(x) = \theta^{T}x = \theta_0x_0 + \theta_1x_1 + \theta_2x_2 + \theta_3x_3 + ... + \theta_nx_n$

**Parameters**: $\theta$ (an n+1 vector)

**Cost Function**: $J(\theta) =  \frac{1}{2m} \sum^{m}_{i=1} (h_{\theta }(x^{(i)})-y^{\left( i\right)  })^{2}$

**Gradient Descent**: 

​	Repeat $\begin{cases}\theta_{j} :=\theta_{j} -\alpha \frac{\partial }{\partial \theta_{j} } J(\theta)&simultaneously\  update\  for\  j=0,...,n\end{cases} $ 

## Explanation

For gradient descent with one feature, we used the following approach:
$$
Repeat \begin{cases}\theta_{j} :=\theta_{j} -\alpha \underbrace{\frac{1}{m} \sum^{m}_{i=1} (h_{\theta }(x^{(i)})-y^{\left( i\right)  })}_{\frac{\partial }{\partial \theta_{j} } J(\theta_{0})} &j=0\\ \theta_{j} :=\theta_{j} -\alpha \frac{1}{m} \sum^{m}_{i=1} (h_{\theta }(x^{(i)})-y^{(i)})x^{(i)}&j=1\end{cases}
$$
Note that when $j=0$, the term multiplied by the learning rate is equivalent to the partial derivative of the cost function with respect to $\theta_0$.

When we have more than one feature we get the following:
$$
Repeat \begin{cases}\theta_{j} :=\theta_{j} -\alpha \frac{1}{m} \sum^{m}_{i=1} (h_{\theta }(x^{(i)})-y^{\left( i\right)  })x\ ^{(i)}_{j} &j=0,...,n\end{cases}
$$
Note, again, that the term multiplied by the learning rate is equivalent to the partial derivative of $J(\theta)$
$$
Repeat \begin{cases}\theta_{j} :=\theta_{j} -\alpha\frac{\partial}{\partial\theta_{j}} J(\theta)&j=0,...,n\end{cases}
$$
