# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/solidYellowLeft.jpg "solidYellowLeft"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

The first steps were easy. I used as starter the last exercise.
The pipeline order was very straigh forward as functions were already provide
so
1) GrAYscale image
2)Gaussian Blur
3)canny edges
4) Mask
5) Hough transformation (include the custom draw_line)
6)weighed image

As I said I used the previous exercise as starter. 
I customized draw_line function
 
because  I needed to draw lines not in the list we get from hough transformation. To be clear I needed to have a full line instead  multiple discontinued lines.
I distinguished the right lines from the left ones so I can draw the missing parts of the line
1)I started to draw lines from  coordonate of the last point of the previous lane to the actual first point of the line. even if a line is already there it doesn't hurt :)
I found out I missed the line at the bottom of the picture (when Y =max);
2)Thanks to intro to self driving car the function 	 y=mx+b where m= slope and b intercept has no secret for me now :) 
ps: I was offered preview of the first course of self driving car months ago. I've watched the course but I found out when I started the course last weekend the project was due in 5 days
So I used 3 different colors during the developpment to distinguish the lines from the hough transformation with the lines I  drawed based upon the maths I mentionned.

I would like to apologized for the writeup as I am trying to finish it before the dead line :)

I tweaked the canny threshold as well the hough min_line & max_gap as I found out in the whiteCarLaneSwitch some part of the image were mistreated as lines

### 2. Identify potential shortcomings with your current pipeline

I chose to draw one line instead of the two lines so the line (where the road marking are discontinued) is not full 
![check the  right road marking][image1]

I am not sure road corners with discontinued road marking will be efficient as I draw straigh lines
If the road marking are not as good as in the pictures (like in some french roads) I am not sure this will work perfectly


Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

remove unused part of the program.
I calculated the point with the lower Y for the right and left but I did'nt needed it
I need to draw 2 lines on the left as well in the right so the drawing would have the same size as the drawing from the hough lines
I need to have instead of fixed number for the mask using the shape of the image so my program  would work on different size of pictures
Another potential improvement could be to ...
having more time so I can test it on google images

Ps: I didn't had time to set up my github repo. Next time I will submit through this channel