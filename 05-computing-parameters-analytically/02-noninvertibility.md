---
Video: mmachine-learning/04_linear-regression-with-multiple-variables/03_computing-parameters-analytically/03_normal-equation-noninvertibility.mp4

---

## Noninvertibility

When implementing the normal equation in octave we want to use the `pinv` function rather than `inv`. The `pinv` function will give you a value of $\theta$ even if $X^TX$ is not invertible. 

If $X^T$ is **noninvertible,** the common causes might be having :

* Redundant features, where two features are very closely related (i.e. they are linearly dependent).  For example:
  * $x_1$ = size in square feet
  * $x_2$ = size in square meters.
  * 1 meter == 3.28 feet, so $x_1 = (3.28)^2 \times x_2$
* Too many features (e.g. $m$ ≤ $n$). In this case, delete some features or use "regularization" (to be explained in a later lesson).

Solutions to the above problems include deleting a feature that is linearly dependent with another or deleting one or more features when there are too many features.