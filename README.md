# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.

## Program:
# DEVELOPED BY :NIROSHA S
# REG NO : 212222230097

# Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("road.jpg",0)
img_c=cv2.imread("road.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
# Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
# Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
# Draw lines on the image
```
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
# Display the result
```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image

![image](https://github.com/Niroshassithanathan/EDGE--LINKING-HOUGH-TRANSFORM/assets/121418437/b5aa80bc-dcfd-4072-862f-3b181964843e)

### Canny Edge detector output

![image](https://github.com/Niroshassithanathan/EDGE--LINKING-HOUGH-TRANSFORM/assets/121418437/c27ee4ca-1713-4944-b005-67c31a3465ec)

### Display the result of Hough transform

![image](https://github.com/Niroshassithanathan/EDGE--LINKING-HOUGH-TRANSFORM/assets/121418437/1f796003-cab3-4685-b04f-2a35df907414)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
