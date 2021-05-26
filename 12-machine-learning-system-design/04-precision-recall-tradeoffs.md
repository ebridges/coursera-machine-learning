---
Video: machine-learning/11_machine-learning-system-design/02_handling-skewed-data/02_trading-off-precision-and-recall.mp4
---

## Precision & Recall Tradeoffs

When using Precision & Recall as an evaluation metric for classification problems with skewed constants, for many applications we will want to somehow control the trade-off between them.

 Given an example where we're trying to predict cancer, and we're using a logistic regression learning algorithm that will give us a value $0 \le h_0(x) \le 1$. And we will predict a category as follows:

Predict $1$ if  $h_0(x)\ge0.5$

Predict $0$ if $h_0(x)\lt0.5$

Suppose we want to predict $y=1$ only if very confident.  To improve confidence we can change the threshold of the prediction from $0.5$ to $0.7$, or even $0.9$.  Doing so, will ensure that we're only saying that the case is cancerous if we're more confident that the result is accurate: this will lead to _higher precision_, but _lower recall_ because we will be missing some cases where the person is cancerous but we were less confident of the prediction.

Now, suppose we want to avoid missing too many cases of cancer — i.e. avoid false negatives. In that case we may change the threshold of the prediction to a lower value, say $0.3$ or even $0.2$.  This will lead to _lower precision_, but _higher recall_ and potentially avoid telling people that they don't have cancer when they actually do with the tradeoff that we may tell people that they do have it when they actually don't.

### Using $F_1$ Score for Precision/Recall Comparison

How to compare precision/recall numbers, in order to evaluate different algorithms?

#### F-Score

$$
2\frac{PR}{P+R}
$$

Where $P$ is precision, and $R$ is recall.

This works better than, say, an average because it gives the lower value of $P$ or $R$ a higher weight.

