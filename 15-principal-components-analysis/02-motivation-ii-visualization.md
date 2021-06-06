---
Video: machine-learning/14_dimensionality-reduction/01_motivation/02_motivation-ii-visualization.mp4
---

### Motivation II: Visualization

Another application of data compression is to enable a way of visualizing the data better, and open up ways of better understanding the data.

Given a large dataset with many features (say 50 features) it's difficult to visualize/plot so many features for examination and further understanding.

So instead of using so many features, let's say we can come up with a way to summarize the numbers into a pair of numbers.  Then, we can plot these numbers into a simpler space and then we can understand the original dataset better.

More generally, given a dataset:
$$
\{ x^{(1)}, x^{(2)}, ..., x^{(m)}\}\ where\ x^{(i)} \in \mathbb{R}^n
$$
In order to visualize it, we apply dimensionality reduction and get:
$$
\{ z^{(1)}, z^{(2)}, ..., z^{(m)}\}\ where\ z^{(i)} \in \mathbb{R}^k
$$
We can then say that the data is compressed, in other words:
$$
k \le n \\
$$
But also, because we can plot 2D or 3D data, but don't have ways to visualize higher dimensional data, we can say:
$$
k \in \{ 2, 3 \}
$$
