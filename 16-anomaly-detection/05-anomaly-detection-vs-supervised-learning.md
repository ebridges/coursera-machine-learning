---
Video: machine-learning/15_anomaly-detection/02_building-an-anomaly-detection-system/02_anomaly-detection-vs-supervised-learning.mp4
---

## Anomaly Detection vs. Supervised Learning

In the process of evaluating an anomaly detection algorithm, we introduced labeled data to help do the evaluation.  This raises the question that, if we've got labeled data to help train our algorithm why not just use supervised learning (e.g. a neural network or logistic regression) to predict whether $y=0$ or $y=1$?

| Anomaly Detection                                            | Supervised Learning                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| • Very small number of positive examples ($y=1$). 0-20 is common | • Large number of positive and negative examples             |
| • Large number of negative examples ($y=0$)                  |                                                              |
| • Many different "types" of anomalies (i.e. there are many ways that an airplane engine can go wrong); future anomalies may look nothing like any of the anomalous examples we've seen so far. | • There are enough positive examples for the algorithm to get a sense of what positive examples are like, and future positive examples are likely to be similar to ones in the training set. |

#### Examples of application:

**Anomaly Detection**

* Fraud detection
* Manufacturing (e.g. aircraft engines)
* Monitoring machines in a data center

**Supervised Learning**

* Email spam classification
* Weather prediction 
* Cancer classification
