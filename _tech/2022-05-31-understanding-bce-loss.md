---
layout: post
title: "Understanding BCE Loss"
description: ""
date: 22-05-31

---
### Introduction
BCE stands for Binary Cross Entropy. As the name suggestes, BCE Loss is used during binary classification. This is not to say that other loss functions cannot be used, but BCE Loss is almost ubiquitous.

### Mathematical Formula and Explanation
The BCE Loss formula is given as: <br>
![BCE Loss Formula](assets/imgs/bce_loss.png)

There are two outputs in a binary classification: the event when the output is predicted to be y<sub>i</sub>, and when the output is predicted NOT y<sub>i</sub>, i.e. (1-y<sub>i</sub>). In the above expression, $\hat{y}$ <sub>i</sub> is the probability that the outcome of the experiment is y<sub>i</sub>. Similarly, (1 - $\hat{y}$) is the probability that the event is not y<sub>i</sub>.<br>
### Implementing BCE Loss
Let's say that our training set is a bunch of numbers (features) having a label (green or red). The training set is shown below:

![BCE Implementation Training Set](/assets/imgs/bce_imp_train_set.png)
Our classification problem is: given a feature x, predict whether it's label is green or not (i.e. the label is red). <br> <br>
Let's say we train a function on the above dataset depicted in the following figure.

![BCE Implementation Trained Function](/assets/imgs/bce_imp_train_func.png)

Now, while calculating the loss of the trained function, we replace the values of $\hat{y}$(s) and y<sub>i</sub>(s) in the above loss function; y<sub>i</sub>(s) coming from the training data (1 when the label is green and 0 when the label is not, i.e. the label is red), and $\hat{y}$(s) being the output of the learned function.

---

**References:**
1. [Understanding binary cross-entroy/log loss](https://towardsdatascience.com/understanding-binary-cross-entropy-log-loss-a-visual-explanation-a3ac6025181a)
2. [Why use Binary Cross Entropy for Generator in Adversarial Networks](https://stats.stackexchange.com/questions/242907/why-use-binary-cross-entropy-for-generator-in-adversarial-networks)


**Further Reading:**
1. [Visual Information Theory](http://colah.github.io/posts/2015-09-Visual-Information/)
2. [Conditional Probability](https://www.probabilitycourse.com/chapter1/1_4_0_conditional_probability.php)
3. [Should I use a categorical cross-entropy or binary cross-entropy loss for binary predictions?](https://stats.stackexchange.com/questions/260505/should-i-use-a-categorical-cross-entropy-or-binary-cross-entropy-loss-for-binary)
