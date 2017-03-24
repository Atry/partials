## Background

To improve the prediction accuracy, we need to use multi-layer neural network, because generally, the more the layers of a network, the higher the capability of the network. That is because the more the parameters, the more the state information represented, and the stronger the expression capability will be. Multi-layer neural network can tackle with more complex problems.

In this article, we will first define a simple neural network, and then use the training set of [CIFAR10](https://www.cs.toronto.edu/~kriz/cifar.html) to train this neural network. Finally, we will use a test set to verify the accuracy of the neural network, and the final accuracy can reach 51%.