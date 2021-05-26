---
Video: machine-learning/10_advice-for-applying-machine-learning/01_evaluating-a-learning-algorithm/01_deciding-what-to-try-next.mp4
---

## Deciding on What to Try Next

There's often a huge difference between someone that really knows how to powerfully and effectively apply a learning algorithm, versus someone who doesn't really understand them and can end up wasting a lot of their time trying things out that don't make sense.

Suppose you are developing an ML system or trying to improve the performance of one, how do you go about deciding what the the proper avenues to try next when troubleshooting.

Concretely, suppose you have implemented regularized linear regression to predict housing prices, and when you test your hypothesis, and you find that it makes unacceptably large errors in its predictions.  What should you try next?

* Get more training examples
* Try smaller sets of features
* Try getting additional features
* Try adding polynomial features
* Try decreasing or increasing $\lambda$

Each of these can be multi-month projects and often people unfortunately go with their gut instinct in choosing, and can end up wasting six months only to discover that it wasn't a promising pursuit.

  Machine learning diagnostics can be used to gain insights about what is/isn't working with a learning algorithm and gain guidance on how best to improve performance.  These can be challenging to implement but will save months by avoiding avenues that won't be productive.

