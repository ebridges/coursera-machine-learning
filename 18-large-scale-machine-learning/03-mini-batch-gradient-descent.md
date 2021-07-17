---
Video: machine-learning/17_large-scale-machine-learning/01_gradient-descent-with-large-datasets/03_mini-batch-gradient-descent.mp4
---

## Mini-batch Gradient Descent

Batch gradient descent: use all $m$ examples in each iteration.

Stochastic gradient descent: use 1 example1 in each iteration.

Mini-batch gradient descent: use $b$ examples in each iteration, where $b$ is the mini-batchsize. A typical size of a mini-batch is 2-100.

Here's an examaple of the algorithm:

Assume $b=10$, $m=1000$

Repeat `{`
        for i:=1, 11, 21, 31…991 {
        $\theta_j:=\theta_j — \alpha \frac{1}{10} (h_θ^{(i)}-y^{(i)})\times x^{(i)}_j \\ (for\ every\ j=0,…,n)$
       }
}

The downside of MbGD is the need to choose a value for the parameter $b$.

