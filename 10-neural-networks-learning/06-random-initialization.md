## Random Initialization [^47]

Initializing all theta weights to zero does not work with neural networks. When we backpropagate, all nodes will update to the same value repeatedly.

Instead we can randomly initialize our weights for our $\Theta$ matrices to a random value between $[ -\epsilon, \epsilon ]$ (epsilon as used here is unrelated to the epsilon from Gradient Checking). This approach is known as "symmetry breaking" or "random initialization". 

Using octave we would use the `rand(x, y)` function to initialize a matrix of random real numbers between 0 & 1.

For example:

```octave
# If the dimensions of Theta1 is 10x11, Theta2 is 10x11 and Theta3 is 1x11.

Theta1 = rand(10,11) * (2 * INIT_EPSILON) - INIT_EPSILON;
Theta2 = rand(10,11) * (2 * INIT_EPSILON) - INIT_EPSILON;
Theta3 = rand(1,11) * (2 * INIT_EPSILON) - INIT_EPSILON;
```
