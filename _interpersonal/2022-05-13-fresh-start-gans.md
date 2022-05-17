---
layout: post
title: "Making a Fresh Start, with GANs"
description: ""

---



**Thought Process** I have been playing with YOLO - the first algorithm I tried to learn in my CV journey - for more than a month now. While writing the code for Object Detection, I followed one blog. After reproducing the results, I thought of training the algorithm for a different set of classes - use transfer learning for different dataset.
For that, I tried following another blog. But as two different authors wrote the blog (and the underlying code by extension), it was difficult (not impossible) to reconcile the two objectives in same code base. At the same time, I am also tired of YOLO algorithm. There are also a few mistakes I did while reproducing the code-base and I would like to make it better, fixing my mistakes.

After contemplating for some time, I decided to rewrite the algorithm after taking a pause of some days. I am aware of the fact that this is not the ideal way to work - once I start working, I won't have this freedom to rewrite the code and would have to reconcile incoming code as per the existing code base's requirements. However, sometimes it's important to make a fresh start.
I am taking a pause from Object Detection right now - will start with GANs and would come back to Object Detection after finishing this project. Moving forward with GANs, I'll be following a more structured approach.


Template: 
- Follow only one blog to begin with. Too many approaches make a mess if you don't know the basics. 
- Understand the underlying concepts in detail before moving to the code. 
- Read the Paper
- Have a rough architecture in mind before starting to code. Keep in mind that you have to write code for training as well
	- Plan the code with CUDA enabled
	- Have training and evaluation graphs to publish
	- Visualize test data
	- Image Augmentation
	- different optimizers
	- change the size of input noise
- No shortcuts
- Daily, regular entries in Tech Blog

