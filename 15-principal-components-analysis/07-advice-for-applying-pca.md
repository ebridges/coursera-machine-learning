---
Video: machine-learning/14_dimensionality-reduction/03_applying-pca/03_advice-for-applying-pca.mp4
---

## Advice for Applying PCA

### Speeding up Runtime

Principal component analysis can be used to speed up the running time of a learning algorithm — and using it for this in supervised learning is is actually one of its most common applications.

Given a supervised learning problem with the following inputs, whose examples are very high dimensional (e.g. $x^{(i)}\in \mathbb{R}^{10000}$, say an imaging problems whose features are individual features):
$$
(x^{(1)}, y^{(1)}), (x^{(2)}, y^{(2)}), ..., (x^{(m)}, y^{(m)})
$$
This large amount of data can make the algorithm run slowly.  PCA can help speed this up through this process.

First we're going to extract inputs to an unlabeled dataset, apply PCA and obtain a reduced dimension representation of this data:
$$
x^{(1)}, x^{(2)}, ..., x^{(m)} \in \mathbb{R}^{10000} \\
\downarrow PCA \\
z^{(1)}, z^{(2)}, ..., z^{(m)} \in \mathbb{R}^{1000}
$$
Now we have a new training set of a much smaller size:
$$
(z^{(1)}, y^{(1)}), (z^{(2)}, y^{(2)}), ..., (z^{(m)}, y^{(m)})
$$
We can now feed this training set to a learning algorithm, which we can use to train an hypothesis; e.g. with logistic regression would take one of these new $z$ vectors as a parameter:
$$
h_\theta^{(z)}=\frac{1}{1+e^{-\theta^Tz}}
$$
Note: what this does is create a mapping from $x$ to $z$, and should be defined by running PCA only on the training set. This mapping can be applied as well to the examples $x_{cv}^{(i)}$ and $x_{test}^{(i)}$, in the x-validation and test sets.

### Application of PCA

* **Compression**

  * Reduce memory/disk needed to store data
  * Speed up learning algorithm

  For this scenario we choose $k$ by the percentage of variance retained.

* **Visualization**

  For this scenario we choose $k$ based on the business purpose of the data, and mostly we know only how to plot 2D or 3D data, and so we'd use 2 or 3 for a value of $k$.

### Misapplication of PCA

* **Preventing Overfitting**

  If use zi instead of xi to reduce the number of features to k < n we would then have fewer features and thereby less likely to overfit.  This is a bad application of PCA.

  This might work OK, but isn't a good way to address overfitting.  Instead use regularization for this task.

  The reason why is that PCA does not use the $y$ label in the data, throwing it away without knowing what those values.  This is okay if you're retaining 99% of the variance but it also dispenses with valuable information.  Just using regularization will give you at least a good a method for preventing overfitting, and will often be better.

* **Unnecessary Application**

  Before implementing PCA first try running whatever you want to do with original/raw data $x^{(i)}$.  Only then, if that doesn't do what you want, implement PCA and consider using $z^{(i)}$.