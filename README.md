# BrainImage-Segmentation
Brain Image Extraction using Convolutional Neural Networks

The architecture was inspired by [U-Net: Convolutional Networks for Biomedical Image Segmentation](http://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/).

---

## Overview

### Data augmentation

The data for training contains 150 256*256*3 images, which are far not enough to feed a deep learning neural network. I use a module called ImageDataGenerator in keras.preprocessing.image to do data augmentation.



### Model

![img/u-net-architecture.png](img/u-net-architecture.png)

This deep neural network is implemented with Keras functional API, which makes it extremely easy to experiment with different interesting architectures.

Output from the network is a 256*256 which represents mask that should be learned. Sigmoid activation function
makes sure that mask pixels are in \[0, 1\] range.

### Training

The model is trained for 5 epochs.

After 5 epochs, calculated accuracy is about 0.97.

Loss function for the training is basically just a binary crossentropy.


---


### Dependencies

* Tensorflow
* Keras >= 1.0


### Results

Use the trained model to do segmentation on test images, the result is statisfactory.

![img/29.png](img/29.png)

![img/29_predict.png](img/29.png)



