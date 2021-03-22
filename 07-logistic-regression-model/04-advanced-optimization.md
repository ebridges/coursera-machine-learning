---
Video: machine-learning/06_logistic-regression/02_logistic-regression-model/05_advanced-optimization.mp4
---

## Advanced Optimization

Techniques more sophisticated than gradient descent for optimizing $\theta$ are "Conjugate Gradient", "BFGS", and "L-BFGS" all of which work faster than GD.  Octave provides these algorithms.

Reminder that the goal of GD is to minimize a cost function $J(\theta)$, and given this definition of gradient descent:
$$
Repeat \left\{
\theta_j:=\theta_j-\alpha\frac{\partial}{\partial\theta_j}J(\theta)
\right\}
$$
Note if we had code that can compute, given $\theta$, the following:
$$
J(\theta)\\
\frac{\partial}{\partial\theta_j}J(\theta) \ (for\ j=0,1,...,n)
$$
If we had code that can compute these values then we could use other optimization algorithms besides Gradient Descent for minimizing the cost function:

* Conjugate Gradient
* BFGS
* L-BFGS

While these all have a disadvantage of being more complex (learning them taking days or weeks to study them in a course on ML), they have the following advantages:

* No need to manually pick $\alpha$, they have a "clever inner loop" known as a line search algorithm, that automatically tries different values for alpha and evaluates them.
* Often converge must faster than gradient descent.
* They can be used without needing to understand the internals of how they work.

### Example

Given the following, where $(3)$ is a matrix of our parameters, $(4)$ is our cost function, and $(5)$ are the derivatives of our cost function:
$$
\theta = \begin{bmatrix}\theta_{1} \\ \theta_{2} \end{bmatrix}
$$

$$
J(\theta)=(\theta_1-5)^2+(\theta_2-5)^2
$$

$$
\frac{\partial}{\partial\theta_1}J(\theta)=2(\theta_1-5)\\
\frac{\partial}{\partial\theta_2}J(\theta)=2(\theta_2-5)
$$

We would implement an octave function as follows:

```octave
function [jVal, gradient] = costFunction(theta)
  jVal = (theta(1)-5)^2 + ... + (theta(2)-5)^2;
  gradient = zeros(2, 1)
  gradient(1) = 2*(theta(1)-5);
  gradient(2) = 2*(theta(2)-5);
```

This is a function that given $\theta$ will return a way to compute the cost function, and the second argument is a 2x1 vector, whose two elements correspond to the two partial derivatives.

Given those two return values we can then pass this function to the octave function `fminunc` ("function minimization unconstrained"):

```octave
options = optimset('GradObj', 'on', 'MaxIter', '100')
initialTheta = zeros(2,1)
[optTheta, functionVal, exitFlag] = fminunc(@costFunction, initialTheta, options)
```

The return value `optTheta` is the optimal value of theta.