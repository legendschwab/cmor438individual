**Logistic Regression** is a regression model that builds upon linear regression by outputting a probability value between 0 and 1. Similar to linear regression, it takes in a set of inputs and applies a linear combination of them. However, this output value is then transformed into a probability value using an exponential function. It is similar to the perceptron model except an exponential function is used for the activation function.

Here is the model:

$$
f(x\mid \boldsymbol{\beta}) = P(y = 1 \mid \mathbf{x}) = \frac{1}{1 + e^{-\mathbf{x}^\top \boldsymbol{\beta}}}
$$

We estimate the value of $\boldsymbol{\beta}$ by Maximum Liklihood Estimation.

![photo](https://images.spiceworks.com/wp-content/uploads/2022/04/11040521/46-4-e1715636469361.png)

*Credits: Spice Works* 

Logistic regression can be used for binary classification tasks where the predicted probability represents the probability that an object belongs in one classification over the other. Since logistic regression is based on a linear combination of inputs, it works best for data that is linearly separable.

In the following notebook, we will retry the classification of board games as short games (finish less than 1 hour) and long games (finish in longer than 1 hour) based on complexity and and rating.

 

