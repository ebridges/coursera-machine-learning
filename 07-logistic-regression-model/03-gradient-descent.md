---
	Video: machine-learning/06_logistic-regression/02_logistic-regression-model/03_simplified-cost-function-and-gradient-descent.mp4
---

### Gradient Descent

The general form of gradient descent is:
$$
Repeat \left\{
\theta_j:=\theta_j-\alpha\frac{\partial}{\partial\theta_j}J(\theta)
\right\}
$$
Using calculus the derivative part can be worked out to get:
$$
Repeat \left\{
\theta_j:=\theta_j-\frac{\alpha}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j
\right\}
$$
Notice that this algorithm is identical to the one we used in linear regression. The values in theta still need to be updated simultaneously. The difference is that $h_\theta(x)$ for linear regression is $\theta^Tx$ whereas for logistic regression it's $\frac{1}{1+e^{-\theta^Tx}}$.

Monitoring gradient descent for logistic regression is done the same way as for linear regression.

A vectorized version is:
$$
\theta:=\theta-\frac{\alpha}{m}X^T(g(X\theta)-\vec{y})
$$
