---
Video: machine-learning/09_neural-networks-learning/02_backpropagation-in-practice/03_gradient-checking.mp4
---

## Gradient Checking

Forward- and back-propagation can be very tricky to implement properly, and bugs can get introduced that are very hard to detect or track down.

Gradient checking will assure that our backpropagation works as intended. We can approximate the derivative of our cost function with:

$$
\frac{\partial}{\partial\Theta}J(\Theta)\approx\frac{J(\Theta+\epsilon)-J(\Theta-\epsilon)}{2\epsilon}
$$

With multiple theta matrices, we can approximate the derivative **with respect to** $\Theta_j$ as follows:

$$
\frac{\partial}{\partial\Theta_j}J(\Theta)\approx\frac{J(\Theta_1,...\Theta_j+\epsilon,...,\Theta_n)-J(\Theta_1,...,\Theta_j-\epsilon,...,\Theta_n)}{2\epsilon}
$$

A small value for $\epsilon$ (epsilon) such as $\epsilon=10^{-4}$, guarantees that the math works out properly. If the value for $\epsilon$ is too small, we can end up with numerical problems. 

```octave
epsilon = 1e-4;
for i = 1:n,
  thetaPlus = theta;
  thetaPlus(i) += epsilon;
  thetaMinus = theta;
  thetaMinus(i) -= epsilon;
  gradApprox(i) = (J(thetaPlus) - J(thetaMinus))/(2*epsilon)
end;
```

We previously saw how to calculate the `deltaVector`. So once we compute our `gradApprox` vector, we can check that `gradApprox` ≈ `deltaVector`. 

Once you have verified **once** that your backpropagation algorithm is correct, you don't need to compute `gradApprox` again. The code to compute `gradApprox` can be very slow.
