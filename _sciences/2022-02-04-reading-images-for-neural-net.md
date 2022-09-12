---
layout: post
title: "Reading Images for Neural Net"
description: ""
date: 22-02-04

---

**Q**: What does a transform do ? <br>
**A**: Changing the properties of an image by using some mathematical operations. For example, one might want to shrink the size of the image. In that case, we would use resize transformation. We can perform a number of operations using transformations. 

---

**Q**: What should be the order of transform ? First Resize and then ToTensor() or first ToTensor() and then Resize () ? <br>
**A**: The answer to this question would be quite complex as explained [here](https://docs.microsoft.com/en-us/dotnet/desktop/winforms/advanced/why-transformation-order-is-significant?view=netframeworkdesktop-4.8#:~:text=The%20order%20of%20the%20composite,%2C%20then%20rotate%2C%20then%20translate).<br>

The other reason why the order of transformation must be important is about the processing time it takes. For example if one resize the image first, and then performs another transformation (let's say colorjitter) vs peforming colorjitter first and then resize. In both the cases, the time taken to complete the operation would be different. <span style="color:#ff726f">[This is my guess right now, haven't tested this theory.] </span>

However, the order of transformation ultimately does not have any effect over the memory your object will end up taking.

---

**Q**: Why is an image converted into a numpy array after being transformed ?

> img = transform(img).numpy().astype('float32')

**A**:

---

**Q**: Why image converted ? 
>    img = img.clone().cpu().numpy()<br>
>    img = img.transpose(1,2,0)<br>
>    std = [0.5,0.5,0.5]<br>
>    mean = [0.5,0.5,0.5]<br>
>    img = img*std + mean<br>

**A**

---

**Observation 01**: Looking at one of the solutions posted on Kaggle, I realised that the reason why my [code](https://github.com/rajattjainn/learnML/blob/main/CatsVsDogs/main.py#L51) has been taking so much time to load the input data is because I tried to [read](https://github.com/rajattjainn/learnML/blob/main/CatsVsDogs/image_utils.py#L13) all the files in the init function of custom dataset class. This resulted in transforming the data at the run time instead of the time when data is supposed to be retrieved. The ideal place to have these functions defined is the __getitem__() function, as done [here](https://github.com/rajattjainn/learnML/blob/main/CatsVsDogs/image_utils.py#L39).