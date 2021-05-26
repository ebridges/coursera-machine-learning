---
Video: machine-learning/11_machine-learning-system-design/02_handling-skewed-data/01_error-metrics-for-skewed-classes.mp4
---

## Error Metrics for Skewed Classes

In the context of error evaluation and error metrics there's one case where it's particularly tricky to come up with an appropriate error metric for evaluating your learning algorithm known as "Skewed Classes."

Given a logistic regression model where we've learned that we get a 1% error on the test set (i.e. 99% correct diagnoses), this sounds great.  However, then we discover only 0.50% of patients in our test set actually have cancer, making that prediction not so great.

In that situation, imagine we have a function that always returns $0$ when predicting whether a given case is cancerous; using that method, we'd then have a 0.50% error rate.  Even better!

This setting, where the number of positive vs. negative cases in our test set is close to one of the extremes is known as "skewed classes" (e.g. number of positive classes is much much smaller than negative).  

The problem with using classification error/accuracy as an evaluation metric:  let's say we have a learning algorithm that's getting 99.2% accuracy, and we make a change to it that leads to 99.5% accuracy.  Is this improvement from something we did that was useful, or not? Or, is it now just predicting $0$ more often? 

Though having a single real number evaluation metric helps us to quickly decide if we made a good change to the algorithm or if that made an ineffective change, if you have very skewed classes in the data it becomes much harder to use just classification accuracy.  This is because we can get very high classification accuracies (or low errors) and it's not clear if doing so is really improving the quality of your classifier.

 When we're faced with skewed classes like this, we would want to come up with a different evaluation metric. One such metric is known as "precision/recall."

### Precision / Recall

Assume we have a classifier that predicts $y=1$ in the presence of a rare class that we want to detect:
$$
\begin{array}{c c|c}
% |c c|c| means that there are three columns in the table and
% a vertical bar ’|’ will be printed on the left and right borders,
% and between the second and the third columns.
% The letter ’c’ means the value will be centered within the column,
% letter ’l’, left-aligned, and ’r’, right-aligned.
Actual\ Class & Predicted\ Class & \\ % Use & to separate the columns
\hline % Put a horizontal line between the table header and the rest.
1 & 1 & True\ Positive\\
0 & 0 & True\ Negative\\
1 & 0 & False\ Negative\\
0 & 1 & False\ Positive \\
\end{array}
$$

#### Precision

Of all cases where we predicted $y=1$, what fraction is actually $y=1$?
$$
\frac{True\ positive}{Num\ predicted\ positive}=\frac{True\ positive}{True\ positive+False\ positive}
$$
Having a high precision is a good thing.

#### Recall

Of all cases that are actually $y=1$, what fraction did we correctly predict as $y=1$?
$$
\frac{True\ positive}{Num\ actual\ positive}=\frac{True\ positive}{True\ positive+False\ negative}
$$
Having a high recall is a good thing.

#### Convention

We normally set $y=1$ for the rare case.

