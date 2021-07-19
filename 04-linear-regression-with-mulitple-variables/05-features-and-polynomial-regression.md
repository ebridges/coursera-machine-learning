## Features & Polynomial Regression [^20]

We can improve our features and the form of our hypothesis function in a couple different ways. Later on we'll explore algorithms to automatically determine what features to use, and what kind of functions (cubed, quadratic, etc.) to apply to the data, this is just to introduce these as possibilities.

### Features

We can combine multiple features into one. For example we can combine $x_1$ and $x_2$ into a new feature $x_3$ by taking $x_1 \cdot x_2 $.  The choice of features that you have and how you can get different learning algorithms, sometimes very powerful ones by choosing appropriate features.

Here he provides an example related to selling a house.  You may have two features  _frontage_ and _depth_ in your hypothesis: $h_\theta(x)=\theta_0+\theta_1\times frontage+\theta_2\times depth$.  You can greatly simplify the model by assuming that $area=frontage\times depth$ and so the hypothesis becomes $h_\theta(x)=\theta_0+\theta_1\times area$.



### Polynomial Regression

Our hypothesis function does not need to be linear (i.e. a straight line) if that does ot fit the data well.  We can change the behavior or _curve_ of the hypothesis function by making it a quadratic, cubic or a square root function (indeed, any other form).

An important thing to note is if you choose your features this way then feature scaling becomes very important.
