---
Video: machine-learning/07_regularization/01_solving-the-problem-of-overfitting/05_regularized-linear-regression.mp4
---

## Regularization: Linear Regression

For linear regression we worked out two learning algorithms: one based on gradient descent and one based on the normal equation.  Here we take those two algorithms and generalize them to the case of regularized linear regression.

This is the optimization objective that we came up with last time for regularized linear regression:
$$
J(\theta)=\frac{1}{2m} \left[ \sum^{m}_{i=1} (h_{\theta }(x^{(i)})-y^{(i)})^{2}+\lambda \sum^{n}_{j=1} \theta^{2}_{j} \right]
$$
And our goal is to minimize the cost function:
$$
\min_{\theta }J(\theta)
$$

### Gradient Descent

Given the function for Gradient Descent as follows, without regularization, for parameters $j=0,1,2,3,…,n$:
$$
Repeat \left\{
\theta_j:=\theta_j-\alpha\cdot\frac{1}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j
\right\}
$$
Rewritten breaking out the case of $j=0$, because with regularized linear regression we do not penalize the $0^{th}$ case of the parameters — only subsequent ones.
$$
\text{Repeat}\begin{cases}\theta_{0}:=\theta_{0}-\alpha\cdot\frac{1}{m} \sum^{m}_{i=1}(h_{\theta }(x^{(i)})-y^{(i)})x^{(i)}_{0}&j=0\\\theta_{j} :=\theta_{j}-\alpha\cdot\frac{1}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j &j=1,2,3,...n\end{cases}
$$
To then implement regularization above, we simply add the regularization term $\frac{\lambda}{m}\theta_j$ to the function for $j>0$:
$$
\text{Repeat}\begin{cases}\theta_{0}:=\theta_{0}-\alpha\cdot\frac{1}{m} \sum^{m}_{i=1}(h_{\theta }(x^{(i)})-y^{(i)})x^{(i)}_{0}&j=0\\\theta_{j} :=\theta_{j}-\alpha\cdot\frac{1}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j+\frac{\lambda}{m}\theta_j&j=1,2,3,...n\end{cases}
$$
Gathering terms, this can be rewritten as follows:
$$
\text{Repeat}
\begin{cases}
    \theta_{0} :=
    \theta_{0}-\alpha\cdot\frac{1}{m} \sum^{m}_{i=1}(h_{\theta }(x^{(i)})-y^{(i)})x^{(i)}_{0}
    &j=0
    \\
    \theta_{j} :=
    \theta_{j}(1-\alpha\frac{\lambda}{m})-\alpha\cdot\frac{1}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j
    &j=1,2,3,...n
\end{cases}
$$
When the terms are grouped in this way, we end up with two terms for the case $j>0$:
$$
\theta_{j}(1-\alpha\frac{\lambda}{m})
$$
And:
$$
\alpha\cdot\frac{1}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j
$$
In the case of the term $(7)$ above we can note that $\lambda$ and $m$ will always be non-zero and that the value of $1-\alpha\frac{\lambda}{m}$ will always be less than one. This will have the effect of making $\theta_j$ ever smaller.  The second term — which is our standard term for gradient descent, will then be reduced (i.e. regularized) as expected.

### Normal Equation

When using the normal equation for evaluating our cost function on an hypothesis, we started with the following.

First, an design matrix with dimensions $m \times (n+1)$ where each row corresponds to a separate example from the training set:
$$
X=\begin{bmatrix}(x^{(i)})^{T}\\ \vdots \\ (x^{(m)})^{T}\end{bmatrix}
$$
And, then an m-dimensional vector $y$ with the labels from our training sets:
$$
y=\begin{bmatrix}y^{(1)}\\ \vdots \\ y^{(m)}\end{bmatrix}
$$
In order to minimize the cost function $J(\theta)$, we found that one way to do that was to set $\theta$ as follows:
$$
\theta=(X^TX)^{-1}X^Ty
$$
This minimizes theta, but without regularization. To regularize this, we simply add the product of $\lambda$ with an $(n+1)\times(n+1)$ matrix whose upper left value is zero  with ones on the left diagonal. For example:
$$
\begin{array}{ll}\begin{bmatrix}0&0&0\\ 0&1&0\\ 0&0&1\end{bmatrix}&n=2 \end{array}
$$
Thus, the regularized normal equation is as follows, assuming $n=2$:
$$
\left( X^{T}X+\lambda \begin{bmatrix}0&0&0\\ 0&1&0\\ 0&0&1\end{bmatrix} \right)^{-1}  X^{T}y
$$

### Non-Invertibility

Suppose our number of examples ($m$) has the following relationship to the number of features ($n$): $m\leq n$.

If we have fewer examples than features, then the expression $X^TX$ will be non-invertible.  If you use the `pinv` function in octave, it'll give you a result it's not clear it'll give a very good hypothesis.  In another language, using a regular `inv` it simply will not work because of this non-invertibility.

Fortunately, regularization will take care of this for us. As long as the value of $\lambda$ is greater than zero, the product of lambda with that special matrix added to the expression $X^TX$ will give us a result that will always be invertible. 
