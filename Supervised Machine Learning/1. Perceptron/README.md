The **perceptron** is the most fundamental supervised machine learning algorithm. Based on neural perceptrons in the human body, this algorithm takes in a set of inputs as a signal, outputs an intermediate value through a weighted linear combination, and then outputs a final value based on some activation function. 

![PerceptronModel](https://anasbrital98.github.io/assets/img/14/Perceptron.png)

The most comomon activation function is a simple step function that outputs -1 or 1 based on a threshold. For example, if the weighted sum is less than 0, the step function will return -1 and 1 otherwise.

The training of a perceptron model determines the set of weights that will minimize the cost function. First, we start with a random initial guess for our weights $$w$$ as well as our bias $$b$$ (denoted as $$w_0$$ in the figure). Using this, we calculate the predicted value $$\hat{y}_i$$ for each $$x_i$$.

Then, we use an iterative method to improve our weights based on the error between the predicted and actual values of each $$y_i$$. 

$$
 w \gets w - \frac{1}{2} (\hat{y}_i - y_i) x_i
$$

$$
 b \gets b - \frac{1}{2} (\hat{y}_i - y_i)
$$

In the following notebook, we will create a Perceptron class that will perform binary classification of roller coasters into Wooden or Steel roller coasters based on their max height, top speed, and number of inversions.
