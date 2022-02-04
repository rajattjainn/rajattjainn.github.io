---
layout: blog
title: "Reading Images for Neural Net"
description: ""
redirect_from:
  - /2022/02/04/

---

**Q**: What does a transform do ? <br>
**A**: Changing the properties of an image by using some mathematical operations. For example, one might want to shrink the size of the image. In that case, we would use resize transformation. We can perform a number of operations using transformations. 

---

**Q**: What should be the order of transform ? First Resize and then ToTensor() or first ToTensor() and then Resize () ? <br>
**A**: The answer to this question would be quite complex as explained [here](https://docs.microsoft.com/en-us/dotnet/desktop/winforms/advanced/why-transformation-order-is-significant?view=netframeworkdesktop-4.8#:~:text=The%20order%20of%20the%20composite,%2C%20then%20rotate%2C%20then%20translate).<br>

The other reason why the order of transformation must be important is about the processing time it takes. For example if one resize the image first, and then performs another transformation (let's say colorjitter) vs peforming colorjitter first and then resize. In both the cases, the time taken to complete the operation would be different. [This is my guess right now, haven't tested this theory.]

However, the order of transformatin ultimately does not have any effect over the memory your object will end up taking.

---

**Q**: Why is an image after being transformed is converted into a numpy array ? 

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
