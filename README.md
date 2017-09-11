# CarND_Term1_P1

---

**Finding Lane Lines on the Road**

The goals of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Pipeline. 

My pipeline consisted of 6 steps:
* Convert the image to grayscale
* Apply gaussian blur filter
* Use canny edge detector to detect the edges on the image
* Form the region of interest (mask)
* Apply Hough transform to the masked part of the image 
* Draw lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

draw_lines() function consists of the following steps:
* Check the slope of the line and separate lines into two categories: right and left. 
* Collect coordinates (x,y) for both line types and do/update the least squares polynomial fitting. I update the estimate of the slope and bias (a and b in y = a*x+b equation for a line) using moving average formula: x_current = (x_previous*(w-1) + x_new)/w, where w is the sliding window. 
* Calculate line coordinates based on (a,b) estimates and roi size
* Draw two lines

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
