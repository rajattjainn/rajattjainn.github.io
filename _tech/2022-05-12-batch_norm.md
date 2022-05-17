---
layout: post
title: "Understanding Batch Normalisation"
description: ""
date: 22-05-12

---

**Normalsation:** Normalization is a method that converts any data into one having similar scale (across varioius dimensions) and having a similar distribution. There are various ways of normalization, z-score normalization being one of the most widely used. Also known as standardization and a lot of times just reffered to as normalization, this is attained by subtracting the mean from all data points and dividing each data point by the standard deviation.
![Normalization](/assets/imgs/normalization.png)

### Batch Normalization
While training a neural network, the input to this network, i.e. the train dataset, is constant. However, as we move forward in training, over the course of various epochs and iterations, the parameters of the networks keep changing. This is because over each iteration, the optimizer changes the values of the parameters depending upon the loss in that iteration.

Now imagine a neural network having 5 layers, and consider the third layer. The input to this layer, i.e. the output of 2nd layer keep changing throughout. This ever-changing input makes it difficult for the network to train the parameters.<br>
A solution to the above problem is have a batch normalization layer before every activation layer in the neural network. This batch normalization layer stabilises the ever changing distribution of every layer's output.


--- 
**References::**
1. [Normalizing Inputs](https://www.youtube.com/watch?v=FDCfw-YqWTE)
2. [Normalizing Activations in a Network](https://www.youtube.com/watch?v=tNIpEZLv_eg)
3. [Fitting Batch Norm Into Neural Networks](https://www.youtube.com/watch?v=em6dfRxYkYU)
4. [How does Batch Normalization Help Optimization](https://www.youtube.com/watch?v=EvAVCxZJN2U)
5. [Data Normalization in ML](https://towardsdatascience.com/data-normalization-in-machine-learning-395fdec69d02)