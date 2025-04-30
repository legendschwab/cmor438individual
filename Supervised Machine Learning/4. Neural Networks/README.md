**Neural Networks** is a multi-layer representation of the perceptron model. It is a supervised machine learning that can perform both regression and classification tasks.

![photo](https://www.qtravel.ai/wp-content/uploads/2023/07/sieci-neuronowe-grafika-1024x759.png)

*Credits: Qtravel*

Each node takes in a set of inputs and outputs a value based on an activation function similar to the perceptron model. However, there are hidden intermediate layers. Each layer has its own set of weights and bias values. Outputs from one layer are then fed into the next layer. We keep repeating until we get the final output. By using these hidden layers, we are able to model non-linear models.

We have a set of weights for each layer to the next, which is represented by a weights matrix $W^{l}$. Each layer's prediction $a^{l}$ is given by:

$a^{l} = \sigma\left(W^{l} a^{l-1} + b^{l}\right) \text{for } l = 1, 2, \dots, L$ 
where $\sigma$ gives the activation function.

We use a training process called **back propagation** to solve for the optimal weights and biases at each layer. It is essentially a multi-layer algorithm similar to the iterative process for the perceptron model. The general intuition is to calculate the error at each layer and propagate it backwards to update the weights/bias at each layer. The updating scheme is based on the **gradient descent** algorithm, where we calculate the gradient of the cost function at each layer to find the direction of steepest descent. This allows us to minimize error at each layer.

Neural Networks is a very powerful machine learning algorithm as it can model more complex situations. However, it can be prone to overfitting and is computationally taxing to implement. In the following notebook, we will apply Neural Networks to classify board games (once again) as games that take a long time and those that do not take a long time. 
