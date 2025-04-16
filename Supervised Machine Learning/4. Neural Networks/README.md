**Neural Networks** is a multi-layer representation of the perceptron model. 

![photo](https://www.qtravel.ai/wp-content/uploads/2023/07/sieci-neuronowe-grafika-1024x759.png)

*Credits: Qtravel*

Each node takes in a set of inputs and outputs a value based on an activation function similar to the perceptron model. However, there are hidden intermediate layers. Each layer has its own set of weights and bias values. Outputs from one layer are then fed into the next layer. We keep repeating until the final output. By using these hidden layers, we are able to model non-linear models.

We have a set of weights for each layer to the next, which is represented by a weights matrix $W^{l}$. Each layer's prediction $a^{l}$ is given by:

$a^{l} = \sigma\left(W^{l} a^{l-1} + b^{l}\right) \text{for } l = 1, 2, \dots, L$ 

We use a training process called **back propagation** to solve for the optimal weights and biases at each layer. It is essentially a multi-layer algorithm similar to the iterative process for perceptron. The general intuition is to calculate the error at each layer and propagate it backwards to update the weights/bias at each layer. The updating scheme is based on the **gradient descent** algorithm, where we calculate the gradient of the cost function at each layer to find the direction of steepest descent. This allows us to minimize error at each layer.




