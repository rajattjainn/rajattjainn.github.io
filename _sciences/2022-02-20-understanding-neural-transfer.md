---
layout: post
title: "Understanding Neural Transfer"
description: "Learnings while reproducing an open source code-base corresponding to Neural Transfer"
date: 22-02-20

---

[Motivation for this blog](#motivation)

### Reference Online Repo - [Neural Style Transfer] (https://github.com/gordicaleksa/pytorch-neural-style-transfer)


1. **Style Content**: The "Style" (or texture) of the image is not *captured* in only one layer, but is *sprinkled* across various layers in the network. It has been found that unlike "Content", "Style" of an image can be *measured* by calculating the correlation of neurons between different channels in the same layer. As style is spread across multiple layers, you do this by capturing correlation across multiple layers.<br>
One way to measure (and hence also capture) the correlation between various layers is by using a Gram Matrix. That's why, a weighted sum of Gram Matrices (from 4-5 layers) is used to measure the loss while understanding the difference between style of two images. <br>
A detailed explanation behind the how and why of Gram Matrices can be found [here](https://gcamp6f.com/2017/12/05/understanding-style-transfer/).



#### Motivation
I have been away from regular coding for almost 4 years now. Owing to this huge gap, I found it difficult starting again even after reading someone elses's code. Hence, for for next 4 weeks (i.e. until March 21, 2022), I'll be reading various code-bases and try solving the said problems by myself. During this time, if I hit a road-block, I'll be going back to the code-base and understand how exactly the author went around that particular problem.

While going through one of such online repos, I also realized going into rabbit holes is a must in order to understand what exactly is happening. I have decided to start takings *notes* during such rabbit holes. This will help me retain the knowledge and also make myself more accountable.


