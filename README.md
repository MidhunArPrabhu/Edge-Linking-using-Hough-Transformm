# EX-07 EDGE LINKING HOUGH TRANSFORM
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
```
DEVELOPED BY: MIDHUN AZHAHU RAJA P
REGISTER NUMBER: 212222240066
```

### Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("cartoon.jpg",0)
img_c=cv2.imread("cartoon.jpg",1)
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
### Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
![Screenshot 2024-04-02 114257](https://github.com/Mathiofficial/Edge-Linking-using-Hough-Transformm/assets/118787327/506360ea-a0e6-4752-8a51-33da74edac1c)

<br>

### Canny Edge detector output
**![Screenshot 2024-04-02 114320](https://github.com/Mathiofficial/Edge-Linking-using-Hough-Transformm/assets/118787327/0405b5ae-7dc2-4445-9524-2406fe03b154)
**
<br>

### Display the result of Hough transform
![Screenshot 2024-04-02 115252](https://github.com/Mathiofficial/Edge-Linking-using-Hough-Transformm/assets/118787327/a9876c5d-7597-481f-b1cf-3d86ffa1c9f9)

<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
