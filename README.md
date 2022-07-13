# CIFAR-10

One of the applications of neural networks is classification. In this project, we are going to categorize images. We want to use different neural networks (specifically fully connected networks) to build a model that takes photos as input and recognizes the category of each photo.

## Problem description
In this problem, we want to classify CIFAR-10 dataset images. This dataset is a smaller version of the CIFAR-100 dataset, which is limited to images from 10 different categories. You can see the categories of images of this dataset in the figure below.

![cifar10](https://user-images.githubusercontent.com/72689599/178667359-fcb52b54-48c4-4de3-8c7c-729a9beab1cf.png)

The dimensions of the images in this dataset are equal to 32 (length) by 32 (width) by 3 (RGB color channels).

![image](https://user-images.githubusercontent.com/72689599/178669613-02c3facd-b844-4065-96c7-4fd0ce615f2b.png)

Here, we first need to convert color images to grayscale, i.e. consisting of only one channel, in a pre-processing step. After this step, we will have 32x32 images. As a result, the input layer of the network has 32x32=1024 neurons, each neuron shows the brightness of a pixel as an int number from 0 to 255.

Here, to reduce the computational volume, we only use the images of the first 4 classes of this dataset. As a result, our output layer will contain 4 neurons. The neuron with the highest activation value is selected as the category detected by our model. For this neural network, we consider two hidden layers, each of which has 16 neurons.
So the structure of our neural network will be as follows:

![image](https://user-images.githubusercontent.com/72689599/178670675-7c8970c9-14ae-49b6-a154-4797a30991b7.png)


