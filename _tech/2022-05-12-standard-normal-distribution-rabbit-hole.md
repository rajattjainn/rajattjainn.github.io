---
layout: post
title: "Standard Normal Distribution Rabbit Hole"
description: ""
date: 22-05-12

---

### Progression(s)

- 'Standard Normal Distribution' --> 'Normal Distribution' --> 'Variance and Standard Deviation'
- 'Normal Distribution' --> 'Probability Distribution' (or) 'Distribution'

### Making Sense of the Jargon

1. **Standard Normal Distribution (SND)** is a type of 'Normal Distribution' (ND). If in a ND, the mean is 0, and the standard deviation is 1, then the type of distribution is a SND.

2. **Normal Distribution (ND)** is a probability distribution that is symmetric about the mean. Also, and equally importantly, the data occurence is more frequent around the mean than data far away from the mean. In other words, you'll find more data around the mean than away from the mean. Normal distribution is also known as **Gaussian Distribution**.
	- **Example:** If the final year results of a class follow a normal distribution with an average percentage of 60%, and standard deviation of 10% (i.e. a mean of 0.6, and SD of 0.1), we can say that 68.26% of students have percentages between 50% to 70%.

	![Normal Distribution](/assets/imgs/normal_distribution.png) 


3. **Probability Distribution** is a stasticial function that describes all the possible values and likelihood (probability) that a random variable can take within a given range. In other words, it is a function that shows the possible value for a variable and how often they occur. 

4. **Variance(σ2)** is the average of squared differences from the Mean.
	- Find the mean.
	- For each value, subtract the mean and square the value.
	- Work out the average of the squared differences.

5. **Standard Deviation (σ)** is the square root of the Variance. Standard Deviation is a measure of how spread the numbers are. After calculating SD, we can tell which values are in 1 SD of the mean, which in 2 SD of the mean, and so on.

![Standard Deviation](/assets/imgs/standard_deviation.svg)


### Building Bottom Up

From the above definitions, we can say that a standard normal distribution is a function to output numbers on the number line. Taking any random output from this function, the probability that
- it'll lie between -1 and 1 is 68.26% 
- it'll lie between -2 and 2 is 95.44%
- it'll lie between -3 and 3 is 99.72%




