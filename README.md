# scratch-neural-net
A library for creating deep neural nets in pure python/numpy

This is a set of functions for building N-Layer neural nets for binary classification in python using numpy. Compared to modern frameworks like Tensorflow, MXNet, etc... it is considerably slower and should not be used in a production application, however it can be useful for debuging deep learning architectures due to functions being evaluated imperatively instead of building a static (black-box) computation graph like Tensorflow.

I created this after completing the deep learning courses from deeplearning.ai, to implement and more fully understand the concepts of deep neural nets by creating them from scrath.

## Usage:
To use call the function 
~~~~
L_layer_model(X, Y, layers_dims, learning_rate = 0.0075, num_iterations = 3000, print_cost=False)
~~~~
Passing in a NxM array for X where
* N = number of examples
* M = number of features (pixels in a flat image)

Pass a binary ground-truth vector for Y indicating 1 as positive and 0 as negative.

Pass a list of scalars for layer_dims where the initial value corresponds to your input dimension, subsequent values will create additional hidden layers with the number of neurons in that layer equal to the value. eg: [784,100,10] for a network to compute a 28x28 image with a two layer network consisting of a hundred hidden units then ten hidden units.

Learning rate and the number of iterations (epochs) can be tuned based on results. Setting print_cost to True will give a readout of the training cost at the end of each iteration so you can check that it is monotonically decreasing (gradient decsent is proceeding effectively).
