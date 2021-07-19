## Collaborative Filtering [^88]

This is an approach to building a recommender system which has an interesting property known as "feature learning" that can start to learn for itself what features to use.

Earlier we discussed an approach for recommendations using the content of a movie.  This is a limited approach because we don't know all of the features that we may want to recommend based on, and we are not able to efficiently gain ratings on each and every feature.

Let's assume that all of the users have told us how much they like different types of movies (e.g. Alice really likes romantic movies), thus giving us the parameter $\theta^{(j)}$.  With that parameter we can then infer what are the values of $x_1$ and $x_2$ for each movie.

In other words, if Alice and Bob both love romantic movies, and Carol and Dave both hate them.  Then, given a new movie seen by them if Alice and Bob loved it and Carol and Dave hate it, then we can infer that this movie is probably a romantic movie and likely not an action movie.

In mathematical terms, we're trying to express: what feature vector should $x^{(1)}$ be so that:
$$
(\theta^{(1)})^Tx^{(1)}\approx5 \\
(\theta^{(2)})^Tx^{(1)}\approx5 \\
(\theta^{(3)})^Tx^{(1)}\approx0 \\
(\theta^{(4)})^Tx^{(1)}\approx0 \\
$$
Given what we know about what Alice, Bob, Carol and Dave feel about the movie we can infer that: $x_{(1)}=\begin{bmatrix}1\\ 1.0\\ 0.0\end{bmatrix}$

The optimization objective for this is very similar as in the previous section, except that given $\theta^{(1)},…,\theta^{(n_u)}$, we're trying to learn $x^{(i)}$:
$$
\min_{x^{(j)}} \frac{1}{2}\sum_{j:r(i,j)=1}\left((\theta^{(j)})^Tx^{(i)}-y^{(i,j)} \right)^2+\frac{\lambda}{2}\sum_{k=1}^{n}\left( \theta^{(j)}_{k} \right)^2
$$
To do for all users is the analogous to the previous section as well.

So if you have all the movie ratings, and features you can learn the parameters for each of the users.  If your users are able to provide you with parameters for each movie, then you can estimate values for all of the features.

To do so, randomly guess some value for the $\theta$ parameters and then use the method in the previous video for guessing features for the movies, and then that can be refined to better estimate a new set of parameters.  Doing this iteratively, the algorithm will converge to a reasonable set of features and user affinities for the movies.

In the next section we will provide an explanation of the algorithm for this.
