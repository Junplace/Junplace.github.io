Minimize the Loss function would be one of the basic steps in Deep Learning. The Loss function consists of weight and bias, which is updated to find out the global minimum. So, we should do the derivative and be cautious not to be stuck in the local minimum that is different to the global one. A bunch of algorithms have been developed to deal with the issue, and here, we will see how parameters are calculated in the back-propagation process using the standard gradient descent.

1. Forward-Propagation

Literally, forward-propagation is to calculate sequentially. After combining Input data with weight and bias linearly, some values come out through activation function on it.

Graph

Equation

We can define the Loss function with an estimate y made in this way. Here is the most common loss function, MSE:

Equation

2. How to work on

Looking closely at the equation above, there are some parameters and an activation function in that equation, and therefore the Chain Rule is required to do math. It means that we serially do derivative from the closest layer to the output layer. For instance, let us differentiate the loss function with respect to w_5,

Equation

The Back-propagation algorithm is to repeat this process until finding the global minimum of the loss function

3. Limits to Back-propagation

To sum up, the goal of this learning is to compute w and b that minimize the loss function with the back-propagation algorithm, which could bring about situations where the result would vary depending on initial value and activation function. Plus, we have to have a solid assumption that the loss function gets the global minimum.

Vanishing gradient, one of the big problems in the back-propagation, indicates that the output error of the neural network may not be reflected, as the layer is away from the output layer. That is, the forward weight would not be remarkably updated since the error would have a little impact on computation in the forward layer. I recommend putting simple numbers into the equation above and observing any slight change so that you can feel what vanishing gradient really means.

To deal with this complication, many activation functions have evolved, and ReLU (Rectified Linear Unit) is currently used the most.

