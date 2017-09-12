# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)


[image1]: Project1/test_images_out/test1.jpg "gray" Project1/test_images_output/test1.jpg 
[image2]: Project1/test_images_out/test2.jpg "g_blur"
[image3]: Project1/test_images_out/test3.jpg "edges"
[image4]: Project1/test_images_out/test4.jpg "masked"
[image5]: Project1/test_images_out/test5.jpg "hlines"
[image6]: Project1/test_images_out/test6.jpg "line_edges"
---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied gaussian blurring.

Grayscale:
![alt text] Project1/test_images_output/test1.jpg 

Gaussian blurring:
![alt text][image2]

For each step of the pipeline I displayed the image, to allow for quicker analysis of results.

After applying the gaussian blurring, Canny edge detection and masking of the image was applied.

Canny edge detection:
![alt text][image3]

Masking:
![alt text][image4]

Finally the hough transform was applied to the image and the lines were drawn unto the image:
Hough transform with (solid lines applied)
![alt text][image5]

Final result
![alt text][image6]


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by separating the 
lines with positive and negative slopes. This portion of the project (along with parameter adjustments) took most of the time.
Limits on the angles were also applied later, as better results were achieved with this rather than only using positive or negative 
slopes.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the angle of the camera changes or when the width of the lines sudden increases.

Another shortcoming could be when the curve increases drastically and moves out of the masked region.

From the challenge video it appears if reflection in the windscreen also affected the effectiveness of the pipeline.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to limit the solid lines between certain angles - this was done during the later stages of the project to get
better results

Another potential improvement could be to implement a function that can detect curves more effectively, perhaps in combination with hugh lines.
