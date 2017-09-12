# **Finding Lane Lines on the Road** 


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied gaussian blurring.

Grayscale:
![alt text](https://github.com/BVG85/Project1/blob/master/test_images_output/test1.jpg)

Gaussian blurring:
![alt text](https://github.com/BVG85/Project1/blob/master/test_images_output/test2.jpg)

For each step of the pipeline I displayed the image, to allow for quicker analysis of results.

After applying the gaussian blurring, Canny edge detection and masking of the image was applied.

Canny edge detection:
![alt text](https://github.com/BVG85/Project1/blob/master/test_images_output/test3.jpg)

Masking:
![alt text](https://github.com/BVG85/Project1/blob/master/test_images_output/test4.jpg)

Finally the hough transform was applied to the image and the lines were drawn unto the image:
Hough transform with (solid lines applied)
![alt text](https://github.com/BVG85/Project1/blob/master/test_images_output/test5.jpg)

Final result
![alt text](https://github.com/BVG85/Project1/blob/master/test_images_output/test6.jpg)


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
