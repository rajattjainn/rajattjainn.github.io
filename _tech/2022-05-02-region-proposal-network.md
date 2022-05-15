---
layout: blog
title: "Region Proposal Network"
description: ""
redirect_from:
  - /2022/05/02/

---

## Region Proposal Network

RPN or Region Proposal Network was first introduced as a part of Faster R-CNN architecture. The main objective of RPN network is to propose regions which might have object(s) that needs to be detected.

### Architecture
<br>

![RPN Architecture](/assets/imgs/rpn_archi.png "Credits: Code With Aarohi") <br>
<br>
In the image above, the block in dotted square represents a RPN network.
<br> <br>
The input image is fed to a convnet which serves as the backbone of RPN. The authors of [Faster R-CNN paper](http://papers.nips.cc/paper/5638-faster-r-cnn-towards-real-time-object-detection-with-region-proposal-networks.pdf) paper used VGG16. However, it is the prerogative of the programmer to use any convnet they want to use. It should be noted that in Faster R-CNN, only the convolutional layers of VGG16 were used, i.e. the Fully Connected layers were removed while using the network as a part of RPN. <br> <br>
The output of the convnet is fed to two different convolutional neural networks, both serving different purposes:

1. One network is a 1x1x(9*2) conv layer. This serves as a classifier network, i.e. it tells whether the region has an object or not.
2. Another network is 1x1x(9*4) conv layer. This is a regressor network - it predicts the offsets for 4 values of the bounding box. The 4 values are x, y, w, and h. 

### How does the RPN work ?
The convnet helps in extracting feature from the image.


TODO <br>
1. Role of anchors ? 
2. Foreground and Background
3. Why 9*2 ?
4. IoU at which stage ? 
5. 

### Training RPN

### Loss Function

### Why RPN ?

### How is this different from YOLO ?
<br>

**References**

1. [3 Region Proposal Network](https://www.youtube.com/watch?v=if1tzf1p0gA)
2. [Region Proposal Network (RPN) architecture explained](https://towardsmachinelearning.org/region-proposal-network/)
3. [Region Proposal Network — A detailed view](https://towardsdatascience.com/region-proposal-network-a-detailed-view-1305c7875853)
4. [Faster R-CNN Explained for Object Detection Tasks](https://blog.paperspace.com/faster-r-cnn-explained-object-detection/)