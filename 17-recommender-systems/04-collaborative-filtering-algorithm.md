### Collaborative Filtering Algorithm [^89]

To restate the optimization objectives from the previous two sections:

Given $x^{(i)},…,x^{(n_m)}$, estimate $\theta^{(1)},…,\theta^{(n_u)}$:
$$
\min_{\theta^{(1)},…,\theta^{(n_u)}} \frac{1}{2} \sum_{j=1}^{n_u}   \sum_{i:r(i,j)=1}\left((\theta^{(j)})^Tx^{(i)}-y^{(i,j)} \right)^2+\frac{\lambda}{2}\sum_{j=1}^{n_u}\sum_{k=1}^{n}\left( \theta^{(j)}_{k} \right)^2
$$
And, given $\theta^{(1)},…,\theta^{(n_u)}$, estimate $x^{(i)},…,x^{(n_m)}$:
$$
\min_{x^{(1)},…,x^{(n_m)}} \frac{1}{2} \sum_{j=1}^{n_m}   \sum_{j:r(i,j)=1}\left((\theta^{(j)})^Tx^{(i)}-y^{(i,j)} \right)^2+\frac{\lambda}{2}\sum_{i=1}^{n_m}\sum_{k=1}^{n}\left( x^{(i)}_{k} \right)^2
$$
And, to do collaborative filtering we would iterate back & forth between to these calculations until we get to a reasonable value.  But it turns out there's a more efficient algorithm that doesn't need to go back and forth like that.

To do so we'd combine both of these optimization objectives into one, thus minimizing  $x^{(i)},…,x^{(n_m)}$ and $\theta^{(1)},…,\theta^{(n_u)}$ simultaneously:
$$
J(x^{(i)},…,x^{(n_m)},\theta^{(1)},…,\theta^{(n_u)})=\frac{1}{2}\sum_{(i,j):r(i,j)=1}\left((\theta^{(j)})^Tx^{(i)}-y^{(i,j)} \right)^2+\frac{\lambda}{2}\sum_{i=1}^{n_m}\sum_{k=1}^{n}\left( x^{(i)}_{k} \right)^2+\frac{\lambda}{2}\sum_{j=1}^{n_u}\sum_{k=1}^{n}\left( \theta^{(j)}_{k} \right)^2
$$
With the objective being to minize the resulting values:
$$
\min_{x^{(i)},…,x^{(n_m)}\\\theta^{(1)},…,\theta^{(n_u)}}J(x^{(i)},…,x^{(n_m)},\theta^{(1)},…,\theta^{(n_u)})
$$
*Note*:

* The squared error term in both (e.g.: $\frac{1}{2}\sum_{i:r(i,j)=1}\left((\theta^{(j)})^Tx^{(i)}-y^{(i,j)} \right)^2$) is basically the same.  The summations are slightly different (i.e. for every user  sum up all movies rated by that user vs. for every movie sum over all the users that have rated that movie).  To account for that, we have the sum go over all movies and users (use $(i,j):r(i,j)$, rather than $i:r(i,j)$ and $j:r(i,j)$ ).
* When we're learning the features in this way, we will do away with the convention of $x_0=1$

#### Algorithm

1. Initialize $x^{(i)},…,x^{(n_m)},\theta^{(1)},…,\theta^{(n_u)}$ to small random values.

2. Minimize $J(x^{(i)},…,x^{(n_m)},\theta^{(1)},…,\theta^{(n_u)})$ using gradient descent (or another advanced optimization algorithm). E.g. for every $j=1,…n_u, i=1,…,n_m$:
   $$
   x^{(i)}_k:=x^{(i)}_k-\alpha\left(\sum_{j:r(i,j)=1} ((\theta^{(j)})^Tx^{(i)}-y^{(i,j)})\theta^{(j)}_k+\lambda x^{(i)}_k) \right)\\
   \theta^{(j)}_k:=\theta^{(j)}_k-\alpha\left(\sum_{i:r(i,j)=1} ((\theta^{(j)})^Tx^{(i)}-y^{(i,j)})x^{(i)}_k+\lambda \theta^{(j)}_k) \right)\\
   $$

   * The two terms multiplied by $\alpha$ in the the above are the partial derivatives of the cost function with respect to $x^{(i)}_k$ and $\theta^{(j)}_k$, respectively.

3. For a user with parameters $\theta$ and a movie with (learned) features $x$, predict a star rating of $\theta^Tx$.
