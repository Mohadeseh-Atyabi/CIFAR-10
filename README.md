# CIFAR-10

One of the applications of neural networks is classification. In this project, we are going to categorize images. We want to use different neural networks (specifically fully connected networks) to build a model that takes photos as input and recognizes the category of each photo.

## Problem description
In this problem, we want to classify CIFAR-10 dataset images. This dataset is a smaller version of the CIFAR-100 dataset, which is limited to images from 10 different categories. You can see the categories of images of this dataset in the figure below.

![cifar10](https://user-images.githubusercontent.com/72689599/178667359-fcb52b54-48c4-4de3-8c7c-729a9beab1cf.png)

The dimensions of the images in this dataset are equal to 32 (length) by 32 (width) by 3 (RGB color channels). Here, we first need to convert color images to grayscale, i.e. consisting of only one channel, in a pre-processing step. After this step, we will have 32x32 images. As a result, the input layer of the network has 32x32=1024 neurons, each neuron shows the brightness of a pixel as an int number from 0 to 255.

Here, to reduce the computational volume, we only use the images of the first 4 classes of this dataset. As a result, our output layer will contain 4 neurons. The neuron with the highest activation value is selected as the category detected by our model. For this neural network, we consider two hidden layers, each of which has 16 neurons.
So the structure of our neural network will be as follows:

![image](https://user-images.githubusercontent.com/72689599/178670675-7c8970c9-14ae-49b6-a154-4797a30991b7.png)


## Feedforward
To calculate the output from the input in neural networks, the following operations are performed in each layer.

![image](https://user-images.githubusercontent.com/72689599/178672388-ebacb3ac-036f-4972-9914-e021492a66d1.png)

As a result, in the implementation of the neural network, for the weights between both layers, we consider a k by n matrix, where k is the number of neurons in the next layer and n is the number of neurons in the current layer. As a result of each row of W matrix, the weights are related to a specific neuron in the next layer. Also, for the biases between both layers, a separate vector is considered whose dimensions are equal to the number of neurons in the next layer.

![image](https://user-images.githubusercontent.com/72689599/178672666-f434a41e-df6e-41f2-b5fe-aad9aa717f82.png)

## Backpropagation
As you know, the neural network learning process means minimizing the cost function:

![image](https://user-images.githubusercontent.com/72689599/178953723-dbe397f4-bea4-43b6-878c-014e2e7cbf30.png)

This work is done with the help of Descent Gradient method, in which we make the desired changes on the parameters by obtaining partial variances of the Cost function with respect to all parameters:

![image](https://user-images.githubusercontent.com/72689599/178953796-b6a1d505-5693-4495-b659-bd5525ef83e9.png)

Consider the hyperparameters as follows: the size_batch value is equal to 16, the learning coefficient is equal to 0.3, and the number of epochs is equal to 10. At the end of this step, report the accuracy of the model and the execution time of the learning process for the same 200 data. Considering that the number of epochs and training data are small, it is expected that at the end of the learning process, the accuracy of the model in this case is about 30% on average.

