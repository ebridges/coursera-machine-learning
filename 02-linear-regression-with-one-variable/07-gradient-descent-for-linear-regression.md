## Application of Gradient Descent to Linear Regression [^9]

The cost function in linear regression provides a measure for us to know how well a given hypothesis fits to a training set of observations.  The lower the result of the cost function for a given set of parameters $\theta_{0} ,\theta_{1}$, then the better the fit for the hypothesis. In order to aid us in minimizing the cost function, we will use gradient descent. 

The key term we need to apply gradient descent is the derivative of the cost function, outlined below in red:

![](NBDraggedImage%207.png)

The professor reduces that value to obtain the following functions for a value of j=0, and j=1:

![](NBDraggedImage%208.png)

When we plug these values back into the original algorithm, we get the following, where the reduced versions of the linear regression model are substituted in for the partial derivatives in the gradient descent algorithm, for each of $\theta_{0}$ and $\theta_{1}$:

![](NBDraggedImage%209.png)

The cost function for linear regression will always be a bowl shaped (or, "convex") function.  As a result, minimizing it using gradient descent will always lead to the global minimum as there is only one.

### Batch Gradient Descent

In every step of gradient descent we end up looking at all training examples.  When computing derivatives we end up computing over all $m$ training examples. Turns out there are other version of Gradient descent that look at small subsets of the training set at a time.

it is possible to obtain the minimum cost function w/o needing to use an iterative function like gradient descent.  This is known as the "normal equations method", however gradient descent scales better to larger data sets.
