## Normal Equation [^21]

The normal equation, for some linear regression problems, will give a better way to solve for parameters $\theta$.

So far the algorithm we've been using for linear regression has been gradient descent where in order to minimize $J(\theta)$ we take an iterative approach involving many steps to converge at the global minimum.

In contrast, the normal equation gives us method to solve for $\theta$ analytically. Rather than run this iterative algorithm we just solve for the global minimum in one go.

### Intuition

Starting with a basic example let's gain an intuition for this.

 Assume that $\theta$ is just a scalar value, a number and not a vector; and, that we have a this quadratic function for a cost function: $J(\theta)=a\theta^2+b\theta+c$.  How do you minimize a quadratic function?

If $\theta$ is a scalar value, one can just use calculus — you take derivatives and set the derivatives equal to zero and solve for theta.

When $\theta$ is a vector value, our cost function looks like this:
$$
J(\theta_0,\theta_1,...,\theta_n)=\frac{1}{2m}\sum^{m}_{i=1} (h_{\theta }(x^{(i)})-y^{\left( i\right)  })^{2}
$$
Using calculus we could take the partial derivative of the cost function for every parameter $\theta$ in turn, and then set each to zero, and solve for each $\theta_0,\theta_1,...,\theta_n$, then if you actually work through the calculus you'll get the answer but it will end up being very involved.

Rather than going through all that, he will just show us how to go about solving this for the minimum value.

Given the following test training dataset, with 4 training examples ($m=4$), and 4 features ($x_n$) with an additional feature $x_0$:

|       | Size ($ft^2$) | # Bedrooms | # Floors | Age (years) | Price ($1000) |
| :---: | :-----------: | :-------: | :-----: | :---------: | ------------- |
| $x_0$ |     $x_1$     |   $x_2$   |  $x_3$  |    $x_4$    | $y$           |
|   1   |     2104      |     5     |    1    |     45      | 460           |
|   1   |     1416      |     3     |    2    |     40      | 232           |
|   1   |     1534      |     3     |    2    |     30      | 315           |
|   1   |      852      |     2     |    1    |     36      | 178           |

Let's put our features in an $m\times(n+1)$ matrix named $X$, and the prices in an $m$ dimension vector named $y$. Letting $m$ be the number of training examples, and $n$ be the number of features (plus one special feature of all ones):
$$
X=\begin{bmatrix}1&2104&5&1&45\\ 1&1416&3&2&40\\ 1&1534&3&2&30\\ 1&852&2&1&36\end{bmatrix} 
y = \begin{bmatrix}460 \\ 232 \\ 315 \\ 178\end{bmatrix}
$$
Then we can compute a $m$ dimension vector containing the values for $\theta$ that minimizes our cost function by the following formula:
$$
\theta=(X^TX)^{-1}X^Ty
$$

### More General Form

Let's say we have $m$ training examples $(x^{(1)},y^{(1)}),...(x^{(m)},y^{(m)})$ and n features.  Our training example would look like this:
$$
x^{(i)}=\begin{bmatrix}x^{(i)}_0 \\ x^{(i)}_1 \\ x^{(i)}_2 \\ \vdots \\ x^{(i)}_n \end{bmatrix}
$$
Our _design matrix_ (matrix X) and solutions ($y$) vector are constructed as 
$$
X=\begin{bmatrix} (x^{(1)})^T \\ (x^{(2)})^T \\ \vdots \\ (x^{(m)})^T \end{bmatrix} y=\begin{bmatrix} y^{(1)} \\ y^{(2)} \\ \vdots \\ y^{(m)} \\ \end{bmatrix}
$$
We then can compute $\theta$ as follows:
$$
\theta=(X^TX)^{-1}X^Ty
$$

* $(X^TX)^{-1}$ is the inverse of matrix $X^TX$
* Set A = $X^TX$ then the inverse is $A^{-1}$

* In octave this would be `pinv(X'*X)*X'*y`
* in octave `x'` is $X^T$

When using the normal equation to solve for $\theta$, feature scaling is not necessary, unless using Gradient Descent.

### When to Choose the Normal Equation

Given $m$ training examples & $n$ features.

| Gradient Descent                          | Normal Equation                                           |
| ----------------------------------------- | :-------------------------------------------------------- |
| • Need to choose $\alpha$ (learning rate) | • No need to choose $\alpha$                              |
| • Needs many iterations                   | • Don't need to iterate.                                  |
| • Works well even when $n$ is large.      | • Need to compute $(X^TX)^{-1}$ (performance is $O(n^3)$) |
|                                           | • Slow if $n$ is very large.                              |

*  If $n=100$ that's okay, but if much bigger than $n=10000$, it would be very expensive and GD should be preferred
