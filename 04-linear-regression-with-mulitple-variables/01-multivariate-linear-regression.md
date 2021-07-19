## Multiple Features [^16]

So far we have been trying to predict a price based on the number of square footage of the property.  What if we wanted to use multiple features besides square footage (e.g. number of bedrooms, number of floors, age of home) to predict a price?

Instead of using just $(x, y)$ to represent a feature ($x$) to predict a price ($y$), we will use the following notation:
$$
x_1, x_2, ..., x_n
$$

* $n$ is the number of features
* $x^{(i)}$ is the $i^{th}$ element of the training set.
* $x{}^{(i)}_{j}$ is the value of feature $j$ in $i^{th}$ element of the training set.

The training set is represented as an $m \times n$ matrix of values where each row in the matrix is another input element of the training set. So if you take, for example, the first row that would be a vector of features that can be used to describe a single price.

## Multivariate Hypothesis Function

When we only had two features, our hypothesis function looked like this:
$$
h_\theta(x) = \theta_0 + \theta_1 \times x
$$
With multiple features our hypothesis will look like this, say for a data set with $n$ features.
$$
h_\theta(x) = \theta_0 + \theta_1x_1 + \theta_2x_2 + \theta_3x_3 + ... + \theta_nx_n
$$
To simplify this, let's simplify by assuming $x_0 = 1$, so for every example data set $i$ then there will be an additional $0^{th}$ feature whose value will always be 1.

So this means that we now have two vectors, one for the example training data set (4), and the set of $\theta$ parameters (5):
$$
x = \begin{bmatrix}x_0 \\x_0\\x_1\\x_2 \\\vdots \\x_n \\\end{bmatrix}
$$

$$
\theta = \begin{bmatrix}\theta_0 \\\theta_0\\\theta_1\\\theta_2 \\\vdots \\\theta_n \\\end{bmatrix}
$$

Given this our hypothesis can now be written like this:
$$
h_\theta(x) = \theta_0x_0 + \theta_1x_1 + \theta_2x_2 + \theta_3x_3 + ... + \theta_nx_n
$$
Which can also be understood as the product of the transpose of $\theta$ and $x$:
$$
h_\theta(x) = \theta^{T}x
$$
