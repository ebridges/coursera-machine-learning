## Regularization Intuition & Cost Function [^32]

If we have smaller values for the parameters, we end up with a simpler hypothesis, and are less prone to overfitting. In other words, if we find that we have overfit the model from our hypothesis function, we can minimize the weight of some of the terms in our function by increasing their cost.

Example, say we have a function: $\theta_0 + \theta_1x + \theta_2x^2 + \theta_3x^3 + \theta_4x^4$, and we want to make it more quadratic because it overfits the model.

To do so, we want to reduce the influence of the terms $\theta_3x^3$ and $\theta_4x^4$ without actually getting rid of them or changing the form of our hypothesis.  We do this by modifying the cost function; by adding two additional terms that inflate the cost of $\theta_3$ and $\theta_4$ it forces smaller inputs for those values, thus reforming the curve to be more quadratic.

To restate this intuition, if we have smaller values for the parameters $\theta_0,\theta_1,…,\theta_n$, then our hypothesis is "simpler" and is less prone to overfitting.

There could be a circumstance where we have many parameters, but we don't know which ones are more important than the others. In a situation like that, we could also regularize all of our theta parameters in a single summation as:
$$
min_{\theta }\frac{1}{2m} \sum^{m}_{i=1} (h_{\theta }(x^{(i)})-y^{(i)})^{2}+\lambda \sum^{n}_{j=1} \theta^2_j
$$
The $\lambda$ value is the **regularization parameter**. It determines how much the costs of our theta parameters are inflated. It controls a tradeoff between two goals: we want to fit the trading data, but we also want to keep the parameters small (keeping the hypothesis simple and avoiding overfitting).  

Using the above cost function with the extra summation, we can smooth the output of our hypothesis function to reduce overfitting. If lambda is chosen to be too large, it may smooth out the function too much and cause underfitting. 

If we provide a value for $\lambda$ that is too large, we end up eliminating the influence of all terms in the cost function, and underfitting the data.