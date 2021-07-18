---
Video: machine-learning/15_anomaly-detection/02_building-an-anomaly-detection-system/01_developing-and-evaluating-an-anomaly-detection-system.mp4
---

## Developing and Evaluating an Anomaly Detection System

The process of how to go about developing a specific application of anomaly detection and how to evaluate how well it's doing at detecting anomalies.

When developing a learning algorithm, it's much easier if we have a way of evaluating the algorithm as you go along.  There are a lot of decisions to make when doing this — say I have an idea for a new feature — and if you're just given a number in order to make that determination.

Assume we have some labeled data of anomalous & non-anomalous examples.  For a training set assume all normal examples.  The cross validation & test sets will include a few examples that are known to be anomalous.

Let say we have a motivating example with 10000 normal airplane engines, and 20 airplane engines with flaws.

Given this data set, a typical way to design our data is as follows:

| Data Set         | Normal Engines | Anomalous Engines |
| ---------------- | -------------- | ----------------- |
| Training Data    | 6000           | 0                 |
| Cross Validation | 2000           | 10                |
| Test Data        | 2000           | 10                |

We'd use the Training Data to fit $p(x)$, and to estimate the parameters $\mu$ and $\sigma^2$.  We'd then use the Cross Validation and Test Data to evaluate the anomaly detection. It is recommended to use different data for all three data sets — not to reuse data across the data sets.

### Algorithm Evaluation

1. Fit model $p(x)$ on training set, which we assume is all normal.

2. On a cross validation/test example $x$, use the anomaly prediction algorithm predict to predict the $y$ labels, and how often it gets these right:
   $$
   y=\begin{cases}1&if\  p(x)<\epsilon\ (anomaly)\\ 0&if\  p(x)\geq \epsilon\ (normal)\end{cases}
   $$
   

   * You can also use the cross validation set to choose parameter $\epsilon$

#### Possible Evaluation Metrics

Because the data is overwhelmingly normal, resulting in a skewed class, classification accuracy is not a good metric for evaluating the algorithm. Instead we should use the following:

* True/false positive, true/false negative fractions
* Computing the precision/recall
* Computing the $F_1$ score.
  * Try many values of $\epsilon$ to revaluate the $F_1$ score
