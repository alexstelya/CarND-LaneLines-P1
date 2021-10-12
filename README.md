# **Finding Lane Lines on the Road** 

[//]: # (Image References)

[image1]: ./examples/my_pipeline.png

---

### Reflection

### 1. Pipeline description

My pipeline consisted of several steps. First, I converted the images to grayscale, then I used Gaussian Blur to smooth image.
After that I used Canny edges algorithm to find edges on the image. Before using Hough algorithm to find parallels lines on the image I cut from image region of interest(for example, we don't need top part of the image as there is no road). In the end of these manipulations I had several parallel lines but I still need to draw single left and right lines.

In order to draw a single line on the left and right lanes, I separated Houghs lines for left and right lines. 
Then with help of linear regression I found my A and B variables in y = Ax+b formula for the lanes.
After that I found left and right lines coordinates and draw these lines on my original image.  

Result of the pipeline work:

![alt text][image1]


### 2. Potential shortcomings


One potential shortcoming would be what would happen when we will have a big curve on the road. 
Another shortcoming could be if we will see other lines on the road(when we have roadworks, for example)


### 3. Possible improvements

A possible improvement would be to make it more robust and handle curvy roads.
Also we should cover change of days and nights as well as weather changes.
