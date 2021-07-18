---
Video: machine-learning/13_unsupervised-learning/01_clustering/03_optimization-objective.mp4
---

## Clustering: Optimization Objective

Supervised learning algorithms like linear regression, logistic regression, etc have an opimization objective, or some cost function that the algorithm was trying to minimize. K-means also has an optimization objective, or cost function, that it's trying to minimize.

The reasons why we want to do this is twofold: first, knowing what the optimization objective for k-means will help us to debug the learning algorithm, and make sure that it's running correctly; second, we can use this to help k-means to find better costs for and to avoid local optima.

We keep track of a set of variables while k-means is running, assuming $K$ is the number of cluster centroids, and $k$ is a particular cluster centroid:

* $c^{(i)}$: the index or number of the cluster to which an example $x_i$ is currently assigned.
* a set one or more of $\mu_k$ — the location of the cluster centroid $k$
* $\mu_{c^{(i)}}$: the cluster centroid to which example $x^{(i)}$ has been assigned.

### Optimization Objective

$$
J\left( c^{\left( 1\right)},...,c^{(m)},\mu_{1} ,...,\mu_{K}\right) =\frac{1}{m} \sum^{m}_{i=1} \parallel x^{(i)}-\mu_{c^{(i)}} \parallel^{2}  
$$

The cost function $J()$ (also known as the _distortion_ of the k-means algorithm) accepts all the indices and $\mu$ locations, and the calculation is the average of the squared sum of the differences between the the example data and the cluster centroid.

What k-means can be shown to be doing is that it's trying to define parameters $c^{(i)}$ and $\mu_i$ to try to minimize this cost function $J()$.
