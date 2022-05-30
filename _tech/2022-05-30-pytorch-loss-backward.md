---
layout: post
title: "How does loss.backward() work in Pytorch ?"
description: ""
date: 22-05-30

---

For a long time, I didn't understand how does loss.backward() work. I referred to multiple blogs and SO questions, but somehow the underlying concept was always elusive. Following is a synthesis of various notes I have made over months in my pursuit to understand the functionality behind `loss.backward`.

### Code - Pseudo and non-Pseudo
1. Define a neural network. We'll use `net` to refer to the network.
2. Define a loss function, e.g. BCELoss. We'll use `criterion` to refer to the loss function object.
3. Feed your `input` to the `net` in order to retrieve `output`.
4. Use ground truth data - `label` - to calculate `loss`.
5. Use `optimiser.step()` to update the parameters of the neural network.
> net = Net()
> net.zero_grad()
> criterion = nn.BCELoss()
> output = net(input)
> loss = criterion(output, label)
> loss.backward()
> optimiser.step()

### What's happening under the hood ?
The neural net, `net`, can be thought of as a computational graph. In fact, if were to use `grad_fn` attribute of `loss`, then we can walkthrough the computation graph of the network. 

#### Calling loss.backward()
Now, when we call the `loss.backward()` function, entire graph, (i.e. all the layers which create the neural network, e.g. conv layer, liner layer, etc) is differentiated with respect to the loss; the value of loss being calculated earlier using criterion as shown above. 
These gradient values are stored in the `net` itself. Every tensor stores some info about how to calculate the gradient and the gradient itself. Remember, each layer in the `net` is a `tensor` itself. Hence, after `loss.backward()` has been called, each tensor (i.e. each layer) contains the gradient value for that tensor.

#### How does loss.backward() identify the network to be differentiated ?
The answer to this question is very obvious, but it was not visible to my eyes. I could have created just another object of `Net`, let's say `net2` below `net`.  How would Pytorch know which network object is to be differentiated ?
I didn't find an answer to the above question anywhere on the web. While experimenting (as suggested in the above paragraph), I realized that there must be some sort of reference mechanism involved which guides Pytorch to identify the network to be differentiated.

While calculating `loss`, we pass `output`  to `criterion`. Similarly, the `output` is calculated using `net`. So we can assume that `loss` has some kind of a reference to `net`, and not to `net2`. When we call `loss.backward()`, Pytorch knows that `net` has to be differentiated, not `net2`.

#### Calling optimiser.step()
Calling `optimiser.step()` subtracts the value of gradients from the original params values. This step is basically updating the value of the params based on the gradients obtained. The gradients are in turn obtained by how well the network fits the output (calculated by the `criterion`) 

#### How does optimiser know which net object to operate upon ?
`optimizer` object knows this because we tell that to the `optimizer` while intializing the object. Remember, we pass `net.parameters()` as one of the arguments while initializing `optimizer`. 

#### Calling net.zero_grad()
As mentioned above, after calling `loss.backward()`, the gradients are stored in the tensors of `net` object. However, while looping over the data, we don't want the gradients of previous loop to influence the params in the current loop. Hence, it is required to zero the gradients. `net.zero_grad()` helps us remove all the gradients of the network.

Another reason to call `net.zero_grad()` is to free up memory. If we don't call `zero_grad()`, the tensor(s) of `net` will store the values of gradients accumulated over various loops thereby using a lot of memory. This scenario can cause exhaustion of available memory and abrubpt termination of the program. 

---
**References**
1. [Neural Networks](http://seba1511.net/tutorials/beginner/blitz/neural_networks_tutorial.html#neural-networks "Permalink to this headline")]
2. [Connection between loss.backward() and optimizer.step()](https://stackoverflow.com/questions/53975717/pytorch-connection-between-loss-backward-and-optimizer-step)
3. 