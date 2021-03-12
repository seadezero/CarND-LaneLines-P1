# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of 5 steps:

1st Step: converts the images to grayscale
2nd Step: converts the grayscale to canny edges
3rd Step: makes a masked area for the interested area in the image
4th Step: creates the straight lines from the marked areas edges based on Hough transformation algorithm
5th Step: extrapolates two straight lines representing left lane and right lane from the Hough lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:

1st Step: separates the lines into left lines and right lines based on their positions
2nd Step: extrapolates all left lines and draws a single straight line
3rd Step: extrapolates all right lines and draws a single straight line


### 2. Identify potential shortcomings with your current pipeline

1st potential shortcoming would be when the lines are separated with large gaps, my pipeline will not 
detect the lane lines.

2nd shortcoming could be when the vehicle makes a sharp turn, my pipeline will not identify the curved
lane lines.

3rd shortcoming is when the vehicle drives up a hill or drives a road for right-side drivers, my pipeline
may not identify the interested area correctly, thus failing the task.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to modify the algorithm to detect curved lane line.

Another potential improvement could be to adjust the interested area (the mask) based on real time road info.

