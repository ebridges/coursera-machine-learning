##  Summary [^48]

Putting all the pieces together from the previous lessons.

### Network Architecture

First, you need to decide on a network architecture.  The choices that need to be decided on are:

* Number of input units: the dimension of features $x^{(i)}$;
* Number of output units: the number of classes in your classification problem;
* Number of hidden layers: the defaults would be 1 hidden layer. If you have more than 1 hidden layer, then it is recommended that you have the same number of units in every hidden layer.
* Number of hidden units per layer = usually more the better (must balance with cost of computation as it increases with more hidden units)

### Training a Neural Network

1. Randomly initialize weights.
2. Implement forward propagation to get $h_\Theta(x^{(i)})$ for any $x^{(i)}$
3. Implement code to compute cost function $J(\Theta)$
4. Implement back propagation to compute partial derivatives $\frac{\partial}{\partial\Theta^{(l)}_{jk}}J(\Theta)$
   * To implement backprop there will be a for loop (at least when you're starting out, more sophisticated approaches exist) over the $m$ training examples, within which we would do the following:
     1. Perform forward and back propagation using each training set example $(x^{(i)}, y^{(i)})$ for $i$ in $1:m$ of training set of size $m$.
     2. This would result in activations $a^{(l)}$ and delta terms $\delta{(l)}$ for $l = 2,…,L$
5. Compute the partial derivatives that will be needed to execute gradient descent, using the delta terms computed with forward and back propagation. 
6. Use gradient checking to compare the partial derivatives computed using backprop vs. using numerical estimate of gradient of $J(\Theta)$. 
   * Disable gradient checking code.
7. Use gradient descent (or advanced optimization e.g. `fminunc`) method with back propagation to try to minimize $J(\Theta)$ as a function of paramters $\Theta$.
   * Note $J(\Theta)$ is non-convex and can result in local optimization.
