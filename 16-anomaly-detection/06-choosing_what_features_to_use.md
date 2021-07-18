---
Video: machine-learning/15_anomaly-detection/02_building-an-anomaly-detection-system/03_choosing-what-features-to-use.mp4
---

## Choosing What Features to Use

When applying anomaly detection, it turns out one of the things that has a huge effect on how well it works is the choice of features that are chosen and used.

### Normalizing Non-Gaussian Features

When using the anomaly detection algorithm we modeled the features using the Gaussian distribution to ensure that the data fit the bell curve.  So one thing you can do is to plot an histogram of the data (using the `hist` function in Octave) as a sanity check, to ensure that the data is Gaussian.

If the data does not look Gaussian when plotted in this way, though it will usually work okay, one might apply some transformations to see if it can be normalized (e.g. `log(x)` transform).  Though it will work either way you will get better results if you can get the data to fit a Gaussian distribution.

### Error Analysis for Anomaly Detection

An error analysis procedure, similar to one that is used with supervised learning, can be used to come up with features for an anomaly detection. In this, we'd run the algorithm on a cross-validation set, looking at what it gets wrong and seeing if there are additional features we can add to improve it on those errors.

When doing anomaly detection we want:

* $p(x)$ to be large for normal examples of $x$
* $p(x)$ to be small for anomalous examples of $x$

The most common issue we run into is that $p(x)$ is comparable for both normal and anomalous examples (e.g. both large).  The process of this is to look at the mistakes that are being made, and to understand what features distinguish that particular error such that we can then use that to improve $p(x)$.
