# **Finding Lane Lines on the Road**

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[gray_image]: ./test_images_output/gray-solidWhiteCurve.jpg "Grayscale Image"
[blur_image]: ./test_images_output/blur-solidWhiteCurve.jpg "Blurred Image"
[canny_image]: ./test_images_output/canny-solidWhiteCurve.jpg
  "Canny-transformed Image"
[masked_image]: ./test_images_output/masked-solidWhiteCurve.jpg "Masked Image"
[hough_image]: ./test_images_output/hough-solidWhiteCurve.jpg
  "Hough-transformed Image"
[weighted_image]: ./test_images_output/weighted-solidWhiteCurve.jpg
  "Weighted Image"
[out_image]: ./test_images_output/out-solidWhiteCurve.jpg "Final Output Image"

---

## Reflection

### 1. Pipeline

My pipeline consists of 7 steps.

First, I convert the images to grayscale:

![Grayscale Image][gray_image]

<img src="./examples/grayscale.jpg" width="480">

Then, I apply Gaussian Blur to the grayscale image to smooth out edges:

![Blurred Image][blur_image]

Then, I apply Canny transform to the blurred grayscale image:

![Canny-transformed Image][canny_image]

Then, I mask all but the region of interest in the image:

![Masked Image][masked_image]

Then, I detect lines using hough transform:

![Hough-transformed Image][hough_image]

Then, I overlay the hough lines with original image:

![Weighted Image][weighted_image]

Finally, I restore the order of R, G, B channels in the final output image:

![Final Output Image][out_image]

In order to draw a single line on the left and right lanes, I modified the
draw_lines() function as follows:

1.


### 2. Potential shortcomings with my current pipeline


As seen in the challenge video output, my current pipeline fails to output a
solid line in few of the video frames, as it just discards the line
fit by np.polyfit if its slope is not within the acceptable range.


### 3. Possible improvements to my pipeline

Discard the points (x, y pairs) that cause slope of the line found by
np.polyfit. One way to do this would be by discarding points causing high
variance in the X, Y vectors.
