---
Video: machine-learning/02_linear-regression-with-one-variable/02_parameter-learning/03_gradient-descent-intuition.mp4
---

## Gradient Descent Algorithm

$$
\theta_{j} :=\theta_{j} -\alpha \frac{\partial }{\partial \theta_{j} } J(\theta_{0} ,\theta_{1} )\  \  (for\  j=0\  and\  j=1)
$$

Where $\alpha$ is the _learning rate_ term and $\frac{\partial }{\partial \theta_{j} } J(\theta_{0} ,\theta_{1} )$ is the _derivative_ term.

Let's develop an intuition for these two terms.

### Learning Rate

![](/Users/ebridges/Documents/coursera-dl/notes/machine-learning/02-linear-regression-with-one-variable/05-gradient-descent.assets/NBDraggedImage 6.png)

Continuously, simultaneously reduce the values for $\theta_{0}$ and $\theta_{1}$ by the learning rate (alpha) until the result converges on a minimum.

### Derivative

The **derivative portion** of this presents us with the slope of a specific point on the curve of the cost function.  If the slope presents itself as a positive value (as when the point on the cost function is to the right of the minimum) then we will end up progressively *reducing* the value of $\theta_{j}$; when the slope of a negative value then it will end up increasing the value of $\theta_{j}$:

![](/Users/ebridges/Documents/coursera-dl/notes/machine-learning/02-linear-regression-with-one-variable/05-gradient-descent.assets/NBDraggedImage 5.png)

### Properties of Gradient Descent

Some properties of gradient descent:

* If $\theta_{1}$ is at a local minimum, subsequent steps of gradient descent will have no effect on $\theta_{1}$. The slope (derivative) will be 0 and will multiply against $\alpha$, resulting in no change to $\theta_{1}$.
* Gradient descent can converge to a local minimum even with the learning rate fixed.  As we approach a local minimum, gradient descent will automatically take smaller steps; so no need to decrease alpha over time. As you approach the minimum the derivative gets closer to zero, resulting in smaller steps.
