## Random Initialization of Cluster Centroids [^69]

How do we randomly initialize the K cluster centroids before beginning execution of the k-means algorithm?

* Should have $K$ < $m$
* Randomly pick $K$ training examples.
* Set $\mu_1,…\mu_K$ equal to these $K$ examples.

As you could imagine, k-means could end up with different solutions.  Indeed it could end up at bad local optima rather than global.

If we want to ensure that k-means arrives at the best optima, we can run it multiple times, say anywhere from 50-1000 times. From these we pick the clustering that gives us the lowest cost, or _distortion_.  

If you're running it for a small number of clusters (K=2-10) then this could be effective.  As K gets larger than you'll typically get a good result with fewer iterations.
