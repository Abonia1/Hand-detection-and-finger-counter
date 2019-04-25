# Hand-Detection-Finger-Counting
### Detect Hand and count number of fingers using Convex Hull algorithm in OpenCV lib in Python

To run the program on primary camera change line 4 to :
```python
cap = cv2.VideoCapture(0)
```
### Steps Involved
1.Find the roi(region of interest)
2.Hand Segmentation : Convert the video frame from BGR to HSV(or Gray)
3.Perform a Gaussian blur
4.Perform a Threshold
5.Find the Biggest Contour(this will be our hand)
6.Perform a convexHull and mark the ROI(region of interest
7.Count the no. of countors	
8.Display it

### SEGMENTING THE HAND SKIN
The most common is the RGB, where any pixel is composed by the union of three colors (red, green, blue). However, for color segmenting, the HSV color space is much better, because in there the information of color is dissociated from the information of illumination. HSV stands for Hue (the color information), S (Saturation, e.g., the percentage of ‘color’ present) and V (Value/brightness, e.g., the percentage of ‘white’ color present). Generally, human skin lies between (H=0,S=58) and (H=50,S=173).

For our convenience we have taken the values as 
Lower skin [0,20,70]
Upper skin [20,255,255]

Note : In order to get good segmentation you need to fine-tune HSV bounds 

### Convex Hull
In order to detect fingertips, we are going to use the Convex Hull technique. In mathematics, Convex Hull is the smallest convex set that contains a set of points. And a convex set is a set of points such that, if we trace a straight line from any pair of points in the set, that line must be also be inside the region. The result is then a nice, smooth region, much easier to be analysed than our contour, that contains many imperfections.



![image](https://drive.google.com/uc?export=view&id=1FXk-wdUJiJ0BcPv9kBdwbe31zADWJE1T)









