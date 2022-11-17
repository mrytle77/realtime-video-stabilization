# Realtime Video Stabilization
Program entirely made with c++, using the help of OpenCV. C++ is fast and powerful language.   
This program works like an EIS (Electronic Image stabilization), Originally the project was made to detect and work as a document scanner. This program checks for any available camera devices that are attached to the computer (web camera in my case), if available, it then uses it. The program then goes into an infinite loop treating 1 millisecond as one frame (though this doesn't happen due to delay created by the processor) and treating that frame as an image. Then we apply the Pre-processing of the image, then we get the Contours, then we Warp the image and display the image in another window. This process happens continuously such that the effect at large scale is treated as a video rather than image


* Preprocessing Step  
  * Convert the raw image to gray scale (cvtColor())  
  * Convert the gray scale image to blurred image (GaussionBlur())  
  * Convert the blurred image to a canny image (canny is used to detect the edges) (Canny())  
  * Covert the canny image to a dilated canny image (dilate())  

  
* Getting the Contours (Shape detection)  
  * Finding the Contours (shapes) in the dilated canny image (findCotours())  
  * Finding the area of the shapes found in the image (contourArea())  
  * Filtering the shapes for a threshold area  
  * Optional: Draw Contours around the shape (drawContours())  
  * Finding the number of points in a given shape   
  * Optional: Draw the Contours around the shape by using the point reference  
  * Filtering the shapes by number of points and max area of a shape (rectangles are filtered in)  
  * Return the points of the biggest rectange 

* Warpping the image
  * Wrapping the by considering the givern points (warpPerspective()) 
  * The final wrapped image then displayed onto a seperate window 

This example shows how, the lable on my book is stabilised and displayed on the other window even though the move my book in different angles and directions.  
Note: As I get the book closer to the screen the clarity of the output window also increases.
<p align="center">
  <img width="500" src="https://github.com/the-confused-genius/realtime-video-stabilization/blob/main/example.gif" alt="Example">
</p>
