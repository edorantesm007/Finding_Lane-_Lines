# Finding_Lane-_Lines
The code reads images from a video stream and finds the lane lines in the road 

1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I apply a Gaussian filter in order to smooth the image; once I have the image filtered I apply the function Canny to detect the edges in the image. Then a mask is applied to analyze only the region of interest inside the image. Next the function Hough is applied to obtain the lines in the region of interest. Finally the lines are drawn in the main image o in the Edges image.
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by adding an additional function that  read the vector lines (the output of the Hough function) and create to vectors; the first with the maximum and minimum values of the line in the right side of the image and the second with the maximum and minimum values of the line in the left side of the image. Then I draw these two vectors. 
2. Identify potential shortcomings with your current pipeline
One potential shortcoming would be what would happen when the camera it is not fixed in a static manner because the mask region or the region of interest is fixed and if the camera moves the region of interest also must move. 
Other shortcoming would happen when the car moves if it finds an obstacle in its way, because it could confuse another lines in the highway with a lane line. 
Another shortcoming could be if the image size it is variable because right now the functionality of  the code depends of a fixed pixels in the image. 
3. Suggest possible improvements to your pipeline
A possible improvement would be to implement a moving mask of interest that resizes automatically depending of the position of the camera or the image.  
Another potential improvement could be to implement more advanced methods to identify lines in an image and to classify them. 
