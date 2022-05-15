---
layout: post
title: "Playing with a MNIST digit recognizer"
description: "Reproducing MNIST digit recognizer. This is a basic project, just to get hands dirty in ML."
redirect_from:
  - /2022/02/09/
tags: notes
date: 22-02-09

---

**Q**: What is the use of step and backward functions ? <br>
**A**: backward() function calculates the gradients for all the tensors. step() function uses the value of these gradients to update the weights of the neural network. A detailed explanation can be found [here](https://stackoverflow.com/questions/53975717/pytorch-connection-between-loss-backward-and-optimizer-step)

**Q**: What does a max function do ?
**A**: Over a tensor, the above function reduces the tensor across a given dimension. Output is a tuple containing two tensors - first is the max value, second is the index of the max value.


---
**Referenced Blogs**
1. [Next Journal](https://nextjournal.com/gkoehler/pytorch-mnist)
