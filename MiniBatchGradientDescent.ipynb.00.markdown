## Background

During large-scale date training, the order of magnitude of data can reach millions. If a parameter is acquired via the computation of the whole training set, the update speed will be too slow. To solve this problem, a common used method is [Mini-Batch Gradient Descent](https://en.wikipedia.org/wiki/Stochastic_gradient_descent) which computes mini-batche data in the training set, resulting faster training parameters in a neural network.

In this article, we will first define a softmax classifier, then use the training set of [CIFAR10](https://www.cs.toronto.edu/~kriz/cifar.html) to train this neural network, and finally use the test set to verify the accuracy of the neural network. The difference is that we will use Mini-Batch Gradient Descent, thus the accuracy of the neural network can reach 40%.
