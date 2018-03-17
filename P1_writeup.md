# **Finding Lane Lines on the Road**

## Writeup

---

**Finding Lane Lines on the Road**

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[gray_image]: ./test_images_output/gray-solidWhiteCurve.jpg "Grayscale Image"
[canny_image]: ./test_images_output/canny-solidWhiteCurve.jpg "Canny-transformed Image"

---

### Reflection

### 1. Pipeline

My pipeline consists of 5 steps.

First, I convert the images to grayscale:

![Grayscale Image][gray_image]

Then, I applied Canny transform to the grayscale image:

![Canny-transformed Image][canny_image]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...


### 2. Potential shortcomings with my current pipeline


One potential shortcoming would be what would happen when ...

Another shortcoming could be ...


### 3. Possible improvements to my pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
