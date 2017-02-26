
**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
This project was completed in two parts. The first part is writing a pipeline and modififying the draw_lines() function 
to draw stable lines on lanes. The pipeline is madeup of five steps. First of all an image is converted to grayscale image.
Once, I have grayscale image, gaussian_blur is applied. The blurring will help to remove irregular spots and pixels. After this, I find the edges using canny edge detection. Now, I have edges but not all of those are important to me. Using polygon that covers the portion of image that interests to me i.e covering both lanes, I extracted that portion. Hough transform is run on that portion. After running hough, draw_lines function is used to draw lines on the image.

In order to mark two lanes with dominant line, the function was modified. The first thing I did was calculated the slop of each lines so as to find which line is left lane and which one is right. I found average slopes and  average intercepts of left and right lanes. I also calculated running average of slopes and intercepts incase of video so as to make the lanes stable. Using, those slopes and intercepts I drew lines on image.


###2. Identify potential shortcomings with your current pipeline
The potential shortcomings are that my pipeline will not perform well if there is shadow in image or image is very different and also if lanes are not very visible. Since, my pipeline does not work well on challenge video, I have removed that portion of code. 

###3. Suggest possible improvements to your pipeline
Using some more preprocessing to remove shadow and other resiliant methods, the pipeline can be modified to work under varying condition. 
