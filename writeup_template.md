# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road Using Image Processing Pipeline**

In this simple example, we attempt to mark lane boundaries in several images and videos using an image processing pipeline, implemented in OpenCV 

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

The image processing pipeline consists of 5 steps:
1. Grayscale the image
2. Apply Gaussian blur to the image
3. Apply Canny edge detection
4. Apply a rectangular mask to approximate area of the lane
5. Apply a Hough transform to return the approximation of the left and right lane boundaries

In order to accurately create the lane boundaries, we used the output lines from the Hough transform and:
1. separate the lines from left and right based on the lines' midpoints landing inside a curtain of values.
2. averaging the lines to create one left line and right line
3. Extrapolate the line to mark the entire lane boundaries (note that I chose to crop out the lane boundaries towards the vantage point to prevent obscuring it, for safety considerations).

Here are some examples of the pipeline on images:
  
[image3]: ./output_images/solidWhiteCurve.jpg "Solid White Curve"
[image5]: ./output_images/solidWhiteRight.jpg


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
