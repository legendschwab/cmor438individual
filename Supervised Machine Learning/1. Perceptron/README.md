The **perceptron** is the most fundamental supervised machine learning algorithm. Based on neural perceptrons in the human body, this algorithm takes in a set of inputs as a signal, outputs an intermediate value through a weighted linear combination, and then outputs a final value based on some activation function. The perceptron is the foundation for more complicated models like Neural Networks. Here is a picture that outlines a simple perceptron model:

![PerceptronModel](https://anasbrital98.github.io/assets/img/14/Perceptron.png)

The most common activation function is a simple step function that outputs -1 or 1 based on a threshold. For example, if the weighted sum is less than 0, the step function will return -1 and 1 otherwise.

The training of a perceptron model determines the set of weights that will minimize the cost function. The cost function is the sum of the difference between the predicted value of $\hat{y}_i$ and the actual value $y_i$ squared for all points in our training data set.

First, we start with a random initial guess for our weights $$w$$ as well as our bias $$b$$ (denoted as $$w_0$$ in the figure). Using this, we calculate the predicted value $$\hat{y}_i$$ for each $$x_i$$.

Then, we use an iterative method to improve our weights based on the error between the predicted and actual values of each $$y_i$$. 

$$
 w \gets w - \frac{1}{2} (\hat{y}_i - y_i) x_i
$$

$$
 b \gets b - \frac{1}{2} (\hat{y}_i - y_i)
$$

The idea here is that if $$\hat{y}_i$$ equals $$y_i$$, then we do not change our weights or bias. If the predicted value is $-1$ while the actual value is $1$, then we update $w \gets w + x_i$, which means that in future iterations, $w \cdot x_i + b$ will be more positive. This increases the chance that the prediction will be corrected to $1$. Similarly, if the predicted value is $1$ while the actual value is $-1$, we update $w \gets w - x_i$. In future iterations, $w \cdot x_i + b$ will be more negative, increasing the chance that the prediction will be $-1$.


In the following notebook, we will create a Perceptron class that will perform binary classification of the top 100 board games into those can be finished in an hour vs. those who cannot based on its average complexity level and rating.
