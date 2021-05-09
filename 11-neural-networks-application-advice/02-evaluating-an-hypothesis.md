---
Video: machine-learning/10_advice-for-applying-machine-learning/01_evaluating-a-learning-algorithm/02_evaluating-a-hypothesis.mp4
---

## Evaluating an Hypothesis

A hypothesis may have a low error for the training examples but still be inaccurate (because of overfitting). Thus, to evaluate a hypothesis, given a dataset of training examples, we can split up the data into two sets: a **training set** and a **test set**. Typically, the training set consists of 70 % of your data and the test set is the remaining 30 %.

The new procedure using these two sets is then:

1. Learn $\Theta$ and minimize $J_{train}(\Theta)$ using the training set
2. Compute the test set error $J_{test}(\Theta)$

### Procedure for computing test set error

#### For Linear Regression

Compute the squared error for the test set.

 $J_{test}(\Theta) = \dfrac{1}{2m_{test}} \sum_{i=1}^{m_{test}}(h_\Theta(x^{(i)}_{test}) - y^{(i)}_{test})^2$

#### For Logistic Regression

First, learn parameters from the training data, and then compute test error using the [same cost function](07-logistic-regression-model/02-simplified-cost-function.md) that we always use for logistic regression except we're substituting in the test set, as follows:
$$
J_{test}(\Theta)=-\frac{1}{m_{test}}\sum^{m_{test}}_{i=1}y^{(i)}_{test}log\ h_{\Theta}(x^{(i)}_{test})+(1-y^{(i)}_{test})log\ h_{\Theta}(x^{(i)}_{test})
$$
While this is reasonable to use, sometimes there's an easier way of doing this by evaluating misclassification error (aka 0/1 misclassification error):
$$
err(h_\Theta(x),y)=\begin{cases}1&if\  h\Theta (x)\geq 0.5\  and\  y=0\  \\&or\  h\Theta (x)<0.5\  and\  y=1\\ 0&otherwise\end{cases}
$$

> In this example, $0$ will be the result if the hypothesis correctly predicted the value of $y$.  However, if the hypothesis evaluated greater or less than the threshold (in this example, $0.5$), and returned an incorrect value of $y$ (e.g. 0 if greater than threshold or vice versa), then it will result in a value of $1$.

This gives us a binary 0 or 1 error result based on a misclassification. The average test error for the test set is:
$$
Test Error= \frac{1}{m_{test}}\sum^{m_{test}}_{i=1}err(h_\Theta(x^{(i)}_{test}),y^{(i)}_{test})
$$
This gives us the proportion of the test data that was misclassified.



